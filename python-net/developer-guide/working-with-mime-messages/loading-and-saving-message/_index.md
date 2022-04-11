---
title: Loading and Saving Message
type: docs
weight: 30
url: /python-net/loading-and-saving-message/
---


## **Detecting File Formats**
Aspose.Email API provides the capability to detect file format of provided message file. The DetectFileFormat method of FileFormatUtil class can be used to achieve this. The following classes and methods can be used to detect the loaded file format.

- Class Aspose.Email.FileFormatType
- Class Aspose.Email.FileFormatInfo
- Class Aspose.Email.FileFormatUtil
- Method Aspose.Email.FileFormatUtil.DetectFileFormat(Stream)
- Method Aspose.Email.FileFormatUtil.DetectFileFormat(String)

The following code snippet shows you how to detecting file formats.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-DetectDifferentFileFormats-DetectDifferentFileFormats.cs" >}}
## **Loading a Message with Load Options**
The following code snippet shows you how to load a message with load options.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-LoadMessageWithLoadOptions-LoadMessageWithLoadOptions.cs" >}}
### **Preserving Embedded Message Format during Loading**
{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-PreserveEmbeddedMSGFormatDuringLoad-PreserveEmbeddedMSGFormatDuringLoad.cs" >}}
## **Saving and Converting Messages**
Aspose.Email makes it easy to convert any message type to another format. To demonstrate this feature, the code in this article loads three types of messages from disk and saves them back in other formats. The base class SaveOptions and the classes EmlSaveOptions, MsgSaveOptions, MhtSaveOptions, HtmlSaveOptions for additional settings when saving MailMessage can be used for saving messages to other formats. The article shows how to use these classes to save a sample email as:

- EML format.
- Outlook MSG.
- MHTML format.
- HTML format.
### **Loading EML and Saving as EML**
The following code snippet shows you how to loads an EML message and saves it to the disc in the same format.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-LoadAndSaveFileAsEML-LoadAndSaveFileAsEML.cs" >}}
### **Loading EML and Saving as EML Preserving the Original Boundaries**
The following code snippet shows you how to loading EML and saving as EML preserving the original boundaries.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-PreserveOriginalBoundaries-PreservOriginalBoundaries.cs" >}}
### **Saving as EML Preserving TNEF Attachments**
The following code snippet shows you how to saving as EML preserving TNEF attachments.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-PreserveTNEFAttachment-PreserveTNEFAttachment.cs" >}}
### **Loading EML, Saving to MSG**
The following code snippet shows you how to loads an EML message and converts it to MSG using the appropriate option from SaveOptions.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-LoadingEMLAndSavingToMSG-LoadingEMLAndSavingToMSG.cs" >}}
### **Saving as MSG with Preserved Dates**
The MsgSaveOptions class allows you to save the source message as an Outlook Message file (MSG) preserving dates. The following code snippet shows you how to Saving as MSG with Preserved Dates.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-SavingMSGWithPreservedDates-SavingMSGWithPreservedDates.cs" >}}
### **Saving MailMessage as MHTML**
Different options of MHTML can be used to obtain the desired results. The following code snippet shows you how to loads an EML message into MailMessage and converts it to MHTML.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-SaveMailMessageAsMHTML-SaveMailMessageAsMHTML.cs" >}}
#### **Converting to MHTML with Optional Settings**
The MhtSaveOptions class provides additional options for saving email messages to MHTML format. The enumerator MhtFormatOptions makes it possible to write additional email information to the output MHTML. The following additional fields can be written:

- WriteHeader – writes the email header to the output file.
- WriteOutlineAttachments – writes outline attachments to the output file.
- WriteCompleteEmailAddressToMht – writes complete email address to the output file.
- WriteCompleteEmailAddress – writes complete email address to the output file.
- HideExtraPrintHeader – hides extra print header from the top of output file.
- WriteCompleteToEmailAddressToMht – writes the complete recipient email address to the output file.
- WriteCompleteFromEmailAddressToMht – writes the complete sender email address to the output file.
- WriteCompleteCcEmailAddressToMht – writes the complete email addresses of any carbon-copied recipients to the output file.
- WriteCompleteBccEmailAddressToMht – writes the complete email address of any blind carbon-copied recipients to the output file.

The following code snippet shows you how to converting eml file to MHTML with optional settings.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-ConvertMHTMLWithOptionalSettings-ConvertMHTMLWithOptionalSettings.cs" >}}
#### **Rendering Calendar Events while Converting to MHTML**
The MhtFormatOptions.RenderCalendarEvent renders the Calendar events to the output MTHML. Furthermore, the formatting of the output MHTML can be controlled by various properties available as part of MhtMessageFormatter class. The following options are available to format the calendar event output to MHTML, 

- MhtMessageFormatter.StartFormat - Gets or sets the Start format.
- MhtMessageFormatter.EndFormat - Gets or sets the End format.
- MhtMessageFormatter.ShowTimeAsFormat - Gets or sets the ShowTimeAs format.
- MhtMessageFormatter.RecurrenceFormat - Gets or sets the Recurrence format.
- MhtMessageFormatter.RecurrencePatternFormat - Gets or sets the RecurrencePattern format.
- MhtMessageFormatter.OrganizerFormat - Gets or sets the Organizer format.
- MhtMessageFormatter.RequiredAttendeesFormat - Gets or sets the RequiredAttendees format.

The following code snippet shows you how to render calendar events while converting to MHTML.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-RenderingCalendarEvents-RenderingCalendarEvents.cs" >}}
#### **Exporting Email to MHT without Inline Images**
{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-ConvertMHTMLWithOptionalSettings-ConvertToMHTMLWithoutInlineImages.cs" >}}
#### **Exporting Email to MHT with customized TimeZone**
MailMessage class provides the TimeZoneOffset property to set customized Timezone while exporting to MHT. The following code snippet shows you how to export an email to MHT with customized TimeZone.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-ExportEmailToMHTWithCustomTimezone-ExportEmailToMHTWithCustomTimezone.cs" >}}
### **Exporting Email to EML**
The following code snippet shows you how to export email to eml.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-ExportEmailToEML-ExportEmailToEML.cs" >}}
### **Saving Message as HTML**
The HtmlSaveOptions class allows you to export the message body to HTML with the option to save embedded resources. The following code snippet shows you how to Saving Message as HTML where the default value of EmbedResources is true.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-SaveMessageAsHTML-SaveMessageAsHTML.cs" >}}
#### **Saving as HTML without Embedding Resources**
{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-SaveMessageAsHTML-SaveAsHtmlWithoutEmbeddingResources.cs" >}}
### **Saving Message as Outlook Template (.oft) file**
The following code snippet shows you how to save message as outlook template (.oft) file.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-SaveMessageAsOFT-SaveMessageAsOFT.cs" >}}
