---
title: Aspose.Email for CPP 22.7 Release Notes
type: docs
weight: 10
url: /cpp/aspose-email-for-cpp-22-7-release-notes/
---

{{% alert color="primary" %}} 

This page contains release notes information for Aspose.Email for C++ 22.7.

{{% /alert %}} 

Aspose.Email for C++ 22.7 is based on [Aspose.Email for .NET 22.6](https://docs.aspose.com/email/net/aspose-email-for-net-22-6-release-notes/).

Aspose.Email for C++ does not support yet asyncronic features of e-mail protocols


## **New Enhancements**


### **Extracting calendar item from PST and save as ICS with original timestamp.**

**Changes in public API:**

`MapiCalendarIcsSaveOptions` - Allows to specify additional options when saving MapiCalendar to Ics format.
`MapiCalendarIcsSaveOptions.KeepOriginalDateTimeStamp` - Allows keep original DateTimeStamp value in output file.

**Code samples:**

``` cpp
auto cal = System::DynamicCast<Aspose::Email::Mapi::MapiCalendar>(pst->ExtractMessage(messageInfo)->ToMapiMessageItem());

if (cal)
{
  auto options = System::MakeObject<MapiCalendarMsgSaveOptions>();
  options->set_KeepOriginalDateTimeStamp(true);

  cal->Save(u"cal.ics", options);
}
```

The full code of the examples can be found at **[Aspose Email for C++ GitHub examples repository](https://github.com/aspose-email/Aspose.Email-for-C).**




