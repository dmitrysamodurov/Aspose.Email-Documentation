---
title: Working with Message Flags on Server
type: docs
weight: 60
url: /python-net/working-with-message-flags-on-server/
---


## **Changing the Message Flags**
You can change message flags by using the ChangeMessageFlags() method. This method takes two parameters.

1. The message's sequence number or unique ID.
1. MessageFlag.

The following flags can be set:

- Answered
- Deleted
- Draft
- Empty
- Flagged
- IsRead
- Recent
### **Setting Message Flags**
The following code snippet shows you how to change message flags on an IMAP server with Aspose.Email.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-SettingMessageFlags-SettingMessageFlags.py" >}}
### **Setting Custom Flags**
You can also set custom flags to a message using the ImapClient of the API. The ImapClient's AddMessageFlags provides the ability of setting custom flags on messages.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-SetCustomFlags-SetCustomFlags.py" >}}
