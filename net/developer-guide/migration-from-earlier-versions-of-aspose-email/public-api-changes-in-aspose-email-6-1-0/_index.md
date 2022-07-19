---
title: Public API Changes in Aspose.Email 6.1.0
type: docs
weight: 260
url: /net/public-api-changes-in-aspose-email-6-1-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.
## **Added APIs**
Class Aspose.Email.Mail.WebDavContactSaveOptions
Method Aspose.Email.Mail.WebDavContactSaveOptions.#ctor
Property Aspose.Email.Mail.WebDavContactSaveOptions.Default

Class Aspose.Email.Outlook.MapiContactSaveOptions
Method Aspose.Email.Outlook.MapiContactSaveOptions.#ctor
Property Aspose.Email.Outlook.MapiContactSaveOptions.Default

Class Aspose.Email.PipeliningMode
Field/Enum Aspose.Email.PipeliningMode.Auto
Field/Enum Aspose.Email.PipeliningMode.Disabled
Field/Enum Aspose.Email.PipeliningMode.Enabled

Class Aspose.Email.PipeliningStatus
Method Aspose.Email.PipeliningStatus.op_Implicit(Aspose.Email.PipeliningMode)~Aspose.Email.PipeliningStatus
Method Aspose.Email.PipeliningStatus.op_Implicit(Aspose.Email.PipeliningStatus)~Aspose.Email.PipeliningMode
Method Aspose.Email.PipeliningStatus.op_Implicit(Aspose.Email.PipeliningStatus)~System.Boolean
Method Aspose.Email.PipeliningStatus.op_Implicit(System.Boolean)~Aspose.Email.PipeliningStatus
Method Aspose.Email.PipeliningStatus.ToString
Property Aspose.Email.PipeliningStatus.ClientMode
Property Aspose.Email.PipeliningStatus.PipeliningEnabled
Property Aspose.Email.PipeliningStatus.SupportedByServer

Field/Enum Aspose.Email.Mail.PhoneNumberCategory.PrimaryValue
Field/Enum Aspose.Email.Outlook.MapiPropertyTag.PidTagUrlName

Method Aspose.Email.Exchange.IEWSClient.CreateFolder(System.String,System.String)
Property Aspose.Email.Exchange.IEWSClient.UseSlashAsFolderSeparator

Method Aspose.Email.Mail.Contact.op_Implicit(Aspose.Email.Mail.Contact)~Aspose.Email.Outlook.MapiContact
Method Aspose.Email.Mail.Contact.op_Implicit(Aspose.Email.Outlook.MapiContact)~Aspose.Email.Mail.Contact
Method Aspose.Email.Mail.Contact.ToString

Method Aspose.Email.Outlook.MapiAttachmentCollection.Remove(Aspose.Email.Outlook.MapiAttachment)

Method Aspose.Email.Outlook.MapiCalendarTimeZone.#ctor(System.TimeZoneInfo)

Method Aspose.Email.Outlook.Pst.PersonalStorage.ExtractAttachments(Aspose.Email.Outlook.Pst.MessageInfo)
Method Aspose.Email.Outlook.Pst.PersonalStorage.ExtractAttachments(System.String)
Method Aspose.Email.Outlook.Pst.PersonalStorage.GetParentFolder(System.Byte[])
Method Aspose.Email.Outlook.Pst.PersonalStorage.GetParentFolder(System.String)

Property Aspose.Email.Mail.AssociatedPerson.Prefered
Property Aspose.Email.Mail.InstantMessengerAddress.Prefered
Property Aspose.Email.Mail.ObjectIdentifier.WebDavId
Property Aspose.Email.Mail.PhoneNumberCategory.Primary
Property Aspose.Email.Mail.Url.Prefered
Property Aspose.Email.Mail.UrlList.Ftp

Method Aspose.Email.Mail.SmtpClient.BeginForward(Aspose.Email.IConnection,System.String,Aspose.Email.Mail.MailAddressCollection,Aspose.Email.Mail.MailMessage)
Method Aspose.Email.Mail.SmtpClient.BeginForward(Aspose.Email.IConnection,System.String,Aspose.Email.Mail.MailAddressCollection,Aspose.Email.Mail.MailMessage,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginForward(Aspose.Email.IConnection,System.String,Aspose.Email.Mail.MailAddressCollection,Aspose.Email.Mail.MailMessage,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginForward(Aspose.Email.IConnection,System.String,System.String,Aspose.Email.Mail.MailMessage)
Method Aspose.Email.Mail.SmtpClient.BeginForward(Aspose.Email.IConnection,System.String,System.String,Aspose.Email.Mail.MailMessage,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginForward(Aspose.Email.IConnection,System.String,System.String,Aspose.Email.Mail.MailMessage,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginForward(System.String,Aspose.Email.Mail.MailAddressCollection,Aspose.Email.Mail.MailMessage)
Method Aspose.Email.Mail.SmtpClient.BeginForward(System.String,Aspose.Email.Mail.MailAddressCollection,Aspose.Email.Mail.MailMessage,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginForward(System.String,Aspose.Email.Mail.MailAddressCollection,Aspose.Email.Mail.MailMessage,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginForward(System.String,System.String,Aspose.Email.Mail.MailMessage)
Method Aspose.Email.Mail.SmtpClient.BeginForward(System.String,System.String,Aspose.Email.Mail.MailMessage,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginForward(System.String,System.String,Aspose.Email.Mail.MailMessage,System.AsyncCallback,System.Object)

Method Aspose.Email.Mail.SmtpClient.BeginNoop
Method Aspose.Email.Mail.SmtpClient.BeginNoop(Aspose.Email.IConnection)
Method Aspose.Email.Mail.SmtpClient.BeginNoop(Aspose.Email.IConnection,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginNoop(Aspose.Email.IConnection,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginNoop(System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginNoop(System.AsyncCallback,System.Object)

Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,Aspose.Email.Mail.MailMessage)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,Aspose.Email.Mail.MailMessage,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,Aspose.Email.Mail.MailMessage,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,Aspose.Email.Mail.MailMessage[])
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,System.Collections.IEnumerable)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,System.Collections.IEnumerable,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,System.Collections.IEnumerable,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,System.Collections.IEnumerable,System.EventHandler)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,System.Collections.IEnumerable,System.EventHandler,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,System.Collections.IEnumerable,System.EventHandler,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,System.String,System.String,System.String,System.String)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,System.String,System.String,System.String,System.String,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.IConnection,System.String,System.String,System.String,System.String,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.Mail.MailMessage)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.Mail.MailMessage,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.Mail.MailMessage,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginSend(Aspose.Email.Mail.MailMessage[])
Method Aspose.Email.Mail.SmtpClient.BeginSend(System.Collections.IEnumerable)
Method Aspose.Email.Mail.SmtpClient.BeginSend(System.Collections.IEnumerable,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginSend(System.Collections.IEnumerable,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginSend(System.Collections.IEnumerable,System.EventHandler)
Method Aspose.Email.Mail.SmtpClient.BeginSend(System.Collections.IEnumerable,System.EventHandler,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginSend(System.Collections.IEnumerable,System.EventHandler,System.AsyncCallback,System.Object)
Method Aspose.Email.Mail.SmtpClient.BeginSend(System.String,System.String,System.String,System.String)
Method Aspose.Email.Mail.SmtpClient.BeginSend(System.String,System.String,System.String,System.String,System.AsyncCallback)
Method Aspose.Email.Mail.SmtpClient.BeginSend(System.String,System.String,System.String,System.String,System.AsyncCallback,System.Object)

Method Aspose.Email.Mail.SmtpClient.EndForward(System.IAsyncResult)
Method Aspose.Email.Mail.SmtpClient.EndNoop(System.IAsyncResult)
Method Aspose.Email.Mail.SmtpClient.EndSend(System.IAsyncResult)

Method Aspose.Email.Mail.SmtpClient.Forward(Aspose.Email.IConnection,System.String,Aspose.Email.Mail.MailAddressCollection,Aspose.Email.Mail.MailMessage)
Method Aspose.Email.Mail.SmtpClient.Forward(Aspose.Email.IConnection,System.String,System.String,Aspose.Email.Mail.MailMessage)

Method Aspose.Email.Mail.SmtpClient.Noop
Method Aspose.Email.Mail.SmtpClient.Noop(Aspose.Email.IConnection)

Method Aspose.Email.Mail.SmtpClient.Send(Aspose.Email.IConnection,Aspose.Email.Mail.MailMessage)
Method Aspose.Email.Mail.SmtpClient.Send(Aspose.Email.IConnection,Aspose.Email.Mail.MailMessage[])
Method Aspose.Email.Mail.SmtpClient.Send(Aspose.Email.IConnection,Aspose.Email.Mail.MailMessageCollection)
Method Aspose.Email.Mail.SmtpClient.Send(Aspose.Email.IConnection,System.Collections.IEnumerable)
Method Aspose.Email.Mail.SmtpClient.Send(Aspose.Email.IConnection,System.String,System.String,System.String,System.String)
Method Aspose.Email.Mail.SmtpClient.Send(Aspose.Email.Mail.MailMessage[])
Method Aspose.Email.Mail.SmtpClient.Send(Aspose.Email.Mail.MailMessageCollection)
Method Aspose.Email.Mail.SmtpClient.Send(System.Collections.IEnumerable)
## **Removed APIs**
Method Aspose.Email.Mail.Contact.op_Explicit(Aspose.Email.Mail.Contact)~Aspose.Email.Outlook.MapiContact
Property Aspose.Email.Protocols.Exchange.ExchangeDav.WebDavContactSaveOptions.Default
