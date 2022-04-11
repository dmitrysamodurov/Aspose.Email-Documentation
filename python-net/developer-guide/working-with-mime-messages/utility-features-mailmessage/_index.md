---
title: Utility Features - MailMessage
type: docs
weight: 40
url: /python-net/utility-features-mailmessage/
---


## **MailMessages Containing TNEF attachments**
Transport Neutral Encapsulation Format (TNEF) is a proprietary email attachment format used by Microsoft Outlook and Microsoft Exchange Server. The Aspose.Email API allows you to read email messages that have TNEF attachments and modify the contents of the attachment. The email can then be saved as normal email or to the same format, preserving TNEF attachments. This article shows different code samples for working with messages containing TNEF attachments. This article also shows working with creating TNEF EML files from Outlook MSG files.
### **Reading Message by Preserving TNEF Attachments**
The following code snippet shows you how to reading message by preserving TNEF attachments.



{{< gist "aspose-email" "159e15fa1d340cec2fb7" "Examples-CSharp-Email-ReadMessageByPreservingTNEFAttachments-ReadMessageByPreservingTNEFAttachments.cs" >}}
### **Updating Resources in a TNEF Attachment and Preserving TNEF Format**
The following code snippet shows you how to updating resources in a TNEF attachment and preserving TNEF format.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-UpdateTNEFAttachments-UpdateTNEFAttachments.cs" >}}
### **Adding New Attachments to Main Message Containing TNEF**
The following code snippet shows you how to adding new attachments to main message containing TNEF.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-AddNewAttachments-AddNewAttachments.cs" >}}
### **Creating TNEF EML from MSG**
Outlook MSGs sometimes contain information such as tables and text styles that may get disturb if these are converted to EML. Creating TNEF messages from such MSG files allows to retain the formatting and even send such messages via the email clients retaining the formatting. The InterpretAsTnef property is used to achieve this. The following code snippet shows you how to creating TNEF eML from MSG.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-CreateTNEFEMLFromMSG-CreateTNEFEMLFromMSG.cs" >}}



For creating the TNEF, the following sample code can be used.



{{< gist "aspose-email" "159e15fa1d340cec2fb7" "Examples-CSharp-Email-CreateTNEF-CreateTNEF.cs" >}}
### **Detect If a Message is TNEF**
The following code snippet shows you how to detect If a message is TNEF.



{{< gist "aspose-email" "159e15fa1d340cec2fb7" "Examples-CSharp-Email-DetectMessageIsTNEF-DetectMessageIsTNEF.cs" >}}
## **Processing of Bounced Messages**
It is very common that a message sent to a recipient may bounce for any reason such as invalid recipient address. Aspose.Email API has the capability to process such a message for checking if it is a bounced email or a regular email message. The  MailMesage's CheckBounced method returns a valid result if the email message is a bounced email. This article shows the usage of BounceResult class that provides the capability of checking if a message is a bounced email. It further gives detailed information about the recipients, action taken and the reason about the notification. The following code snippet shows you how to process bounced messages.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-CheckBouncedMessage-CheckBouncedMessage.cs" >}}
## **Bayesian Spam Analyzer**
Aspose.Email provides email filtering using a Bayesian spam analyzer. It provides the [SpamAnalyzer](http://www.aspose.com/api/net/email/aspose.email.antispam/spamanalyzer) class for this purpose. This article shows how to train the filter to distinguish between spam and regular emails based on a words database.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Email-BayesianSpamAnalyzer-BayesianSpamAnalyzer.cs" >}}
