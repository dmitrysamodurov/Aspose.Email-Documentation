---
title: Public API Changes in Aspose.Email 6.0.0
type: docs
weight: 250
url: /net/public-api-changes-in-aspose-email-6-0-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.

**Added:**

Class Aspose.Email.Exchange.ExchangeDistributionList
Method Aspose.Email.Exchange.ExchangeDistributionList.#ctor
Method Aspose.Email.Exchange.ExchangeDistributionList.ToMailAddress
Method Aspose.Email.Exchange.IEWSClient.AddToDistributionList(Aspose.Email.Exchange.ExchangeDistributionList,Aspose.Email.Mail.MailAddressCollection)
Method Aspose.Email.Exchange.IEWSClient.CreateDistributionList(Aspose.Email.Exchange.ExchangeDistributionList,Aspose.Email.Mail.MailAddressCollection)
Method Aspose.Email.Exchange.IEWSClient.DeleteDistributionList(Aspose.Email.Exchange.ExchangeDistributionList,System.Boolean)
Method Aspose.Email.Exchange.IEWSClient.DeleteFromDistributionList(Aspose.Email.Exchange.ExchangeDistributionList,Aspose.Email.Mail.MailAddressCollection)
Method Aspose.Email.Exchange.IEWSClient.ExpandDistributionList(Aspose.Email.Mail.MailAddress)
Method Aspose.Email.Exchange.IEWSClient.FetchDistributionList(Aspose.Email.Exchange.ExchangeDistributionList)
Method Aspose.Email.Exchange.IEWSClient.ListDistributionLists
Property Aspose.Email.Exchange.ExchangeDistributionList.ChangeKey
Property Aspose.Email.Exchange.ExchangeDistributionList.DisplayName
Property Aspose.Email.Exchange.ExchangeDistributionList.Id
Property Aspose.Email.Mail.MailAddress.Id

Class Aspose.Email.ForwardMessageBuilder
Class Aspose.Email.OriginalMessageAdditionMode
Class Aspose.Email.ReplyMessageBuilder
Class Aspose.Email.ResponseMessageBuilder
Enum Aspose.Email.OriginalMessageAdditionMode.Attachment
Enum Aspose.Email.OriginalMessageAdditionMode.None
Enum Aspose.Email.OriginalMessageAdditionMode.Textpart
Field Aspose.Email.Outlook.MapiPropertyTag.PR_ATTACHMENT_HIDDEN
Method Aspose.Email.ForwardMessageBuilder.#ctor
Method Aspose.Email.ForwardMessageBuilder.BuildResponse(Aspose.Email.Mail.MailMessage)
Method Aspose.Email.ForwardMessageBuilder.BuildResponse(Aspose.Email.Outlook.MapiMessage)
Method Aspose.Email.ReplyMessageBuilder.#ctor
Method Aspose.Email.ReplyMessageBuilder.BuildResponse(Aspose.Email.Mail.MailMessage)
Method Aspose.Email.ReplyMessageBuilder.BuildResponse(Aspose.Email.Outlook.MapiMessage)
Method Aspose.Email.ResponseMessageBuilder.#ctor
Method Aspose.Email.ResponseMessageBuilder.BuildResponse(Aspose.Email.Mail.MailMessage)
Method Aspose.Email.ResponseMessageBuilder.BuildResponse(Aspose.Email.Outlook.MapiMessage)
Property Aspose.Email.ReplyMessageBuilder.ReplyAll
Property Aspose.Email.ResponseMessageBuilder.AdditionMode
Property Aspose.Email.ResponseMessageBuilder.ResponseText
Property Aspose.Email.ResponseMessageBuilder.Sender

Field/Enum Aspose.Email.Mail.MhtFormatOptions.SkipByteOrderMarkInBody

Class Aspose.Email.Mail.MailMessageEventArgs
Method Aspose.Email.Mail.MailMessageEventArgs.#ctor(Aspose.Email.Mail.MailMessage)
Property Aspose.Email.Mail.MailMessageEventArgs.Message
Method Aspose.Email.Exchange.IEWSClient.ListMessages(System.Collections.Generic.IEnumerable<System.String>)

Method Aspose.Email.Outlook.MapiAttachmentCollection.RemoveAt(System.Int32)
Method Aspose.Email.Outlook.Pst.PersonalStorage.SplitInto(System.Int64,System.String)

**Removed:**

Method Aspose.Email.Outlook.Pst.PersonalStorage.SplitInto(System.Int32,System.String)
Property Aspose.Email.Mail.SmtpClientBulkSendEventArgs.Message
