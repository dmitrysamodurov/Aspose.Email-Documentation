---
title: Aspose.Email for CPP 22.8 Release Notes
type: docs
weight: 10
url: /cpp/aspose-email-for-cpp-22-8-release-notes/
---

{{% alert color="primary" %}} 

This page contains release notes information for Aspose.Email for C++ 22.8.

{{% /alert %}} 

Aspose.Email for C++ 22.8 is based on [Aspose.Email for .NET 22.7](https://docs.aspose.com/email/net/aspose-email-for-net-22-7-release-notes/).

Aspose.Email for C++ does not support yet asyncronic features of e-mail protocols


## **New Enhancements**


### **Obtaining the identification info for messages received from a mailbox**

Sometimes, when processing messages received from the server, it is required to get the message identification info such as UID or sequence number.

**Changes in public API:**

 - `Aspose::Email::MailboxInfo` class - Represents identification information about message in a mailbox.
    - `Aspose::Email::MailboxInfo::SequenceNumber` property - The sequence number of message.
    - `Aspose::Email::MailboxInfo::UniqueId` property - The unique id of message.
 - `Aspose::Email::MailMessage::ItemId` property - Represents identification information about message in a mailbox.

**Code samples:**

```cpp
    System::SharedPtr<ImapClient> client = System::MakeObject<ImapClient>(u"host.domain.com", 993, u"username", u"password");

    System::SharedPtr<ImapMessageInfoCollection> msgs = client->ListMessages();
    for (auto&& msgInfo : System::IterateOver(msgs))
    {
        System::String sequenceNumber = msgInfo->get_SequenceNumber();
        System::Console::WriteLine(System::String(u"SequenceNumber: ") + sequenceNumber);
        System::SharedPtr<MailMessage> msg = client->FetchMessage(sequenceNumber);
        System::Console::WriteLine(System::String(u"Subject: ") + msg->get_Subject());
    }
```

The full code of the examples can be found at **[Aspose Email for C++ GitHub examples repository](https://github.com/aspose-email/Aspose.Email-for-C).**




