---
title: Public API Changes in Aspose.Email 5.2.0
type: docs
weight: 170
url: /net/public-api-changes-in-aspose-email-5-2-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.
## **Added APIs**
Class Aspose.Email.Mail.DKIM.CanonicalizationType
Class Aspose.Email.Mail.DKIM.DKIMHashAlgorithm
Class Aspose.Email.Mail.DKIM.DKIMSignatureInfo
Class Aspose.Email.Mail.DKIM.HeaderList
Class Aspose.Email.Mail.DKIM.PemReader
Field/Enum Aspose.Email.Mail.DKIM.CanonicalizationType.Relaxed
Field/Enum Aspose.Email.Mail.DKIM.CanonicalizationType.Simple
Field/Enum Aspose.Email.Mail.DKIM.DKIMHashAlgorithm.RSASha1
Field/Enum Aspose.Email.Mail.DKIM.DKIMHashAlgorithm.RSASha256
Method Aspose.Email.Mail.DKIM.DKIMSignatureInfo.#ctor(System.String,System.String)
Method Aspose.Email.Mail.DKIM.HeaderList.#ctor
Method Aspose.Email.Mail.DKIM.PemReader.GetPrivateKey(System.IO.Stream)
Method Aspose.Email.Mail.DKIM.PemReader.GetPrivateKey(System.String)
Property Aspose.Email.Mail.DKIM.DKIMSignatureInfo.BodyCanonicalization
Property Aspose.Email.Mail.DKIM.DKIMSignatureInfo.Domain
Property Aspose.Email.Mail.DKIM.DKIMSignatureInfo.HashAlgorithm
Property Aspose.Email.Mail.DKIM.DKIMSignatureInfo.HeaderCanonicalization
Property Aspose.Email.Mail.DKIM.DKIMSignatureInfo.Headers
Property Aspose.Email.Mail.DKIM.DKIMSignatureInfo.Selector
Property Aspose.Email.Mail.DKIM.DKIMSignatureInfo.Time
Method Aspose.Email.Mail.MailMessage.DKIMSign(System.Security.Cryptography.RSACryptoServiceProvider, Aspose.Email.Mail.DKIM.DKIMSignatureInfo)

Class Aspose.Email.OAuth.TokenProvider
Class Aspose.Email.OAuth.TokenProvider.Google
Class Aspose.Email.OAuth.TokenProvider.Outlook
Method Aspose.Email.OAuth.BaseTokenProvider.#ctor
Method Aspose.Email.OAuth.TokenProvider.Dispose
Method Aspose.Email.OAuth.TokenProvider.GetAccessToken
Method Aspose.Email.OAuth.TokenProvider.GetAccessToken(System.Boolean)
Method Aspose.Email.OAuth.TokenProvider.GetInstance(System.String,System.String,System.String,System.String)
Method Aspose.Email.OAuth.TokenProvider.Google.GetInstance(System.String,System.String,System.String)
Method Aspose.Email.OAuth.TokenProvider.Outlook.GetInstance(System.String,System.String,System.String)
Property Aspose.Email.OAuth.TokenProvider.ClientId
Property Aspose.Email.OAuth.TokenProvider.ClientSecret
Property Aspose.Email.OAuth.TokenProvider.ExtraParameters
Property Aspose.Email.OAuth.TokenProvider.Login
Property Aspose.Email.OAuth.TokenProvider.Password
Property Aspose.Email.OAuth.TokenProvider.RefreshToken
Property Aspose.Email.OAuth.TokenProvider.RequestUrl
Property Aspose.Email.OAuth.TokenProvider.UseBasicAuthorization

Method Aspose.Email.Imap.ImapQueryBuilder.#ctor(System.Text.Encoding)
Method Aspose.Email.MailQueryBuilder.#ctor(System.Text.Encoding)
Property Aspose.Email.MailQueryBuilder.DefaultEncoding

Property Aspose.Email.Exchange.ExchangeMessageInfo.Size
