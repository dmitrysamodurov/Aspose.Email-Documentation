---
title: Public API Changes in Aspose.Email 4.0.0
type: docs
weight: 50
url: /net/public-api-changes-in-aspose-email-4-0-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.

**Adds FolderInfo.AddFile method**

Adds a file into pst folder

**Adds MapiTask.ReminderTime, MapiTask.ReminderSet and MapiTask.ReminderFileParameter properties**

These properties get or set reminder information for MapiTask

**Adds IEWSClient.GetCallInfo, IEWSClient.DisconnectPhoneCall, IEWSClient.PlayOnPhone properties and IEWSClient.GetUMConfiguration() method**

These members provide support for "Unified Messaging" feature from Exchange 2010 EWS

**Adds IEWSClient.UpdateContact method**

Updates a contact item in the Exchange store.

**Adds IEWSClient.ListMessages(string folder, int maxNumberOfMessages, MailQuery query) method**

List the messages in the specified folder with the search criteria.

**Adds Pop3Client.BeginListMessages(MailQuery query) and Pop3Client.BeginListMessages(MailQuery query, AsyncCallback callback, object state) method**

Begins ListMessage operation asynchronously with the search criteria.

**Adds ImapClient.ListMessages(bool retrieveRecursively) and ImapClient.ListMessages(string folderName, bool retrieveRecursively) methods**

Provides recursive listing of messages.

**Adds CredentialsByHostClient.OnConnect event**

The OnConnect event occurs when the client connects to the server.

**Adds MailMessageSaveOptions.NoEncodeCharactersToMht enum**

Provides the saving in MHT format without encode characters
