---
title: Adding Attachments and HTML Text to Outlook MSG File
type: docs
weight: 30
url: /net/adding-attachments-and-html-text-to-outlook-msg-file/
---


{{% alert color="primary" %}} 

Our migration tips show how Aspose products can be used to improve your applications and free you from dependency on traditional automation.

This migration tip shows how to create an MSG file with HTML formatted body and add multiple attachments to it:

- A section of VBA code that uses [Microsoft Office Automation](#office-automation) to create the MSG file with attachments and HTML body.
- The same thing accomplished using [Aspose.Email for .NET](#asposeemail-for-net), in both C# and VB.NET.

{{% /alert %}} 
## **Office Automation**
Using this method, Microsoft Outlook must be installed on the machine where the VBA code runs. The code snippet below creates an Outlook MSG file with attachments and HTML body.

**VBA**

``` cs

 ' Create an object of type Outlook.Application

Set objOutlookApplication = CreateObject("Outlook.Application")

' Create an object of type olMailItem

Set objMsg = objOutlookApplication.CreateItem(olMailItem)

' Set properties of the message file e.g. subject, body and to address

' Set subject

objMsg.Subject = "This MSG file is created using Office Automation."

' Set to (recipient) address

objMsg.To = "to@domain.com"

' Set body of the email message

objMsg.HTMLBody = "<html><p>This MSG file is created using VBA code.</p>"

' Add attachments to the message

objMsg.Attachments.Add "C:\test.bmp"

objMsg.Attachments.Add "C:\test2.jpg"

' Save as Outlook MSG file

objMsg.SaveAs ("c:\testvba.msg")

' Open the MSG file

objMsg.Display



```
## **Aspose.Email for .NET**
The code snippet below uses Aspose.Email for .NET library to create an MSG file, similar to [the one created above](#office-automation), with multiple attachments and HTML body. Since Aspose.Email for .NET is purely written in .NET, COM interop is not required. Also, Microsoft Outlook 2003/2007 does not have to be installed on the machine. The method described below is suitable when Microsoft Outlook is not installed or when you want to generate MSG files on a server.

The code snippets below show how to perform the same task in C# and VB.NET using Aspose.Email for .NET.

**C#**

``` cs

 // Create an instance of type MailMessage

MailMessage msg = new MailMessage();

// Set properties of message like subject, to and HTML body

// Set subject

msg.Subject = "This MSG file is created using Aspose.Email for .NET";

// Set from (sender) address

msg.Sender = new MailAddress("from@domain.com", "From Name");

// Set to (recipient) address and name

msg.To.Add(new MailAddress("to@domain.com", "To Name"));

// Set HTML body of the email message

msg.HtmlBody = @"<html><p>This MSG file is created using C# code.</p>" +

    "<p>Microsoft Outlook does not need to be installed on the machine running this code.</p>" +

    "<p>This method is suitable for creating MSG files on the server side.</html>";



// Add attachments to the message file

msg.Attachments.Add(new Attachment(@"C:\test.bmp"));

msg.Attachments.Add(new Attachment(@"C:\test2.jpg"));

// Save as Outlook MSG file

string strSaveFile = @"C:\TestAspose.msg";

msg.Save(strSaveFile, MessageFormat.Msg);



```
