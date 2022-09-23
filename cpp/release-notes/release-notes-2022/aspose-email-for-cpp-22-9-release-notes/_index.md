---
title: Aspose.Email for CPP 22.9 Release Notes
type: docs
weight: 10
url: /cpp/aspose-email-for-cpp-22-9-release-notes/
---

{{% alert color="primary" %}} 

This page contains release notes information for Aspose.Email for C++ 22.9.

{{% /alert %}} 

Aspose.Email for C++ 22.9 is based on [Aspose.Email for .NET 22.8](https://docs.aspose.com/email/net/aspose-email-for-net-22-8-release-notes/).

Aspose.Email for C++ does not support yet asyncronic features of e-mail protocols


## **New Enhancements**

### **Configuring the load options when reading messages from MBOX**

**Changes in public API:**

 - `MailStorageConverter::set_MboxMessageOptions, MailStorageConverter::get_MboxMessageOptions` methods - Gets or sets email load options when parsing an Mbox storage.
 - `MboxrdStorageReader::ReadNextMessage(EmlLoadOptions options)` method - EmlLoadOptions parameter specifies options when reading message from Mbox storage.

**Code samples:**

```cpp
auto reader = System::MakeObject<MboxrdStorageReader>(fileName, System::MakeObject<MboxLoadOptions>());

// Read messages preserving tnef attachments.
auto options = System::MakeObject<EmlLoadOptions>()
options->set_PreserveTnefAttachments(true)
auto eml = reader->ReadNextMessage(options);
```

```cpp
auto options = System::MakeObject<EmlLoadOptions>()
options->set_PreserveTnefAttachments(true)
MailStorageConverter::set_MboxMessageOptions(options);

// Convert messages from mbox to pst preserving tnef attachments.
auto pst = MailStorageConverter::mboxToPst(u"Input.mbox", u"Output.pst");
```


The full code of the examples can be found at **[Aspose Email for C++ GitHub examples repository](https://github.com/aspose-email/Aspose.Email-for-C).**




