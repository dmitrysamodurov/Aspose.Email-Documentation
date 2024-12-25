---
title: Manage Extended Properties of Email Messages Using EWS in C#
ArticleTitle: Create, Retrieve, and Update Extended Properties of Email Messages Using EWS
type: docs
weight: 120
url: /net/manage-extended-properties-of-email-messages-using-ews/
---


Aspose.Email API lets you create, retrieve and update Extended properties of messages using the EWS client of the API. The following code sample illustrates this by creating an extended attribute, adding it to the message on the server and retrieve the message as [MapiMessage](https://reference.aspose.com/email/net/aspose.email.mapi/mapimessage/) from Exchange server using the client [FetchItem](https://reference.aspose.com/email/net/aspose.email.clients.exchange.webservice/iewsclient/fetchitem/).

```csharp
// Define a PidTagBodyContentId extended property
var extendedProperty = KnownPropertyList.BodyContentId;

// Create a message and set an extended property value
var msg = new MapiMessage("from@from.com", "to@to.com", "Test message", "This is a test message");
msg.SetProperty(extendedProperty, "03454432-6230-4e4b-887f-a498ea223599");

// Append message
var uri = ewsClient.AppendMessage(ewsClient.MailboxInfo.InboxUri, msg, true);

// Fetch appended item. Pass the extended property descriptor as method parameter.
var fetchedMsg = ewsClient.FetchItem(uri, new PropertyDescriptor[] { extendedProperty });

// Print the extended property value
Console.WriteLine(fetchedMsg.Properties[extendedProperty].GetString());
```
