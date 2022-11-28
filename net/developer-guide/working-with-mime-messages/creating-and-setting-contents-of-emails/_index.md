---
title: Creating and Setting Contents of Emails in .NET
linktitle: Creating and setting contents of Emails
type: docs
weight: 10
url: /net/creating-and-setting-contents-of-emails/
---

## Overview

This article discusses how to create and set contents of emails using C# .NET. It covers the following topics.

_Category_: **Create Email**
- [C# Create an email message](#csharp-create-email-message)
- [C# Create an EML email message](#csharp-create-email-eml)
- [C# Create an Apple EML email message](#csharp-create-email-apple-eml)
- [C# Create MSG Unicode email message](#csharp-create-email-msg-unicode)

_Category_: **Email Contents**
- [C# Specify Multiple Recipients of Email](#csharp-specify-multiple-recipients-of-email)
- [C# Change Email Addresses to Friendly Names](#csharp-change-email-addresses-to-friendly-names)
- [C# Set Email HTML Body](#csharp-set-email-html-body)
- [C# Set Email Alternate Text](#csharp-set-email-alternate-text)

_Category_: **Email Body Encoding**
- [C# Specify Email Body Encoding in ANSI Code Page](#csharp-specify-email-body-encoding-in-ansi)
- [C# Specify Email Body Encoding in ASCII](#csharp-specify-email-body-encoding-in-ascii)
- [C# Specify Email Body Encoding in UTF-8](#csharp-specify-email-body-encoding-in-utf-8)

_Category_: **Send Email**
- [C# Send Email to Multiple Recipients](#csharp-send-email-to-multiple-recipients)
- [C$ Send Email after Changing Email Addresses to Friendly Names](#csharp-send-email-after-changing-email-addresses-to-friendly-names)

Other topics covered by this article.
- [See Also](#see-also)

## **Create New Email Message**

The [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class represents an email message and allows developers to create a new email message. Basic email properties like From, To, Subject and body can be easily attached to the newly created mail message. Similarly, we can save the mail message into different formats like EML, MSG, and MHTML.

_Steps: Create New Email_
- <a name="csharp-create-email-message" id="csharp-create-email-message"><strong>_Steps:_ Create an email message in C#</strong></a>
- <a name="csharp-create-email-eml" id="csharp-create-email-eml"><strong>_Steps:_ Create an EML email message in C#</strong></a>
- <a name="csharp-create-email-apple-eml" id="csharp-create-email-apple-eml"><strong>_Steps:_ Create an Apple EML email message in C#</strong></a>
- <a name="csharp-create-email-msg-unicode" id="csharp-create-email-msg-unicode"><strong>_Steps:_ Create MSG Unicode email message in C#</strong></a>

_Code Steps:_
1. Create an instance of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class.
2. Set mail message properties.
3. Save the mail message in different formats e.g.
   1. **EML** using [SaveOptions.DefaultEml](https://reference.aspose.com/email/net/aspose.email/saveoptions/defaulteml/)
   2. **EmlxFormat** (_Apple Email_) using [CreateSaveOptions](https://reference.aspose.com/email/net/aspose.email/saveoptions/) method.
   3. **MSG Unicode** using [SaveOptions.DefaultMsgUnicode](https://reference.aspose.com/email/net/aspose.email/saveoptions/defaultmsgunicode/)
   4. **MHTML** using [SaveOptions.DefaultMhtml](https://reference.aspose.com/email/net/aspose.email/saveoptions/defaultmhtml/)

The following code snippet shows you how to create a new email with different properties.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-CreateNewMailMessage-CreateNewMailMessage.cs" >}}

## **Specifying Multiple Recipients**

The [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) represents an email message. Instances of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class are used to construct email messages that are transmitted to an SMTP server using the [SmtpClient](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient) class. This topic demonstrates how to specify more than one email address. Email addresses can be specified using the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class. The email addresses used in the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class are:

- **To** - Recipient addresses can be specified in the 'To' field. The 'To' field recipients are the primary message audience. There can be more than one recipient address
- **Cc** - Cc stands for "carbon copy", or "courtesy copy", and lets you add email recipients who need to see the email but who are not necessarily expected to act on it. Managers, for example, or members of your team who need to be aware of a conversation. With Aspose.Email, Cc addresses can be specified in your code. This way, automated emails, or all emails to a specific address, can be copied to relevant personnel.
- **Bcc** -  Where a Cc appears in the email information that the main recipients see, a Bcc doesn't. It is meant for hidden notification. 

To specify multiple email addresses in an email message, follow these steps:

<a name="csharp-specify-multiple-recipients-of-email" id="csharp-specify-multiple-recipients-of-email"><strong>_Steps:_ Specify Multiple Recipients of Email using C#</strong></a> |
<a name="csharp-send-email-to-multiple-recipients" id="csharp-send-email-to-multiple-recipients"><strong>_Steps:_ Send Email to Multiple Recipients in C#</strong></a>

1. Create an instance of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class.
2. Specify the From and multiple To, Cc and Bcc addresses using the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) instance.
3. Create an instance of the [SmtpClient](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient) class and send the email using the [Send](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient/methods/send/index) method.

The code sample below shows how multiple To, Cc, and Bcc addresses can be specified.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-SpecifyRecipientAddresses-SpecifyRecipientAddresses.cs" >}}

## **Changing email addresses to a friendly name**

The programming samples below demonstrate how to change email addresses to friendly names in an email message. A friendly name is a name that is more human-friendly than the email address, for example John Smith instead of [js346@domain.com](/email/net/mailto-js346@domain-com/). When sending an email, we can associate a friendly name with an email address in the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class constructor.

To change email addresses to friendly names in an email message, follow these steps:

<a name="csharp-change-email-addresses-to-friendly-names" id="csharp-change-email-addresses-to-friendly-names"><strong>_Steps:_ Change Email Addresses to Friendly Names in C#</strong></a> | 
<a name="csharp-send-email-after-changing-email-addresses-to-friendly-names" id="csharp-send-email-after-changing-email-addresses-to-friendly-names"><strong>_Steps:_ Send Email after Changing Email Addresses to Friendly Names in C#</strong></a>

1. Create an instance of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class and specify email addresses in the **To** and **From** fields along with friendly names.
2. Specify the Cc and Bcc email addresses along with friendly names by calling the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class constructor in the MailMessage instance.
3. Create an instance of the [SmtpClient](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient) class and send the email using the [Send](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient/methods/send/index) method.

The following code snippet shows you how to display Names for email addresses.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-ChangeEmailAddress-ChangeEmailAddress.cs" >}}

## **Set Mail Body**

The [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class represents an email message. Instances of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class are used to construct email messages that are transmitted to an SMTP server for delivery using the [SmtpClient](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient) class. A mail body can be specified using the [Body](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/body) and [HtmlBody](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/htmlbody) properties of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class. The [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class also allows you to add alternate views to the email.

This article shows how to add body and alternate views to the email.

### **Setting HTML Body**

[HtmlBody](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/htmlbody) is used to specify the HTML content of a message body. [HtmlBody](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/htmlbody) must be enclosed between <html> </html> tags. The following code snippet shows you how to set HTML body.

<a name="csharp-set-email-html-body" id="csharp-set-email-html-body"><strong>_Steps:_ Set Email HTML Body in C#</strong></a>

1. Create an instance of [MailMessage](https://reference.aspose.com/email/net/aspose.email/mailmessage/) class.
2. Set email HTML body using [MailMessage.HtmlBody](https://reference.aspose.com/email/net/aspose.email/mailmessage/htmlbody/) property.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-SetHTMLBody-SetHTMLBody.cs" >}}

### **Setting Alternate Text**

Use the [AlternateView](https://apireference.aspose.com/email/net/aspose.email/alternateview) class to specify copies of an email message in different formats. For example, if you send a message in HTML, you might also want to provide a plain text version in case some of the recipients use email readers that cannot display HTML content. This class has two properties, [LinkedResources](https://apireference.aspose.com/email/net/aspose.email/alternateview/properties/linkedresources) and [BaseUri](https://apireference.aspose.com/email/net/aspose.email/alternateview/properties/baseuri), which are used to resolve URLs within the content of the email.

- [LinkedResources](https://apireference.aspose.com/email/net/aspose.email/alternateview/properties/linkedresources) is a collection of [LinkedResource](https://apireference.aspose.com/email/net/aspose.email/linkedresource) objects. When rendered, URLs within the email's content are first matched against the URLs in the Content Link of each [LinkedResource](https://apireference.aspose.com/email/net/aspose.email/linkedresource) object in the [LinkedResources](https://apireference.aspose.com/email/net/aspose.email/alternateview/properties/linkedresources) collection and resolved.
- [BaseUri](https://apireference.aspose.com/email/net/aspose.email/alternateview/properties/baseuri) is used by the mail reader to resolve relative URLs within the body, and also to resolve relative Content Link URLs, in the [LinkedResources](https://apireference.aspose.com/email/net/aspose.email/alternateview/properties/linkedresources) collection.

The following code snippet shows you how to set alternate text.

<a name="csharp-set-email-alternate-text" id="csharp-set-email-alternate-text"><strong>_Steps:_ Set Email Alternate Text in C#</strong></a>

1. Create an instance of [MailMessage](https://reference.aspose.com/email/net/aspose.email/mailmessage/htmlbody/) class.
2. Create [AlternateView](https://reference.aspose.com/email/net/aspose.email/alternateview/createalternateviewfromstring/) to view an email message using the content specified in the string.
3. Add alternate text using **Add** method of [MailMessage.AlternateViews](https://reference.aspose.com/email/net/aspose.email/mailmessage/alternateviews/) collection.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-AlternateText-AlternateText.cs" >}}

## **Specifying Mail Body Encoding**
The content type defines the email content format: the character set, for example. The encoding formats provided in System.Text.Encoding are:

- ASCII: Encoding for the ASCII (7 bit) character set.
- Default: Encoding for the system's current ANSI code page.
- Unicode: Encoding for the Unicode format in little-endian byte order.
- BigEndianUnicode: Encoding for the Unicode format in the big-endian byte order.
- UTF7: Encoding for the UTF-7 format.
- UTF8: Encoding for the UTF-8 format.

Aspose.Email uses the [BodyEncoding](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/bodyencoding) property of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class to specify the email body encoding. To encode the body of an email message, follow the steps given below:

_Steps: Specifying Mail Body Encoding_
- <a name="csharp-specify-email-body-encoding-in-ansi" id="csharp-specify-email-body-encoding-in-ansi"><strong>_Steps:_ Specify Email Body Encoding in ANSI Code Page using C#</strong></a>
- <a name="csharp-specify-email-body-encoding-in-ascii" id="csharp-specify-email-body-encoding-in-ascii"><strong>_Steps:_ Specify Email Body Encoding in ASCII using C#</strong></a>
- <a name="csharp-specify-email-body-encoding-in-unicode" id="csharp-specify-email-body-encoding-in-unicode"><strong>_Steps:_ Specify Email Body Encoding in Unicode using C#</strong></a>
- <a name="csharp-specify-email-body-encoding-in-bigendianunicode" id="csharp-specify-email-body-encoding-in-bigendianunicode"><strong>_Steps:_ Specify Email Body Encoding in BigEndianUnicode using C#</strong></a>
- <a name="csharp-specify-email-body-encoding-in-utf-7" id="csharp-specify-email-body-encoding-in-utf-7"><strong>_Steps:_ Specify Email Body Encoding in UTF-7 using C#</strong></a>
- <a name="csharp-specify-email-body-encoding-in-utf-8" id="csharp-specify-email-body-encoding-in-utf-8"><strong>_Steps:_ Specify Email Body Encoding in UTF-8 using C#</strong></a>
- <a name="csharp-send-email-after-setting-encoding" id="csharp-send-email-after-setting-encoding"><strong>_Steps:_ Send Email after Setting Encoding in C#</strong></a>

_Code Steps:_

1. Create an instance of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class.
1. Specify the sender, receiver and HTML body email in the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) instance.
1. Specify the [BodyEncoding](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/bodyencoding) property value.
1. Create an instance of the [SmtpClient](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient) class and send the email using the [Send](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient/methods/send/index) method.
 


{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-SpecifyMailBodyEncoding-SpecifyMailBodyEncoding.cs" >}}
## **MailMessage Features**
The [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class represents the content of an email message. Instances of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class are used to construct an email message that is transmitted to an SMTP server for delivery using the [SmtpClient](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient) class. This article shows how to use [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class utility features for controlling the following email features:

- **Date and time** - Through the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class [Date](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/date) property we get or set an email's date and time.
- **Message priority** - The [MailPriority](https://apireference.aspose.com/email/net/aspose.email/mailpriority) class specifies priority levels for sending an email message. It can be low, normal or high. Priority influences transmission speed and delivery.
- **Message sensitivity** - The [MailSensitivity](https://apireference.aspose.com/email/net/aspose.email/mailsensitivity) class specifies five levels of sensitivity.
- **Delivery notification** - Delivery notifications let senders know that the email they sent has been delivered to the recipient's inbox.

By default, the date is the actual date that the message was sent, and time is the time it was sent, as displayed by Microsoft Outlook. However, the real email delivery time is added by the SMTP server itself in the mail header. For example, below is a common mail header, where [Date](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/date) sets the field Date.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-DateAndTime-DateAndTime.cs" >}}



The code snippet below illustrates how each of the features discussed above can be used.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-UseMailMessageFeatures-MailMessageFeatures.cs" >}}
## **Requesting a Read Receipt**
The programming samples below show how you can request a read receipt. The [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class [DeliveryNotificationOptions](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/deliverynotificationoptions) Enumeration property describes the delivery notification options for an email. To request a read receipt after sending an email, follow these steps:

1. Create an instance of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class.
1. Specify the sender, receiver and HTML body for the email in the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) instance.
1. Specify the [DeliveryNotificationOptions](https://apireference.aspose.com/email/net/aspose.email/mailmessage/properties/deliverynotificationoptions) in other [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) instances.
1. Create an instance of the [SmtpClient](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient) class and send the email using the [Send](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient/methods/send/index) method.

Read receipt requests may not be always honored because:

- A mail client may not implement that functionality.
- The end-user may have that functionality turned off.
- The end-user may choose not to send one.

The following code snippet shows you how to request a read receipt.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-RequestReadReceipt-RequestReadReceipt.cs" >}}
## **Set Email Headers**
Email headers represent an Internet standard and RFC define header fields which are included in Internet email messages. An email header can be specified using the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class. Common header types are defined in the [HeaderType](https://apireference.aspose.com/email/net/aspose.email/headertype) class. It is a sealed class working as a normal enumeration.

Normally an email header contains these fields:

- To: Recipient addresses can be specified in the **To** field. The **To** field recipients are the message's primary audience. There can be more than one recipient addresses.
- From: This field presents the email address of the message sender.
- Cc: Allows users to send a message as a "Carbon Copy" or "Courtesy Copy". That is, the receiver is not expected to reply or act. Typically, supervisory personnel are notified with CC.
- Bcc: It stands for Blind Carbon Copy, which lets you send an email to a recipient that is hidden from other recipients.
- ReplyTo: This header field is meant to indicate where the sender wants replies to go.
- Subject: Title, heading, subject. Often used as a thread indicator for messages replying to or commenting on other messages.
- Date: This header specifies a date (and time). Normally this is the date at which the message was composed and sent.
- XMailer: Information about the client software of the originator. Example: X-Mailer: Aspose.Email
  XMailer is used by mail clients. Different mail clients will have different XMailer values. MS Outlook's XMailer value is Microsoft Office Outlook, Build 11.0.5510. It is ignored by the email receiver or email reader.

Normally, an email header looks something like this:

``` cs

 Reply-To: reply@reply.com

From: sender@sender.com

To: guangzhou@guangzhoo.com

Subject: test mail

Date: 6 Mar 2006 8:2:2 +0800

X-Mailer: Aspose.Email

```

To customize an email header, follow these steps:

- Create an instance of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class.
- Specify To, From, Cc, Bcc, ReplyTo, Subject, Date & XMailer using an instance of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage).
- Create an instance of the [MimeHeader](https://apireference.aspose.com/email/net/aspose.email.mime/mimeheader) class and specify the secret header.
- Add the secret header to the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) instance.

The following code snippet shows you how to set email headers.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-SetEmailHeaders-SetEmailHeaders.cs" >}}



The above code snippet produces an email header in the following format. This can be observed by opening the resultant file "MsgHeaders.msg" in Microsoft Outlook and then view the Properties.

``` cs

 Reply-To: reply@reply.com

From: sender@sender.com

To: receiver1@receiver.com

CC: receiver2@receiver.com

BCC: receiver3@receiver.com

Subject: test mail

Date: 6 Mar 2006 8:2:2 +0800

X-Mailer: Aspose.Email

secret-header: mystery

```
### **Insert Header at Specific Location**
The [Add](https://apireference.aspose.com/email/net/aspose.email.mime/headercollection/methods/add/index) method of [HeadersCollection](https://apireference.aspose.com/email/net/aspose.email.mime/headercollection) class inserts the header at the end of the collection. However, it may sometimes be necessary to insert a header at a specific location. In such a case, the [Add](https://apireference.aspose.com/email/net/aspose.email.mime/headercollection/methods/add/index) method won't be of help. To achieve this, use the [Insert](https://apireference.aspose.com/email/net/aspose.email.mime/headercollection/methods/insert) method of the [HeadersCollection](https://apireference.aspose.com/email/net/aspose.email.mime/headercollection). If the collection contains headers with the same name, this header will be inserted before other headers with the same name. The following code snippet shows you how to insert header at a specific location.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-InsertHeaderAtSpecificLocation.cs" >}}
### **Adding Custom headers to email**
The programming samples below demonstrates how to specify a custom header in an email message. An email header can be specified using the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class. To specify a custom header in an email message, please follow these steps:

1. Create an instance of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class.
1. Specify the to, from and subject values using the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) instance.
1. Add the secret header into the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) instance.
1. Create an instance of the [SmtpClient](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient) class and send the email using the [Send](https://apireference.aspose.com/email/net/aspose.email.clients.smtp/smtpclient/methods/send/index) method.

The following code snippet shows you how to add custom headers to email.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-SpecifyCustomHeader-SpecifyCustomHeader.cs" >}}
## **Sign Emails with DKIM**
Aspose.Email allows signing Email with DKIM (DomainKeys Identified Mail). This lets an organization take responsibility for a message that is in transit ([More Info](http://www.dkim.org)). DKIM adds a digital signature to the email message headers that can be validated by recipients. The public key of the sender enables the receiver to verify that the signature matches the message's contents. The [DKIMSign](https://apireference.aspose.com/email/net/aspose.email/mailmessage/methods/dkimsign) method of the [MailMessage](https://apireference.aspose.com/email/net/aspose.email/mailmessage) class is used to set the cryptographic and signature information for signing the message. The following code snippet shows you how to sign emails with DKIM.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-SignEmailsWithDKIM-SignEmailsWithDKIM.cs" >}}

## See Also

This article also covers these topics. The codes are same as above.

_Category_: **Email Body Encoding**
- [C# Specify Email Body Encoding in Unicode](#csharp-specify-email-body-encoding-in-unicode)
- [C# Specify Email Body Encoding in BigEndianUnicode](#csharp-specify-email-body-encoding-in-bigendianunicode)
- [C# Specify Email Body Encoding in UTF-7](#csharp-specify-email-body-encoding-in-utf-7)

_Category_: **Send Email**
- [C# Send Email after Setting Encoding](#csharp-send-email-after-setting-encoding)
