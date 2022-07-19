---
title: Public API Changes in Aspose.Email 3.9.0
type: docs
weight: 40
url: /net/public-api-changes-in-aspose-email-3-9-0/
---


{{% alert color="primary" %}} 

This page list public API changes that were introduced in Aspose.Email 3.8.0. It includes new and obsolete public methods, as well as a description of any changes in the behavior of the API that may affect existing code.

{{% /alert %}} 

- MapiTask.FromVTodo(Stream stream)
- MapiTask.FromVTodo(string filePath)
- GmailClient.GetInstance(string clientId, string clientSecret, string refreshToken)
- GmailClient.GetInstance(string clientId, string clientSecret, string refreshToken, WebProxy proxy)
- ImapClient(string host, string username, ITokenProvider tokenProvider)
- ImapClient(string host, int port, string username, ITokenProvider tokenProvider)
- SmtpClient(string host, string username, ITokenProvider tokenProvider)
- SmtpClient(string host, int port, string username, ITokenProvider tokenProvider)
- PersonalStorage.MoveItem(FolderInfo folder, FolderInfo destFolder) - Moves a specified folder to a new parent folder within the current pst
- PersonalStorage.MoveItem(MessageInfo message, FolderInfo destFolder) - Moves a specified message to a new folder within the current pst
- MoveContents(FolderInfo destFolder) - Moves the contents to a new folder
- MoveSubfolders(FolderInfo destFolder) - Moves the subfolders to a new parent folder
- Pop3Client.GetCapabilities()
- ImapClient.GetCapabilities()
- SmtpClient.GetCapabilities()
- ImapClient.BeginFetchMessage(string uniqueId)
- ImapClient.BeginFetchMessage(string folder, string uniqueId)
- ImapClient.BeginFetchMessage(string uniqueId, AsyncCallback callback, object state)
- ImapClient.BeginFetchMessage(string folder, string uniqueId, AsyncCallback callback, object state)
- ImapClient.BeginDeleteMessage(string uniqueId)
- ImapClient.BeginDeleteMessage(parentFolder, uniqueId, null, null);
- ImapClient.BeginDeleteMessage(string uniqueId, AsyncCallback callback, object state)
- ImapClient.BeginDeleteMessage(string parentFolder, string uniqueId, AsyncCallback callback, object state)
- ImapClient.BeginListMessages(MailQuery query, int maxNumberOfMessages)
- ImapClient.BeginListMessages(string parentFolder, MailQuery query, int maxNumberOfMessages)
- ImapClient.BeginListMessages(MailQuery query, int maxNumberOfMessages, AsyncCallback callback, object state)
- ImapClient.BeginListMessages(string parentFolder, MailQuery query, int maxNumberOfMessages, AsyncCallback callback, object state)
- ImapClient.BeginListMessages(MailQuery query)
- ImapClient.BeginListMessages(string parentFolder, MailQuery query)
- ImapClient.BeginListMessages(MailQuery query, AsyncCallback callback, object state)
- ImapClient.BeginListMessages(string parentFolder, MailQuery query, AsyncCallback callback, object state)
- Pop3Client.FetchMessage(string uniqueId)
- Pop3Client.DeleteMessage(string uniqueId)
- Pop3Client.BeginDeleteMessage(string uniqueId)
- Pop3Client.BeginDeleteMessage(string uniqueId, AsyncCallback callback, object state)
- BeginFetchMessage(string uniqueId)
- BeginFetchMessage(string uniqueId, AsyncCallback callback, object state)
