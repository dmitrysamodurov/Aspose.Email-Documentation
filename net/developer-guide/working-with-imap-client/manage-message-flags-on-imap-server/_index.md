---
title: Managing Message Flags on IMAP Server
ArticleTitle: Set, Change & Remove Message Flags on IMAP Server
type: docs
weight: 40
url: /net/manage-message-flags-on-imap-server/
---

## **Set/Change Message Flags**

You can change message flags by setting new ones with the [ChangeMessageFlags()](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapclient/changemessageflags/#changemessageflags/) method. This method takes two parameters.

1. The sequence number of a message or its unique ID.
2. [MessageFlag](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapmessageflags/).

The following flags can be set:

- [Answered](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapmessageflags/answered/)
- [Deleted](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapmessageflags/deleted/)
- [Draft](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapmessageflags/draft/)
- [Empty](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapmessageflags/empty/)
- [Flagged](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapmessageflags/flagged/)
- [IsRead](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapmessageflags/isread/)
- [Recent](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapmessageflags/recent/)

The following code snippet shows you how to change message flags on an IMAP server with Aspose.Email.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-IMAP-SettingMessageFlags-SettingMessageFlags.cs" >}}

## **Remove Message Flags**

Message flags can also be removed with the [RemoveMessageFlags()](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapclient/removemessageflags/#removemessageflags/) method. Usage is similar to that of the [ChangeMessageFlags()](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapclient/changemessageflags/#changemessageflags/) method. It takes a sequence number or unique message ID and [MessageFlag](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapmessageflags/). The following code snippet shows you how to remove message flags.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-IMAP-RemovingMessageFlags-RemovingMessageFlags.cs" >}}

## **Set Custom Flags**

You can also set custom flags to a message using the [ImapClient](https://reference.aspose.com/email/net/aspose.email.clients.imap/imapclient/) of the API. The ImapClient AddMessageFlags provides the ability to set custom flags on messages.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-IMAP-SetCustomFlag-SetCustomFlag.cs" >}}
