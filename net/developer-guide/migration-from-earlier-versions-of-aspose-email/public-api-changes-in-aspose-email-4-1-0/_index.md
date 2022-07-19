---
title: Public API Changes in Aspose.Email 4.1.0
type: docs
weight: 60
url: /net/public-api-changes-in-aspose-email-4-1-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.

**Adds ImapMessageInfo.InternalDate property**

Gets the internal date for a message

**Adds IEWSClient.Reply, IEWSClient.ReplyAll, IEWSClient.Forward methods**

Provides the ability to send RE and FW messages in IEWSClient

**Adds MhtFormatOptions enum with members WriteCompleteEmailAddressToMht, HideExtraPrintHeader**

Provides the control of the top header visibility in Mht output. The MhtMessageFormatter.Format(MailMessage message, bool writeCompleteEmailAddress) method marked as obsolete. Use the MhtMessageFormatter.Format(MailMessage message, MhtFormatOptions formatOptions) method instead.

**Adds MailMessageSaveOptions.HideExtraPrintHeader enum member**

Provides the control of the top header visibility in Mht output.

**Adds ImapMessageInfo.MessageId property**

Gets the MessageId string
