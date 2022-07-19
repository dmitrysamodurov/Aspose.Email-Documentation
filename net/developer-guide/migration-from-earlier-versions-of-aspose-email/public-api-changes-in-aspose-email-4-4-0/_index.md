---
title: Public API Changes in Aspose.Email 4.4.0
type: docs
weight: 90
url: /net/public-api-changes-in-aspose-email-4-4-0/
---


{{% alert color="primary" %}} 

The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.

{{% /alert %}} 
## **Added APIs**
Method Aspose.Email.Mail.MailMessageLoadOptions.#ctor(Aspose.Email.Mail.MessageFormat)

Method Aspose.Email.Outlook.MapiJournal.Save(System.IO.Stream)
Method Aspose.Email.Outlook.MapiJournal.Save(System.String)
Property Aspose.Email.Outlook.MapiJournal.Attachments
Property Aspose.Email.Outlook.MapiJournal.Companies

Method Aspose.Email.CredentialsByHostClient.CancelAsyncOperation(System.IAsyncResult)
Method Aspose.Email.CredentialsByHostClient.CancelAsyncOperations
Method Aspose.Email.CredentialsByHostClient.Disconnect
Property Aspose.Email.CredentialsByHostClient.ConnectionState
Property Aspose.Email.CredentialsByHostClient.ConnectionTimeout
Property Aspose.Email.CredentialsByHostClient.MaxConnectionsPerServer

Method Aspose.Email.Imap.ImapClient.BeginCopyMessage(System.String,System.String)
Method Aspose.Email.Imap.ImapClient.BeginCopyMessage(System.String,System.String,System.AsyncCallback,System.Object)
Method Aspose.Email.Imap.ImapClient.BeginCopyMessage(System.String,System.String,System.String)
Method Aspose.Email.Imap.ImapClient.BeginCopyMessage(System.String,System.String,System.String,System.AsyncCallback,System.Object)
Method Aspose.Email.Imap.ImapClient.BeginSaveMessage(System.String,System.IO.Stream)
Method Aspose.Email.Imap.ImapClient.BeginSaveMessage(System.String,System.IO.Stream,System.AsyncCallback,System.Object)
Method Aspose.Email.Imap.ImapClient.BeginSaveMessage(System.String,System.String,System.IO.Stream)
Method Aspose.Email.Imap.ImapClient.BeginSaveMessage(System.String,System.String,System.IO.Stream,System.AsyncCallback,System.Object)
Method Aspose.Email.Imap.ImapClient.CommitDeletes
Method Aspose.Email.Imap.ImapClient.CommitDeletes(System.Int32)

Method Aspose.Email.Pop3.Pop3Client.BeginSaveMessage(System.String,System.IO.Stream)
Method Aspose.Email.Pop3.Pop3Client.BeginSaveMessage(System.String,System.IO.Stream,System.AsyncCallback,System.Object)
Method Aspose.Email.Pop3.Pop3Client.SaveMessage(System.String,System.IO.Stream)
## **Removed APIs**
Method Aspose.Email.CredentialsByHostClient.CheckCredentials
Method Aspose.Email.CredentialsByHostClient.Initialize
Property Aspose.Email.CredentialsByHostClient.InCall

Method Aspose.Email.Imap.ImapClient.Disconnect
Property Aspose.Email.Imap.ImapClient.ConnectionState
Method Aspose.Email.Pop3.Pop3Client.Disconnect

Property Aspose.Email.Mail.SmtpClient.ConnectionTimeout
