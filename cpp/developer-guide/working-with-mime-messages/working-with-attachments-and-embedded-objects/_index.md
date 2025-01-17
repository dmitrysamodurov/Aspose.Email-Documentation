---
title: Working with Attachments and Embedded Objects using C++ Email Parser Library
ArticleTitle: Working with Attachments and Embedded Objects using C++ Email Parser Library
linktitle: Working with Attachments and Embedded Objects
type: docs
weight: 50
url: /cpp/working-with-attachments-and-embedded-objects/
description: You can add and remove email attachments, display the attachment file name, and work with embedded objects using the C++ Email Parser Library API.
---

## **Managing Email Attachments**
An email attachment is a computer file which is sent along with an email message. The file may be sent as a separate message as well as a part of the message to which it is attached. The Attachment class is used with the MailMessage class class. All messages include a body. In addition to the body, you might want to send additional files. These are sent as attachments and are represented as instance of the Attachment class. You can send any number of attachments but the size of the attachment is limited by the mail server. Gmail, for example, does not support file sizes greater than 10MB.
{{% alert %}}
**Try it out!**

Add or remove email attachments with the free [**Aspose.Email Editor App**](https://products.aspose.app/email/editor).
{{% /alert %}}
### **Adding Attachment**
To attach an attachment to an email, please follow these steps:

1. Create an instance of the MailMessage class class.
1. Create an instance of the Attachment class.
1. Load attachment into the Attachment instance.
1. Add the Attachment instance into the MailMessage class instance.

The following code snippet shows you how to add an attachment to an email.

{{< gist "aspose-email" "ef0db907527892c88c557bb418093cee" "Examples-EmailCPP-Email-AddEmailAttachments-AddEmailAttachments.cpp" >}}

Above, we described how to add attachments to your email message with Aspose.Email. What follows shows how to remove attachments, and display information about them on screen.

### **Removing an Attachment**
To remove an attachment, follow the steps given below:

- Create an instance of Attachment class.
- Load attachment in the instance of Attachment class.
- Add attachment to the instance of MailMessage class.
- Remove the attachments from the instance of Attachment class using MailMessage class instance.

The following code snippet shows you how to remove an attachment.

{{< gist "aspose-email" "ef0db907527892c88c557bb418093cee" "Examples-EmailCPP-Email-RemoveAttachments-RemoveAttachments.cpp" >}}

### **Displaying Attachment File Name**
To display the attachment file name, follow these steps:

1. Loop through the attachments in the email message and
   1. Save each attachment.
   1. Display each attachment's name on screen.

The following code snippet shows you how to display an attachment file name on the screen.

{{< gist "aspose-email" "ef0db907527892c88c557bb418093cee" "Examples-EmailCPP-Email-DisplayAttachmentFileName-DisplayAttachmentFileName.cpp" >}}

### **Extracting Email Attachments**
This topic explains how to extract an attachment from an email file. An email attachment is a computer file which is sent along with an email message. The file may be sent as a separate message as well as a part of the message to which it is attached. All emails messages includes a body. As well as the body, you might want to send additional files. These are sent as attachments and are represented as instances of the Attachment class. The Attachment class is used with the MailMessage class to work with attachments. To extract attachments from an email message, follow these steps:

- Create an instance of the MailMessage class.
- Load an email file into the MailMessage instance.
- Create an instance of the Attachment class and use it in a loop to extract all attachments.
- Save the attachment and display it on screen.
- Specify sender and recepient address in the MailMessage instance.
- The code snippets extract attachments from an email.

|**Extracted attachments in email**|
| :- |
|![todo:image_alt_text](working-with-attachments-and-embedded-objects_1.png)|
The following code snippet shows you how to Extracting Email Attachments.



{{< gist "aspose-email" "ef0db907527892c88c557bb418093cee" "Examples-EmailCPP-Email-ExtractEmbeddedObjectsFromEmail-ExtractEmbeddedObjectsFromEmail.cpp" >}}
#### **Retrieving Content-Description from Attachment**
Aspose.Email API provides the capability to read attachment's Content-Description from attachment header. The following code snippet shows you how to retrieving content description from attachment.



{{< gist "aspose-email" "ef0db907527892c88c557bb418093cee" "Examples-EmailCPP-Email-RetrieveContentDescriptionFromAttachment-RetrieveContentDescriptionFromAttachment.cpp" >}}
## **Working with Embedded Objects**
An embedded object is an object that was created with one application an enclosed within a document or file created by another application. For example, a Microsoft Excel spreadsheet can be embedded into a Microsoft Word report, or a video file can be embedded into a Microsoft PowerPoint presentation. When a file is embedded, rather than inserted or pasted into another document, it retains its original format. The embedded document can be opened in the original application and modified.
### **Embedding Objects into an Email**
The LinkedResources class is used with MailMessage class to embed objects in your email messages. To add an embedded object, follow these steps

1. Create an instance of the MailMessage class.
1. Specify the from, to and subject values in MailMessage instance.
1. Create an instance of the AlternateView class.
1. Create an instance of the LinkedResources class.
1. Load an embedded object into the LinkedResources instance.
1. Add the loaded embedded object into the MailMessage class instance.
1. Add the AlternateViews instance to the MailMessage class instance.

The code snippets below produce an email message with both plain text and HTML bodies and an image embedded into the HTML

|**Image embedded into email**|
| :- |
|![todo:image_alt_text](/plugins/servlet/confluence/placeholder/unknown-attachment)|
You can send any number of embedded objects. The size of the attachment is limited by the mail server. Gmail, for example, does not support file sizes greater then 10MB. The code snippets below shows how to embed objects into an Email.



{{< gist "aspose-email" "ef0db907527892c88c557bb418093cee" "Examples-EmailCPP-Email-EmbeddedObjects-EmbeddedObjects.cpp" >}}
### **Extracting Embedded Objects**
This topic explains how to extract embedded objects from an email file. An embedded object is an object that was created with one application an enclosed within a document or file created by another application. For example, a Microsoft Excel spreadsheet can be embedded into a Microsoft Word report, or a video file can be embedded into a Microsoft PowerPoint presentation. When a file is embedded, rather than inserted or pasted into another document, it retains its original format. The embedded document can be opened in the original application and modified.To extract an embedded object from an email message, follow these steps:

1. Create an instance of the MailMessage class.
1. Load an email file in the MailMessage instance.
1. Create a loop and create an instance of the Attachment class in it.
1. Save the attachment and display it on screen.
1. Specify sender and recepient address in the MailMessage instance.
1. The code snippet below extract embedded objects from an email.

|**Extracted embedded objects in email**|
| :- |
|![todo:image_alt_text](working-with-attachments-and-embedded-objects_2.png)|
The following code snippet shows you how to Extracting Embedded Objects.



{{< gist "aspose-email" "ef0db907527892c88c557bb418093cee" "Examples-EmailCPP-Email-ExtractEmbeddedObjectsFromEmail-ExtractEmbeddedObjectsFromEmail.cpp" >}}
