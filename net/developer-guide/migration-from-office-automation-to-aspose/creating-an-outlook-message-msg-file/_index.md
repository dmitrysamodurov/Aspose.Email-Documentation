---
title: Creating an Outlook Message (MSG) File
type: docs
weight: 20
url: /net/creating-an-outlook-message-msg-file/
---


{{% alert color="primary" %}} 

Our migration tips show how Aspose products can be used to improve your applications and free you from dependency on traditional automation.

This migration tip shows how to create an Outlook Message (MSG) file using [Microsoft Office Automation](#office-automation) and [Aspose.Email](#asposeemail-for-net). The code samples set the MSG file's basic properties - To, Cc, Subject, and HTML body - before saving the file to disk.

{{% /alert %}} 
## **Office Automation**
To use Office Automation, Microsoft Outlook must be installed on the machine that the code runs on. A reference to Outlook.interop.dll is also required.
### **Programming Samples**
The following code snippets create an MSG file using Office Automation.

**C#**

``` cs

 // Creates a new Outlook Application instance

Outlook.Application objOutlook = new Outlook.Application();

// Creating a new Outlook message from the Outlook Application instance

Outlook.MailItem msgInterop = (Outlook.MailItem)(objOutlook.CreateItem(Outlook.OlItemType.olMailItem));

// Set recipient information

msgInterop.To = "to@domain.com";

msgInterop.CC = "cc@domain.com";

// Set the message subject

msgInterop.Subject = "Subject";

// Set some HTML text in the HTML body

msgInterop.HTMLBody = "<h3>HTML Heading 3</h3> <u>This is underlined text</u>";

// Save the MSG file in local disk

string strMsg = @"c:\\temp\TestInterop.msg";

msgInterop.SaveAs(strMsg, Outlook.OlSaveAsType.olMSG);



```
## **Aspose.Email for .NET**
The samples below use Aspose.Email to create the Outlook MSG file. It's written in pure .NET and does not use COM Interop. Outlook installation is not required for creating the msg file this way.

**C#**

``` cs

 // Create an instance of the Aspose.Email.MailMessage class

MailMessage msg = new MailMessage();

// Set recipients information

msg.To = "to@domain.com";

msg.CC = "cc@domain.com";

// Set the subject

msg.Subject = "Subject";

// Set HTML body

msg.HtmlBody = "<h3>HTML Heading 3</h3> <u>This is underlined text</u>";

// Add an attachment

msg.Attachments.Add(new Attachment("test.txt"));

// Save it in local disk

string strMsg = @"c:\ TestAspose.msg";

msg.Save(strMsg, MessageFormat.Msg);



```
