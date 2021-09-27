---
title: Access SMTP and IMAP Server using OAuth
type: docs
weight: 190
url: /java/access-smtp-and-imap-server-using-oauth/
---


Aspose.Email for Java can be used to access SMTP and IMAP servers. OAuth support for Google mail is implemented only for version 2.0 as OAuth 1.0 has been [officially deprecated as of April 20, 2012](https://developers.google.com/accounts/docs/RegistrationForWebAppsAuto). At this moment, Google supports OAuth only for [the Google Apps Platform](https://developers.google.com/gmail/imap) and public mail accounts can't be used with the OAuth mechanism. When a new Google Apps account is created, a new "Installed Application" should be registered for this account for testing in the APIs Console. [Free trial accounts](https://www.google.com/a/signup/?hl=en&source=gafb-homepage-canvas-en) can be created, provided by Google Apps for Business.
## **Using Aspose.Email to Access SMTP and IMAP Servers**
With Aspose.Email for Java, it is possible to access SMTP and IMAP servers using OAuth. The following code snippet uses this feature to access SMTP and IMAP server.
How to use [GoogleOAuthHelper Class](/email/java/gmail-utility-features/#googleoauthhelper-class)


~~~Java
public static void run() {
    try {
        String accessToken = getAccessToken(authorizationCode);
        accessSMTPServer(accessToken);
        accessIMAPServer(accessToken);
    } catch (Exception ex) {
        System.err.println(ex);
    }
}

static void accessSMTPServer(String accessToken) {
    MailMessage message = new MailMessage("user1@testaccount.com", "user1@testaccount.com", "SUBJECT - " + UUID.randomUUID().toString(), "Access to SMTP servers using OAuth");
    try (SmtpClient client = new SmtpClient("smtp.gmail.com", 587, "user1@testaccount.com", accessToken, true)) {
        client.setTimeout(400000);
        client.setSecurityOptions(SecurityOptions.SSLImplicit);
        client.send(message);
    }
}

static void accessIMAPServer(String accessToken) {
    try (ImapClient client = new ImapClient("imap.gmail.com", 993, "user1@testaccount.com", accessToken, true)) {
        client.setSecurityOptions(SecurityOptions.SSLImplicit);
        client.selectFolder("Inbox");
        ImapMessageInfoCollection messageInfoCol = client.listMessages();
    }
}
~~~