---
title: Connect to POP3 Server
type: docs
weight: 10
url: /python-net/connect-to-pop3-server/
---

## **Connecting to POP3 Server**
The Pop3Client class allows applications to manage email boxes using the Post Office Protocol, Version 3 (POP3). To connect to a server, use the Pop3Client class. The Pop3Client class is the major entry for developers who want to add POP3 management to their .NET applications. This article explains how to use it. To connect to a POP3 server:

1. Create an instance of the Pop3Client class as client.
1. Specify the host, username and password in the Pop3Client instance.

The following code snippet shows you how to connect with POP3 server.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-POP3-ConnectingToPOP3-ConnectingToPOP3.py" >}}
## **Connecting to SSL server**
Connecting to a POP3 Server described how to connect to a POP3 server in three simple steps:

1. Create an instance of the Pop3Client class.
1. Specify the host, username and password.

The process for connecting to an SSL enabled POP3 server is similar but requires that you set another few properties:

- SecurityOptions
- Port

To connect to an SSL enabled POP3 server, use the Aspose.Email.Pop3.Pop3Client class and set the SecurityOptions and Port properties. The following code snippet shows you how to connect to an SSL enables POP3 server.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-POP3-SSLEnabledPOP3Server-SSLEnabledPOP3Server.py" >}}
