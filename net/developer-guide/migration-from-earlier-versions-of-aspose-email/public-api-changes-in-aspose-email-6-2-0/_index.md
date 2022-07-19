---
title: Public API Changes in Aspose.Email 6.2.0
type: docs
weight: 270
url: /net/public-api-changes-in-aspose-email-6-2-0/
---

The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.
### **Added APIs**
Class Aspose.Email.Exchange.AppointmentCollection
Class Aspose.Email.Mail.HtmlFormatOptions
Field/Enum Aspose.Email.Mail.HtmlFormatOptions.None
Field/Enum Aspose.Email.Mail.HtmlFormatOptions.WriteCompleteBccEmailAddress
Field/Enum Aspose.Email.Mail.HtmlFormatOptions.WriteCompleteCcEmailAddress
Field/Enum Aspose.Email.Mail.HtmlFormatOptions.WriteCompleteEmailAddress
Field/Enum Aspose.Email.Mail.HtmlFormatOptions.WriteCompleteFromEmailAddress
Field/Enum Aspose.Email.Mail.HtmlFormatOptions.WriteCompleteToEmailAddress
Field/Enum Aspose.Email.Mail.HtmlFormatOptions.WriteHeader
Method Aspose.Email.Exchange.AppointmentCollection.#ctor
Method Aspose.Email.Exchange.AppointmentCollection.#ctor(System.Collections.Generic.IEnumerable)
Method Aspose.Email.Exchange.AppointmentCollection.op_Implicit(Aspose.Email.Exchange.AppointmentCollection)~Aspose.Email.Mail.Appointment[]
Method Aspose.Email.Exchange.AppointmentCollection.op_Implicit(Aspose.Email.Exchange.AppointmentCollection)~System.Collections.Generic.List
Method Aspose.Email.Exchange.AppointmentCollection.op_Implicit(Aspose.Email.Mail.Appointment[])~Aspose.Email.Exchange.AppointmentCollection
Method Aspose.Email.Exchange.AppointmentCollection.op_Implicit(System.Collections.Generic.List)~Aspose.Email.Exchange.AppointmentCollection
Method Aspose.Email.Exchange.ExchangeClient.MoveItems(System.String, System.Boolean,System.String[])
Method Aspose.Email.Exchange.ExchangeClient.MoveMessage(System.String, System.Boolean,System.String)
Method Aspose.Email.Exchange.ExchangeClient.MoveMessage(System.String, System.String)
Method Aspose.Email.Exchange.ExchangeMessageInfoCollection.#ctor(System.Collections.Generic.IEnumerable)
Method Aspose.Email.Exchange.IEWSClient.GetContact(Aspose.Email.Mail.ObjectIdentifier)
Method Aspose.Email.Exchange.IEWSClient.GetContact(Aspose.Email.Mail.ObjectIdentifier, Aspose.Email.Exchange.ExchangeListContactsOptions)
Method Aspose.Email.Exchange.IEWSClient.GetContact(System.String)
Method Aspose.Email.Exchange.IEWSClient.GetContact(System.String,Aspose.Email.Exchange.ExchangeListContactsOptions)
Method Aspose.Email.Exchange.IEWSClient.ListAppointments(Aspose.Email.MailQuery, System.Int32)
Method Aspose.Email.Exchange.IEWSClient.ListAppointments(Aspose.Email.MailQuery, System.Int32,System.Int32)
Method Aspose.Email.Exchange.IEWSClient.ListAppointments(System.Int32)
Method Aspose.Email.Exchange.IEWSClient.ListAppointments(System.Int32, System.Int32)
Method Aspose.Email.Exchange.IEWSClient.ListAppointments(System.String, Aspose.Email.MailQuery, System.Int32)
Method Aspose.Email.Exchange.IEWSClient.ListAppointments(System.String, Aspose.Email.MailQuery, System.Int32, System.Int32)
Method Aspose.Email.Exchange.IEWSClient.ListAppointments(System.String, System.Int32)
Method Aspose.Email.Exchange.IEWSClient.ListAppointments(System.String, System.Int32, System.Int32)
Method Aspose.Email.Exchange.IEWSClient.ListMessages(System.String, Aspose.Email.Exchange.ExchangeMessageInfoCollection, System.Int32, System.Int32, Aspose.Email.Exchange.ExchangeListMessagesOptions)
Method Aspose.Email.Exchange.IEWSClient.ListMessages(System.String,System.Int32, System.Int32, Aspose.Email.Exchange.ExchangeListMessagesOptions)
Method Aspose.Email.Imap.ImapClient.BeginListMessages(Aspose.Email.IConnection, System.Int32, System.Int32)
Method Aspose.Email.Imap.ImapClient.BeginListMessages(Aspose.Email.IConnection, System.Int32, System.Int32, System.AsyncCallback)
Method Aspose.Email.Imap.ImapClient.BeginListMessages(Aspose.Email.IConnection, System.Int32, System.Int32, System.AsyncCallback, System.Object)
Method Aspose.Email.Imap.ImapClient.BeginListMessages(System.Int32, System.Int32)
Method Aspose.Email.Imap.ImapClient.BeginListMessages(System.Int32, System.Int32, System.AsyncCallback)
Method Aspose.Email.Imap.ImapClient.BeginListMessages(System.Int32, System.Int32, System.AsyncCallback, System.Object)
Method Aspose.Email.Imap.ImapClient.ListMessages(Aspose.Email.IConnection, System.Int32, System.Int32)
Method Aspose.Email.Imap.ImapClient.ListMessages(System.Int32, System.Int32)
Method Aspose.Email.Imap.ImapMessageInfoCollection.#ctor(System.Collections.Generic.IEnumerable)
Method Aspose.Email.Imap.ImapMessageInfoCollection.op_Implicit(Aspose.Email.Imap.ImapMessageInfo[])~Aspose.Email.Imap.ImapMessageInfoCollection
Method Aspose.Email.Imap.ImapMessageInfoCollection.op_Implicit(Aspose.Email.Imap.ImapMessageInfoCollection)~Aspose.Email.Imap.ImapMessageInfo[]
Method Aspose.Email.Imap.ImapMessageInfoCollection.op_Implicit(Aspose.Email.Imap.ImapMessageInfoCollection)~System.Collections.Generic.List
Method Aspose.Email.Imap.ImapMessageInfoCollection.op_Implicit(System.Collections.Generic.List)~Aspose.Email.Imap.ImapMessageInfoCollection
Method Aspose.Email.Outlook.MapiAttachmentCollection.Insert(System.Int32, System.String, Aspose.Email.Outlook.MapiMessage)
Method Aspose.Email.Outlook.MapiAttachmentCollection.Replace(System.Int32, System.String, Aspose.Email.Outlook.MapiMessage)
Method Aspose.Email.Outlook.MapiContact.FromVCard(System.String, System.Text.Encoding)
Method Aspose.Email.Outlook.MapiObjectProperty.ToMapiMessage
Property Aspose.Email.Exchange.AppointmentCollection.LastItemOffset
Property Aspose.Email.Exchange.AppointmentCollection.LastPage
Property Aspose.Email.Exchange.AppointmentCollection.TotalCount
Property Aspose.Email.Imap.ImapMessageInfoCollection.LastItemOffset
Property Aspose.Email.Imap.ImapMessageInfoCollection.LastPage
Property Aspose.Email.Imap.ImapMessageInfoCollection.TotalCount
Property Aspose.Email.Mail.HtmlSaveOptions.HtmlFormatOptions
### **Removed APIs**
Class Aspose.Email.Mail.MailMessageSaveOptions
Event Aspose.Email.Mail.SmtpClient.SendCompleted
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.HideExtraPrintHeader
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.NoEncodeCharactersToMht
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.None
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.WriteCompleteBccEmailAddressToMht
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.WriteCompleteCcEmailAddressToMht
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.WriteCompleteEmailAddressToMht
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.WriteCompleteFromEmailAddressToMht
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.WriteCompleteToEmailAddressToMht
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.WriteHeaderToMht
Field/Enum Aspose.Email.Mail.MailMessageSaveOptions.WriteOutlineAttachmentsToMht
Field/Enum Aspose.Email.Mail.MhtFormatOptions.WriteCompleteEmailAddressToMht
Method Aspose.Email.Exchange.ExchangeClient.MoveItem(System.String, System.String)
Method Aspose.Email.Exchange.IEWSClient.DeleteContact(Aspose.Email.Outlook.MapiContact, System.Boolean)
Method Aspose.Email.Exchange.IEWSClient.FetchMapiAttachments(System.Collections.Generic.IEnumerable)
Method Aspose.Email.Exchange.IEWSClient.ListContacts(System.String,Aspose.Email.Exchange.ExchangeListContactsOptions)
Method Aspose.Email.Exchange.IEWSClient.LoadContactPhoto(Aspose.Email.Outlook.MapiContactPhoto)
Method Aspose.Email.Exchange.IEWSClient.UpdateContact(Aspose.Email.Outlook.MapiContact)
Method Aspose.Email.Mail.IMessage.Save(System.IO.Stream,Aspose.Email.Mail.MailMessageSaveType)
Method Aspose.Email.Mail.IMessage.Save(System.String,Aspose.Email.Mail.MailMessageSaveType)
Method Aspose.Email.Mail.MailMessage.Save(System.IO.Stream,Aspose.Email.Mail.FileCompatibilityMode)
Method Aspose.Email.Mail.MailMessage.Save(System.IO.Stream,Aspose.Email.Mail.MailMessageSaveType)
Method Aspose.Email.Mail.MailMessage.Save(System.IO.Stream,Aspose.Email.Mail.MailMessageSaveType,Aspose.Email.Mail.MailMessageSaveOptions)
Method Aspose.Email.Mail.MailMessage.Save(System.IO.Stream,Aspose.Email.Mail.MessageFormat)
Method Aspose.Email.Mail.MailMessage.Save(System.IO.Stream,Aspose.Email.Mail.MessageFormat,Aspose.Email.Mail.MailMessageSaveOptions)
Method Aspose.Email.Mail.MailMessage.Save(System.String,Aspose.Email.Mail.FileCompatibilityMode)
Method Aspose.Email.Mail.MailMessage.Save(System.String,Aspose.Email.Mail.MailMessageSaveType)
Method Aspose.Email.Mail.MailMessage.Save(System.String,Aspose.Email.Mail.MailMessageSaveType,Aspose.Email.Mail.MailMessageSaveOptions)
Method Aspose.Email.Mail.MailMessage.Save(System.String,Aspose.Email.Mail.MessageFormat)
Method Aspose.Email.Mail.MailMessage.Save(System.String,Aspose.Email.Mail.MessageFormat,Aspose.Email.Mail.MailMessageSaveOptions)
Method Aspose.Email.Mail.SmtpClient.SendAsyncCancel
Method Aspose.Email.Mime.HeaderCollection.Add(Aspose.Email.Mime.MimeHeader)
Method Aspose.Email.Outlook.FollowUpManager.GetFlag(Aspose.Email.Outlook.MapiMessage)
Method Aspose.Email.Outlook.FollowUpManager.SetFlag(Aspose.Email.Outlook.MapiMessage, Aspose.Email.Outlook.FollowUpOptions)
Method Aspose.Email.Outlook.MapiContactPhoto.#ctor(System.String, Aspose.Email.Outlook.MapiContactPhotoImageFormat)
Method Aspose.Email.Outlook.MapiContactPhoto.#ctor(System.String, System.Byte[], Aspose.Email.Outlook.MapiContactPhotoImageFormat)
Method Aspose.Email.Outlook.MapiMessage.FromMailMessage(Aspose.Email.Mail.MailMessage, Aspose.Email.Outlook.OutlookMessageFormat)
Method Aspose.Email.Outlook.MapiMessage.FromMailMessage(Aspose.Email.Mail.MailMessage, Aspose.Email.Outlook.OutlookMessageFormat, System.Boolean)
Method Aspose.Email.Outlook.Pst.PersonalStorage.ChangeDisplayName(System.String)
Property Aspose.Email.Mail.MailMessage.PreserveOriginalBoundaries
Property Aspose.Email.Mail.MailMessage.PreserveOriginalDates
Property Aspose.Email.Outlook.Pst.PersonalStorage.DisplayName
Property Aspose.Email.Outlook.Pst.PersonalStorage.MessageStoreProperties
