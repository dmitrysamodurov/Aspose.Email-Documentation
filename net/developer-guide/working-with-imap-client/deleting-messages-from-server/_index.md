---
title: Deleting Messages from Server
type: docs
weight: 50
url: /net/deleting-messages-from-server/
---


## **Deleting Messages**
The [ImapClient](https://apireference.aspose.com/email/net/aspose.email.clients.imap/imapclient) class can delete messages from an IMAP server. The [ImapClient](https://apireference.aspose.com/email/net/aspose.email.clients.imap/imapclient) class [DeleteMessage()](https://apireference.aspose.com/email/net/aspose.email.clients.imap/imapclient/methods/deletemessage/index) function is used to delete messages. It takes the message sequence number or unique ID as a parameter. The [ImapClient](https://apireference.aspose.com/email/net/aspose.email.clients.imap/imapclient) provides [DeleteMessage](https://apireference.aspose.com/email/net/aspose.email.clients.imap/imapclient/methods/deletemessage/index) and [DeleteMessages](https://apireference.aspose.com/email/net/aspose.email.clients.imap/imapclient/methods/deletemessages/index) methods for deleting messages one by one or multiple. The following code snippet shows you how to delete an email message with the message ID 1 from an IMAP server.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-IMAP-DeleteSingleMessage-DeleteSingleMessage.cs" >}}
## **Deleting Multiple Messages**
Multiple emails can be deleted from mailbox using the [ImapClient](https://apireference.aspose.com/email/net/aspose.email.clients.imap/imapclient) of Aspose.Email API. The [DeleteMessages](https://apireference.aspose.com/email/net/aspose.email.clients.imap/imapclient/methods/deletemessages/index) method provides a number of options to delete multiple messages from the server using unique ids, sequence numbers or [ImapMessageInfoCollection](https://apireference.aspose.com/email/net/aspose.email.clients.imap/imapmessageinfocollection) elements. The following code snippet shows you how to delete multiple messages.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-IMAP-DeleteMultipleMessages-DeleteMultipleMessages.cs" >}}
