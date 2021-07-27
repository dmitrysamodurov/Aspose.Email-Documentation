---
title: Loading and Saving Message
type: docs
weight: 40
url: /java/loading-and-saving-message/
---

## **Detecting File Formats**
Aspose.Email API provides the capability to detect the file format of the provided message file. The DetectFileFormat method of [FileFormatUtil](https://apireference.aspose.com/java/email/com.aspose.email/fileformatutil) class can be used to achieve this.

The following classes and methods can be used to detect the loaded file format.

- Class [Aspose.Email.FileFormatType](https://apireference.aspose.com/java/email/com.aspose.email/fileformattype)
- Class [Aspose.Email.FileFormatInfo](https://apireference.aspose.com/java/email/com.aspose.email/fileformatinfo)
- Class [Aspose.Email.FileFormatUtil](https://apireference.aspose.com/java/email/com.aspose.email/fileformatutil)
- Method [Aspose.Email.FileFormatUtil.detectFileFormat(Stream)](https://apireference.aspose.com/java/email/com.aspose.email/FileFormatUtil#detectFileFormat\(java.io.InputStream\))
- Method [Aspose.Email.FileFormatUtil.detectFileFormat(String)](https://apireference.aspose.com/java/email/com.aspose.email/FileFormatUtil#detectFileFormat\(java.lang.String\))



{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-DetectingFileFormat-.java" >}}
## **Loading a Message with Load Options**
To load a message with specific load options, Aspose.Email provides the [LoadOptions](https://apireference.aspose.com/java/email/com.aspose.email/loadoptions) class that can be used as follow:



{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-LoadingAMessageWithLoadOptions-.java" >}}
### **Preserving Embedded Message Format during Loading**
{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-PreservingEmbeddedMessageFormatduringLoading-PreservingEmbeddedMessageFormatduringLoading.java" >}}
## **Saving and Converting Messages**
Aspose.Email makes it easy to convert any message type to another format. To demonstrate this feature, the code in this article loads three types of messages from disk and saves them back in other formats. The base class [SaveOptions](https://apireference.aspose.com/java/email/com.aspose.email/saveoptions) and the classes [EmlSaveOptions](https://apireference.aspose.com/java/email/com.aspose.email/emlsaveoptions), [MsgSaveOptions](https://apireference.aspose.com/java/email/com.aspose.email/msgsaveoptions), [MhtSaveOptions](https://apireference.aspose.com/java/email/com.aspose.email/mhtsaveoptions), [HtmlSaveOptions](https://apireference.aspose.com/java/email/com.aspose.email/htmlsaveoptions) for additional settings when saving [MailMessage](https://apireference.aspose.com/java/email/com.aspose.email/mailmessage) can be used for saving messages to other formats. The article shows how to use these classes to save a sample email as EML format, Outlook MSG, MHTML format and HTML format. It also shows how to preserve the original email address.
### **Loading EML and Saving as EML**
{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-LoadingEMLAndSavingAsEML.java" >}}
### **Loading EML and Saving as EML Preserving the Original Boundaries**
{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-LoadingAndSavingAsEMLPreservingTheOriginalBoundaries.java" >}}
### **Saving as EML Preserving TNEF Attachments**
{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-SavingAsEMLPreservingTNEFAttachments.java" >}}
### **Loading EML, Saving to MSG**
{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-LoadingEMLSavingToMSG.java" >}}
### **Saving as MSG with Preserved Dates**
{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-SavingAsMSGWithPreservedDates.java" >}}
### **Saving MailMessage as MHTML**
The following code sample loads an EML message into MailMessage and converts it to MHTML. Different options of MHTML can be used to obtain the desired results.

{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-SavingMailMessageAsMHTML.java" >}}
#### **Converting to MHTML with Optional Settings**
The [MhtSaveOptions](https://apireference.aspose.com/java/email/com.aspose.email/mhtsaveoptions) class provides additional options for saving email messages to MHTML format. The enumerator [MhtFormatOptions](https://apireference.aspose.com/java/email/com.aspose.email/mhtformatoptions) makes it possible to write additional email information to the output MHTML. The following additional fields can be written:

**WriteHeader** – writes the email header to the output file.
**WriteOutlineAttachments** – writes outline attachments to the output file.
**WriteCompleteEmailAddressToMht** – writes the complete email address to the output file.
**WriteCompleteEmailAddress** – writes the complete email address to the output file.
**HideExtraPrintHeader** – hides extra print header from the top of the output file.
**WriteCompleteToEmailAddressToMht** – writes the complete recipient email address to the output file.
**WriteCompleteFromEmailAddressToMht** – writes the complete sender email address to the output file.
**WriteCompleteCcEmailAddressToMht** – writes the complete email addresses of any carbon-copied recipients to the output file.
**WriteCompleteBccEmailAddressToMht** – writes the complete email address of any blind carbon-copied recipients to the output file.

{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-ConvertingToMHTMLWithOptionalSettings.java" >}}
#### **Rendering Calendar Events while Converting to MHTML**
Aspose.Email API can render calendar events to the output MHTML file using the [MhtFormatOptions](https://apireference.aspose.com/java/email/com.aspose.email/mhtformatoptions) Enumeration.

{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-RenderingCalendarEvents-RenderingCalendarEvents.java" >}}
#### **Exporting Email to MHT without Inline Images**
Aspose.Email API can render calendar events to the output MHTML file using the [MhtFormatOptions](https://apireference.aspose.com/java/email/com.aspose.email/mhtformatoptions) Enumeration.

{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-ConvertToMHTMLWithoutInlineImages.java" >}}
#### **Exporting Email to MHT with customized TimeZone**
[MailMessage](https://apireference.aspose.com/java/email/com.aspose.email/mailmessage) class provides the [setTimeZoneOffset](https://apireference.aspose.com/java/email/com.aspose.email/MailMessage#setTimeZoneOffset\(double\)) method to set customized Timezone while exporting to MHT. The following code snippet shows you how to export the email to MHT with customized TimeZone.


~~~java
MailMessage msg = MailMessage.load(filename, new MsgLoadOptions());
msg.setDate(new Date());

// Set the timezone offset in milliseconds
msg.setTimeZoneOffset(5*60*60*1000);

MhtSaveOptions mhtOptions = new MhtSaveOptions();
mhtOptions.setMhtFormatOptions(MhtFormatOptions.WriteHeader);
msg.save(dataDir + "ExportToMHTWithCustomTimezone_out.mhtml", mhtOptions);
~~~
### **Exporting Email to EML**
The following code snippet shows you how to export emails to EML.

{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ExportingEmailToEML-ExportingEmailToEML.java" >}}
### **Saving Message as HTML**
The [HtmlSaveOptions](https://apireference.aspose.com/java/email/com.aspose.email/htmlsaveoptions) class allows you to export the message body to HTML with the option to save embedded resources. The following code sample shows how to achieve this where the default value of EmbedResources is true.

{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-SavingMessageAsHTML.java" >}}
#### **Saving as HTML without Embedding Resources**
{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-ConvertEmailMessages-SavingasHTMLwithoutEmbeddingResources.java" >}}
### **Saving Message as Outlook Template (.oft) file**
The following code snippet shows you how to save a message as an outlook template (.oft) file.

{{< gist "aspose-com-gists" "709d733586ce50505c3bca3f6e8bd18d" "Examples-src-main-java-com-aspose-email-examples-email-SaveMessageAsOFT-SaveMessageAsOFT.java" >}}
