---
title: Working with large PST files
type: docs
weight: 130
url: /net/working-with-large-pst-files/
---

Performance may be degraded when processing large PST files.
The following suggestions will help improve the performance of your app when processing large files.

### **Consider methods returning `IEnumerable` when traversing folders or messages in a pst.**

```csharp
using var pst = PersonalStorage.FromFile(@"storage.pst");

foreach (var folder in pst.RootFolder.EnumerateFolders())
foreach (var messageInfo in folder.EnumerateMessages())
{
    // Do something with message
}
```

### **Prefer [MessageInfo](https://reference.aspose.com/email/net/aspose.email.storage.pst/messageinfo/) for accessing basic message properties.**

```csharp
foreach (var messageInfo in folder.EnumerateMessages())
{
    Console.WriteLine($"Subject: {messageInfo.Subject}");
    Console.WriteLine($"To: {messageInfo.DisplayTo}");
    Console.WriteLine($"Importance: {messageInfo.Importance}");
    Console.WriteLine($"Message Class: {messageInfo.MessageClass}");
}
```

### **Avoid using the [ExtractMessage](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/extractmessage/) or [EnumerateMapiMessages](https://reference.aspose.com/email/net/aspose.email.storage.pst/folderinfo/enumeratemapimessages/) methods for all messages unless you need to have access to all properties.**

### **Consider using [EnumerateMessagesEntryId](https://reference.aspose.com/email/net/aspose.email.storage.pst/folderinfo/enumeratemessagesentryid/) to easily retrieve all message IDs contained in a folder.**

 ```csharp
foreach (var id in folder.EnumerateMessagesEntryId())
{
   // Use id to retrieve a property (ExtractProperty),
	 // extract a MapiMessage (ExtractMessage),
	 // extarct message attachments (ExtractAttachments),
	 // save msg to a stream(SaveMessageToStream).
}
 ```


### **Consider using [ExtractProperty](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/extractproperty/) to read a single property that is missing in MessageInfo.**

 ```csharp
foreach (var msgId in folder.EnumerateMessagesEntryId())
{
    var transportMessageHeaders =
        pst.ExtractProperty(Convert.FromBase64String(msgId), KnownPropertyList.TransportMessageHeaders.Tag)
            .GetString();
}
 ```

### **Consider using [ExtractAttachments](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/extractattachments/) if only the attachments are required.**

```csharp
foreach (var msgId in folder.EnumerateMessagesEntryId())
{
   var attachments = pst.ExtractAttachments(msgId);
}
```

### **Use [seach criteria](https://docs.aspose.com/email/net/working-with-messages-in-a-pst-file/#searching-messages-and-folders-in-pst)-based filtering to get the messages you require.**

```csharp
using var pst = PersonalStorage.FromFile(@"storage.pst");

var builder = new PersonalStorageQueryBuilder();
// Unread messages
builder.HasNoFlags(MapiMessageFlags.MSGFLAG_READ);

foreach (var folder in pst.RootFolder.EnumerateFolders())
{
    var unread = folder.GetContents(builder.GetQuery());
}
```

### **Consider using [SaveMessageToStream](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/savemessagetostream/) if it is necessary to save messages from pst.**

Instead of using:

```csharp
foreach (var id in folder.EnumerateMessagesEntryId())
{
    var msg = pst.ExtractMessage(id);
    msg.Save(@"message.msg");
}
```

Use:

```csharp
foreach (var id in folder.EnumerateMessagesEntryId())
{
    pst.SaveMessageToStream(id, File.OpenWrite(@"message.msg"));
}
```

### **Prefer bulk methods to [add](https://docs.aspose.com/email/net/working-with-messages-in-a-pst-file/#adding-bulk-messages) or [delete](https://docs.aspose.com/email/net/working-with-messages-in-a-pst-file/#delete-items-in-bulk-from-pst-file) multiple items.**
