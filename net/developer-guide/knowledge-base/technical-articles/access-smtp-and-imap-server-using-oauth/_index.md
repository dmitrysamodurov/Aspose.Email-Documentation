---
title: Access SMTP and IMAP Server using OAuth
type: docs
weight: 190
url: /net/access-smtp-and-imap-server-using-oauth/
---


OAuth 2.0 support has been added to Aspose.Email and can be used to access **SMTP**, **POP3**, and **IMAP** servers.
In general, all servers which are support **OAuth 2.0** bearer tokens can be used with Aspose.Email, but our email clients have been tested with Google mail servers and Microsoft Office 365 servers.
Access to the server from the EmailClient with OAuth may be implemented in 2 ways.

1. Provide access token directly into the constructor of EmailClient. In this case, the user has to understand that lifetime of access tokens is limited. When the token is expired, EmailClient can't be used to access the server.
2. Provide a custom implementation of token provider based on ITokenProvider interface into the constructor of EmailClient. In this case, the client checks token expiration time and requests ITokenProvider for a new access token when the previous is expired. In this way, the client refreshes tokens periodically and may work with the server for unlimited time. Оften services support a simple way to refresh access tokens. For example, using refresh tokens in google services or ROPC authentication flow in Microsoft identity platform can be used for implementation token provider.

## **Configure an account on the appropriate server**

For [office365](https://docs.microsoft.com/en-us/exchange/client-developer/legacy-protocols/how-to-authenticate-an-imap-pop-smtp-application-by-using-oauth)
For [gmail](https://developers.google.com/gmail/imap/imap-smtp)

## **Access mail services with the access tokens**

```csharp
using (SmtpClient client = new SmtpClient(
    "smtp.gmail.com",
    587,
    "user1@gmail.com",
    "accessToken",
    true,
    SecurityOptions.SSLExplicit))
{

}

using (ImapClient client = new ImapClient(
   "imap.gmail.com",
   993,
   "user1@gmail.com",
   "accessToken",
   true))
{

}

using (Pop3Client client = new Pop3Client(
   "pop.gmail.com",
   995,
   "user1@gmail.com",
   "accessToken",
   true,
   SecurityOptions.Auto))
{

}
```

## **Access mail services with the token providers**

```csharp
ITokenProvider tokenProvider = TokenProvider.Google.GetInstance(
     "ClientId",
     "ClientSecret",
     "RefreshToken");

using (SmtpClient client = new SmtpClient(
    "smtp.gmail.com",
    587,
    "user1@gmail.com",
    tokenProvider,
    SecurityOptions.SSLExplicit))
{

}

using (ImapClient client = new ImapClient(
   "imap.gmail.com",
   993,
   "user1@gmail.com",
   tokenProvider))
{
}

using (Pop3Client client = new Pop3Client(
   "pop.gmail.com",
   995,
   "user1@gmail.com",
   tokenProvider,
   SecurityOptions.Auto))
{
}
```

## **Implementation of custom ITokenProvider for Office365**

```cssharp
using JsonConvert = Newtonsoft.Json.JsonConvert;
using Aspose.Email.Clients;
using Aspose.Email.Common.Utils;
using Aspose.Email.Tests.TestUtils;
using Newtonsoft.Json;
using System;
using System.IO;
using System.Net;
using System.Text;

namespace TestNS
{
    /// <summary>
    /// Azure resource owner password credential (ROPC) token provider
    /// https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth-ropc
    /// https://portal.azure.com
    /// https://developer.microsoft.com/en-us/graph/graph-explorer/#
    /// token parser https://jwt.io
    /// </summary>
    internal class AzureROPCTokenProvider : ITokenProvider
    {
        private const string uriFormat = "https://login.microsoftonline.com/{0}/oauth2/v2.0/token";
        private const string bodyFormat =
            "client_id={0}" +
            "&scope={1}" +
            "&username={2}" +
            "&password={3}" +
            "&grant_type={4}";

        private readonly string scope;
        private const string grant_type = "password";
        private readonly object tokenSyncObj = new object();
        private OAuthToken token;
        private readonly string tenant;
        private readonly string clientId;
        private readonly string clientSecret;
        private readonly string userName;
        private readonly string password;

        /// <summary>
        /// Initializes a new instance of the <see cref="AzureROPCTokenProvider"/> class
        /// </summary>
        /// <param name="tenant"></param>
        /// <param name="clientId"></param>
        /// <param name="clientSecret"></param>
        /// <param name="scope"></param>
        /// <param name="userName"></param>
        /// <param name="password"></param>
        /// <param name="scopeAr"></param>
        public AzureROPCTokenProvider(
            string tenant, 
            string clientId, 
            string clientSecret, 
            string userName, 
            string password,
            string[] scopeAr)
        {
            this.tenant = tenant;
            this.clientId = clientId;
            this.clientSecret = clientSecret;
            this.userName = userName;
            this.password = password;
            this.scope = string.Join(" ", scopeAr);
        }

        /// <summary>
        /// Gets oAuth access token. 
        /// </summary>
        /// <param name="ignoreExistingToken">
        /// If ignoreExistingToken is true, requests new token from a server. Otherwise behaviour is depended on whether token exists or not.
        /// If token exists and its expiration date is not expired returns current token, otherwise requests new token from a server.
        /// </param>
        /// <returns>Returns oAuth access token</returns>
        public virtual OAuthToken GetAccessToken(bool ignoreExistingToken)
        {
            lock (tokenSyncObj)
            {
                if (this.token != null && !this.token.Expired && !ignoreExistingToken)
                    return this.token;
                token = null;
                string uri = string.Format(uriFormat, string.IsNullOrWhiteSpace(tenant) ? "common" : tenant);
                HttpWebRequest request = (HttpWebRequest)HttpWebRequest.Create(uri);
                string body = string.Format(bodyFormat,
                    HttpUtility.UrlEncode(clientId),
                    HttpUtility.UrlEncode(scope),
                    HttpUtility.UrlEncode(userName),
                    HttpUtility.UrlEncode(password),
                    HttpUtility.UrlEncode(grant_type));
                byte[] bytes = Encoding.ASCII.GetBytes(body);
                request.Method = "POST";
                request.ContentType = "application/x-www-form-urlencoded";
                request.ContentLength = bytes.Length;
                MemoryStream ms = new MemoryStream(bytes);
                using (Stream requestStream = request.GetRequestStream())
                    requestStream.Write(bytes, 0, bytes.Length);
                HttpWebResponse response = (HttpWebResponse)request.GetResponse();
                StringBuilder responseText = new StringBuilder();
                bytes = new byte[1024];
                int read = 0;
                using (Stream stream = response.GetResponseStream())
                {
                    while ((read = stream.Read(bytes, 0, bytes.Length)) > 0)
                        responseText.Append(Encoding.ASCII.GetString(bytes, 0, read));
                }
                string jsonString = responseText.ToString();
                AzureTokenResponse t = JsonConvert.DeserializeObject<AzureTokenResponse>(jsonString);
                token = new OAuthToken(
                    t.access_token,
                    TokenType.AccessToken,
                    DateTime.Now.AddSeconds(t.expires_in));
                return token;
            }
        }

        /// <summary>
        /// Gets oAuth access token.
        /// If token exists and its expiration date is not expired returns current token, otherwise requests new token from a server.
        /// </summary>
        /// <returns>Returns oAuth access token</returns>
        public OAuthToken GetAccessToken()
        {
            return GetAccessToken(false);
        }

        /// <summary>
        /// Performs application-defined tasks associated with freeing, releasing, or resetting unmanaged resources.
        /// </summary>
        public virtual void Dispose()
        {
        }
    }

    /// <summary>
    /// A success response contains a JSON OAuth 2.0 response with the following parameters.
    /// </summary>
    public class AzureTokenResponse
    {
        /// <summary>
        /// The requested access token. The calling web service can use this token to authenticate to the receiving web service.
        /// </summary>
        public string access_token { get; set; }

        /// <summary>
        /// Indicates the token type value. The only type that Azure AD supports is Bearer For more information about bearer tokens, 
        /// see The OAuth 2.0 Authorization Framework: Bearer Token Usage (RFC 6750).
        /// </summary>
        public string token_type { get; set; }

        /// <summary>
        /// How long the access token is valid (in seconds).
        /// </summary>
        public int expires_in { get; set; }

        /// <summary>
        /// How long the access token is valid (in seconds).
        /// </summary>
        public int ext_expires_in { get; set; }

        /// <summary>
        /// The time when the access token expires. 
        /// The date is represented as the number of seconds from 1970-01-01T00:00:00Z UTC until the expiration time.
        /// This value is used to determine the lifetime of cached tokens.
        /// </summary>
        public int expires_on { get; set; }

        /// <summary>
        /// The App ID URI of the receiving web service.
        /// </summary>
        public string resource { get; set; }

        /// <summary>
        /// If an access token was returned, this parameter lists the scopes the access token is valid for.
        /// </summary>
        public string scope { get; set; }

        /// <summary>
        /// Issued if the original scope parameter included the openid scope.
        /// </summary>
        public string id_token { get; set; }

        /// <summary>
        /// Issued if the original scope parameter included offline_access.
        /// </summary>
        public string refresh_token { get; set; }
    }
}

```

```csharp
ITokenProvider tokenProvider = new AzureROPCTokenProvider(
    "Tenant",
    "ClientId",
    "ClientSecret",
    "EMail",
    "Password",
    scopeAr);

using (ImapClient client = new ImapClient(
    "outlook.office365.com",
    993,
    "Test1@test.onmicrosoft.com",
    tokenProvider,
    SecurityOptions.SSLImplicit))
{

}

using (SmtpClient client = new SmtpClient(
    "smtp.office365.com",
    587,
    "Test1@test.onmicrosoft.com",
    tokenProvider,
    SecurityOptions.SSLExplicit))
{

}

using (Pop3Client client = new Pop3Client(
   "outlook.office365.com",
   995,
   "Test1@test.onmicrosoft.com",
   tokenProvider,
   SecurityOptions.Auto))
{

}
```
