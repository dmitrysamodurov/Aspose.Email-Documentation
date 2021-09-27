---
title: Connect to POP3 Server
type: docs
weight: 10
url: /net/connect-to-pop3-server/
---


The [Pop3Client](https://apireference.aspose.com/email/net/aspose.email.clients.pop3/pop3client) class allows applications to manage email boxes using the Post Office Protocol, Version 3 (POP3). To connect to a server, use the [Pop3Client](https://apireference.aspose.com/email/net/aspose.email.clients.pop3/pop3client) class. The [Pop3Client](https://apireference.aspose.com/email/net/aspose.email.clients.pop3/pop3client) class is the major entry for developers who want to add POP3 management to their .NET applications. This article explains how to use it. To connect to a POP3 server:

1. Create an instance of the [Pop3Client](https://apireference.aspose.com/email/net/aspose.email.clients.pop3/pop3client) class.
1. Specify the host, username, and password in the [Pop3Client](https://apireference.aspose.com/email/net/aspose.email.clients.pop3/pop3client) instance.

The following code snippet shows you how to connect with the POP3 server.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-POP3-ConnectingToPOP3-ConnectingToPOP3.cs" >}}
## **Connecting to SSL server**
[Connecting to a POP3 Server](#connecting-to-pop3-server) described how to connect to a POP3 server in three simple steps:

1. Create an instance of the [Pop3Client](https://apireference.aspose.com/email/net/aspose.email.clients.pop3/pop3client) class.
1. Specify the host, username, and password.

The process for connecting to an SSL enabled POP3 server is similar but requires that you set another few properties:

- [SecurityOptions](https://apireference.aspose.com/email/net/aspose.email.clients/securityoptions)
- Port

To connect to an SSL enabled POP3 server, use the [Pop3Client](https://apireference.aspose.com/email/net/aspose.email.clients.pop3/pop3client) class and set the [SecurityOptions](https://apireference.aspose.com/email/net/aspose.email.clients/securityoptions) and Port properties. The following code snippet shows you how to connect to an SSL enables POP3 server.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-POP3-SSLEnabledPOP3Server-SSLEnabledPOP3Server.cs" >}}
## **Connecting with an APOP Server**
POP stands for Post Office Protocol. APOP stands for Authenticated Post Office Protocol. APOP is an extended version of the POP3 server setting that encrypts your username and password and uses an authentication mechanism designed to protect your POP3 account's password when checking email. APOP authentication does not require the account password to be sent as plain text to the POP3 mail server.
## **Connecting to Server via Proxy**
Proxy servers are very common for communicating with the outside world. In such cases, proxy addresses are used for email clients to access mailboxes over the Internet. Aspose.Email provides support for versions 4, 4a and 5 of the SOCKS proxy protocol. This article provides a working sample of retrieving email using a proxy mail server. To retrieve email via a proxy server:

1. Initialize [Proxy](https://apireference.aspose.com/email/net/aspose.email.clients/proxy) with the required information, that is, proxy address, port, and SOCKS version.
1. Initialize [Pop3Client](https://apireference.aspose.com/email/net/aspose.email.clients.pop3/pop3client) with the host address, user name, password, and any other settings.
1. Set the client's Proxy property to the [Proxy](https://apireference.aspose.com/email/net/aspose.email.clients/proxy) object created above.

The following code snippet shows you how to retrieve email via proxy server.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-POP3-RetrieveEmailViaProxyServer-RetrieveEmailViaProxyServer.cs" >}}
## **Connecting to Server via HTTP Proxy**
{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-POP3-AccessMailboxViaHttpProxy-AccessPOP3MailboxViaHttpProxy.cs" >}}
