---
title: Public API Changes in Aspose.Email 6.3.0
type: docs
weight: 280
url: /net/public-api-changes-in-aspose-email-6-3-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.
## **Added APIs**
Class Aspose.Email.FileFormatType
Class Aspose.Email.FileFormatInfo
Class Aspose.Email.FileFormatUtil
Method Aspose.Email.FileFormatUtil.DetectFileFormat(Stream)
Method Aspose.Email.FileFormatUtil.DetectFileFormat(String)

Method Aspose.Email.Mail.MailMessage.AttachSignature(Cryptography.Pkcs.CmsSigner, Boolean)
Method Aspose.Email.Mail.MailMessage.AttachSignature(Cryptography.X509Certificates.X509Certificate2, Boolean)

Class Aspose.Email.TimeoutException
Method Aspose.Email.TimeoutException.#ctor
Method Aspose.Email.TimeoutException.#ctor(String)

Property Aspose.Email.Mail.EmlSaveOptions.CheckBodyContentEncoding
Property Aspose.Email.Mail.HtmlSaveOptions.CheckBodyContentEncoding
Property Aspose.Email.Mail.MhtSaveOptions.CheckBodyContentEncoding

**Some classes have been moved to the new namespaces. It's necessary to use the newly created same classes in the new namespaces.** 
**The old namespaces and their obsolete classes will be removed soon.** 
**The following table shows these changes.**

|**Deprecated namespace** |**New namespace** |**Moved namespace members** |
| :- | :- | :- |
|Aspose.Email.Common.Commands |Aspose.Email |**Classes** <br>AsyncCommand <br>ResultEventArgs <br>CommandStatus <br><br>**Interfaces** <br>IAsyncCommand <br>ICommand <br><br>**Enumerations** <br>AsyncCommandResults |
|Aspose.iCalendar |Aspose.Email.Recurrences |**Classes** <br>ByDay <br>ByDayCollection <br>ByNumberCollection <br>DateCollection <br>RecurrencePattern (renamed to CalendarRecurrence) <br>RecurrenceRule <br>RecurrenceRuleCollection <br><br>**Enumerations** <br>EndType <br>Frequency |
|Aspose.Email.Mail.Calendaring |Aspose.Email.Recurrences |**Classes** <br>DailyRecurrencePattern <br>MonthlyRecurrencePattern <br>RecurrencePattern <br>WeeklyRecurrencePattern <br>YearlyRecurrencePattern <br><br>**Enumerations** <br>CalendarDay <br>CalendarMonth <br>DayPosition |
|Aspose.Email.Verify |Aspose.Email.Verifications |**Classes** <br>DomainValidatingEventArgs <br>EmailValidator <br>MailServerValidatingEventArgs <br>SyntaxValidatingEventArgs <br>ValidationResult <br><br>**Delegates** <br>DomainValidatingEventHandler <br>MailServerValidatingEventHandler <br>SyntaxValidatingEventHandler <br><br>**Enumerations** <br>ValidationPolicy <br>ValidationResponseCode |
|Aspose.Windows.Forms |Aspose.Email.Windows.Forms |**Classes** <br>FileDataObject <br>FileDataObjectCollection <br>FileDragEventArgs <br>FileDropTargetManager <br>FileDropTargetPanel <br>MailClientAgent <br>Recipient <br>RecipientCollection <br><br>**Interfaces** <br>IFileDropTargetControl <br><br>**Delegates** <br>FileDragEventHandler <br><br>**Enumerations** <br>RecipientType |

