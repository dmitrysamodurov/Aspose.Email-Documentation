---
title: Aspose.Email for CPP 22.11 Release Notes
type: docs
weight: 10
url: /cpp/aspose-email-for-cpp-22-11-release-notes/
---

{{% alert color="primary" %}} 

This page contains release notes information for Aspose.Email for C++ 22.11.

{{% /alert %}} 

Aspose.Email for C++ 22.11 is based on [Aspose.Email for .NET 22.10](https://docs.aspose.com/email/net/aspose-email-for-net-22-10-release-notes/).

Aspose.Email for C++ does not support asyncronic features of e-mail protocols

## **New Features**


### **Renaming an Attachment in MapiMessage**

It is possible to edit the DisplayName property value in MapiMessage attachments now.

**Code samples:**

```cpp
auto msg = MapiMessage->Load(fileName);
msg->get_Attachments[0]->set_DisplayName(u"New display name 1");
msg->get_Attachments[1]->set_DisplayName(u"New display name 2");
```

The full code of the examples can be found at **[Aspose Email for C++ GitHub examples repository](https://github.com/aspose-email/Aspose.Email-for-C).**




