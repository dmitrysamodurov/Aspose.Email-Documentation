---
title: Connecting to IMAP Server
type: docs
weight: 10
url: /python-net/connecting-to-imap-server/
---


Connecting with IMAP Server described how to connect to an IMAP server in four simple steps:

1. Create an instance of the ImapClient class.
1. Specify the hostname, username and password.
1. Specify the port.
1. Specify the Security Options.

The process for connecting to an SSL enables IMAP server is similar but requires that you set another few properties:

- Set Security Options to SSLImplicit.

The following code snippet shows how to

1. Set a username, password and port.
1. Set security option.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-SSLEnabledIMAPServer-SSLEnabledIMAPServer.py" >}}
