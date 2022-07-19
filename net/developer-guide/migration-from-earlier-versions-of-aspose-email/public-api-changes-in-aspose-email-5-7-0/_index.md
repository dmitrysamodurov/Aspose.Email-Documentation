---
title: Public API Changes in Aspose.Email 5.7.0
type: docs
weight: 220
url: /net/public-api-changes-in-aspose-email-5-7-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.
## **Added APIs**
Class Aspose.Email.Imap.ImapMonitoringEventArgs
Class Aspose.Email.Imap.ImapMonitoringEventHandler
Class Aspose.Email.Mail.EmlLoadOptions
Class Aspose.Email.Mail.EmlxLoadOptions
Class Aspose.Email.Mail.HtmlLoadOptions
Class Aspose.Email.Mail.LoadOptions
Class Aspose.Email.Mail.MhtmlLoadOptions
Class Aspose.Email.Mail.MsgLoadOptions
Class Aspose.Email.Outlook.Pst.MessageKind
Field/Enum Aspose.Email.Outlook.Pst.MessageKind.FolderAssociatedInformation
Field/Enum Aspose.Email.Outlook.Pst.MessageKind.Normal
Method Aspose.Email.Exchange.IEWSClient.AddHeader(System.String,System.String)
Method Aspose.Email.Exchange.IEWSClient.RemoveHeader(System.String)
Method Aspose.Email.Imap.ImapClient.Dispose
Method Aspose.Email.Imap.ImapClient.StartMonitoring(Aspose.Email.Imap.ImapMonitoringEventHandler)
Method Aspose.Email.Imap.ImapClient.StartMonitoring(System.String,Aspose.Email.Imap.ImapMonitoringEventHandler)
Method Aspose.Email.Imap.ImapClient.StopMonitoring
Method Aspose.Email.Imap.ImapClient.StopMonitoring(System.String)
Method Aspose.Email.Imap.ImapMonitoringEventArgs.#ctor(System.String,Aspose.Email.Imap.ImapMessageInfo[],Aspose.Email.Imap.ImapMessageInfo[])
Method Aspose.Email.Imap.ImapMonitoringEventArgs.#ctor(System.String,System.Exception)
Method Aspose.Email.Mail.EmlLoadOptions.#ctor
Method Aspose.Email.Mail.EmlxLoadOptions.#ctor
Method Aspose.Email.Mail.HtmlLoadOptions.#ctor
Method Aspose.Email.Mail.LoadOptions.#ctor
Method Aspose.Email.Mail.LoadOptions.#ctor(Aspose.Email.Mail.MessageFormat)
Method Aspose.Email.Mail.MailMessage.Load(System.IO.Stream,Aspose.Email.Mail.LoadOptions)
Method Aspose.Email.Mail.MailMessage.Load(System.String,Aspose.Email.Mail.LoadOptions)
Method Aspose.Email.Mail.MhtmlLoadOptions.#ctor
Method Aspose.Email.Mail.MsgLoadOptions.#ctor
Method Aspose.Email.Mail.TemplateEngine.Merge(System.Data.DataRow)
Method Aspose.Email.Outlook.MapiCalendar.Dispose
Method Aspose.Email.Outlook.Pst.FolderInfo.GetContents(Aspose.Email.Outlook.Pst.MessageKind)
Property Aspose.Email.Exchange.ExchangeQueryBuilder.MessageId
Property Aspose.Email.Exchange.IEWSClient.Headers
Property Aspose.Email.Imap.ImapMonitoringEventArgs.DeletedMessages
Property Aspose.Email.Imap.ImapMonitoringEventArgs.Error
Property Aspose.Email.Imap.ImapMonitoringEventArgs.FolderName
Property Aspose.Email.Imap.ImapMonitoringEventArgs.NewMessages
Property Aspose.Email.Mail.EmlLoadOptions.PreserveTnefAttachments
Property Aspose.Email.Mail.HtmlLoadOptions.PathToResources
Property Aspose.Email.Mail.HtmlLoadOptions.SetPlainTextView
Property Aspose.Email.Mail.LoadOptions.MessageFormat
Property Aspose.Email.Mail.LoadOptions.PrefferedTextEncoding
Property Aspose.Email.Mail.MessageFormat.Html
Property Aspose.Email.Mail.MhtmlLoadOptions.PreserveTnefAttachments
Property Aspose.Email.Mail.MsgLoadOptions.PreserveTnefAttachments
Property Aspose.Email.Outlook.Pst.PersonalStorageQueryBuilder.MessageId
## **Removed APIs**
Class Aspose.Email.Pop3.Pop3Authentication
Method Aspose.Email.Outlook.Pst.FolderInfo.DeleteChildMessages(Aspose.Email.Outlook.Pst.MessageInfoCollection)
Method Aspose.Email.Pop3.Pop3Authentication.Equals(System.Object)
Method Aspose.Email.Pop3.Pop3Authentication.GetHashCode
Method Aspose.Email.Pop3.Pop3Authentication.ToString
Property Aspose.Email.Pop3.Pop3Authentication.Auto
Property Aspose.Email.Pop3.Pop3Authentication.CramMD5Authentication
Property Aspose.Email.Pop3.Pop3Authentication.DigestMD5Authentication
Property Aspose.Email.Pop3.Pop3Authentication.PlainTextAuthentication
Property Aspose.Email.Pop3.Pop3Authentication.PlainTextLogin
