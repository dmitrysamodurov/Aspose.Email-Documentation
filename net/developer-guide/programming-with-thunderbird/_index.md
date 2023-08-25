---
title: Programming with Thunderbird
type: docs
weight: 110
url: /net/programming-with-thunderbird/
---


## **Reading Messages**

[Mozilla Thunderbird](https://www.thunderbird.net/en-US/) is an open-source, cross-platform email client, developed by the Mozilla Foundation. It stores emails in its own file structure, managing messages indices and subfolders through proprietary file formats. Aspose.Email can work with Thunderbird mail storage structures. The [MboxrdStorageReader](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxrdstoragereader/) class lets developers read messages from Mozilla Thunderbird mail storage file. This article shows how to read the messages from Thunderbird email storage:

1. Open the Thunderbird storage file in *FileStream*.
1. Create an instance of the [MboxrdStorageReader](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxrdstoragereader/) class and pass the above stream to the constructor.
1. Call [ReadNextMessage()](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxrdstoragereader/readnextmessage/#readnextmessage/) to get the first message.
1. Use the same [ReadNextMessage()](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxrdstoragereader/readnextmessage/#readnextmessage/) in a while loop to read all the messages.
1. Close all the streams.

The following code snippet shows you how to read all the messages from a Thunderbird mail storage.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Thunderbird-ReadMessagesFromThunderbird-ReadMessagesFromThunderbird.cs" >}}

### **Retrieving message properties**

[MboxMessageInfo](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxmessageinfo/#mboxmessageinfo-class) class contains the following properties to retrieve information about a message:

- DateTime [Date](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxmessageinfo/date/#mboxmessageinfodate-property) - Gets the date of message
- MailAddress [From](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxmessageinfo/from/#mboxmessageinfofrom-property) - Gets the from address
- string [Subject](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxmessageinfo/subject/) - Gets the message subject
- MailAddressCollection [To](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxmessageinfo/to/) - Gets the address collection that contains the recipients of message
- MailAddressCollection [CC](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxmessageinfo/cc/) - Gets the address collection that contains CC recipients
- MailAddressCollection [Bcc](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxmessageinfo/bcc/) - Gets the address collection that contains BCC recipients of message

**Code sample**

```cs
MboxStorageReader reader = MboxStorageReader.CreateReader(fileName, new MboxLoadOptions());

foreach (var mboxMessageInfo in reader.EnumerateMessageInfo())
{
    Console.Writeline($"Subject: {mboxMessageInfo.Subject}");
    Console.Writeline($"Date: {mboxMessageInfo.Date}");
    Console.Writeline($"From: {mboxMessageInfo.From}");
    Console.Writeline($"To: {mboxMessageInfo.To}");
    Console.Writeline($"CC: {mboxMessageInfo.CC}");
    Console.Writeline($"Bcc: {mboxMessageInfo.Bcc}");
}
```

### **Configuring the load options when reading messages from MBOX** 

The following features will allow you to specify various options related to loading and processing messages:

- MailStorageConverter.MboxMessageOptions property - Gets or sets email load options when parsing an Mbox storage.

- MboxrdStorageReader.ReadNextMessage(EmlLoadOptions options) method - EmlLoadOptions parameter specifies options when reading message from Mbox storage.

**Code sample**

```cs
var reader = new MboxrdStorageReader(fileName, new MboxLoadOptions());
// Read messages preserving tnef attachments.
var eml = reader.ReadNextMessage(new EmlLoadOptions {PreserveTnefAttachments = true});
MailStorageConverter.MboxMessageOptions(new EmlLoadOptions {PreserveTnefAttachments = true});
// Convert messages from mbox to pst preserving tnef attachments.
var pst = MailStorageConverter.mboxToPst("Input.mbox", "Output.pst");
```

## **Setting Preferred Text Encoding when Loading Mbox Files for Reading**

Encoding option is available for MboxrdStorageReader class. This provides additional options for loading the mbox file and ensures that messages with the encoded content will be correctly read and processed.. The following code snippet shows how you can set text encoding that satisfies your needs:

```cs
var reader = new MboxrdStorageReader("sample.mbox", new MboxLoadOptions() { PreferredTextEncoding = Encoding.UTF8});
var message = reader.ReadNextMessage();
```

## **Writing Messages**

The [MboxrdStorageWriter](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxrdstoragewriter/) class provides the facility to write new messages to Thunderbird mail storage file. To write messages:

1. Open the Thunderbird storage file in *FileStream*.
1. Create an instance of the [MboxrdStorageWriter](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxrdstoragewriter/) class and pass the above stream to the constructor.
1. Prepare a new message using the [MailMessage](https://reference.aspose.com/email/net/aspose.email/mailmessage/) class.
1. Call the [WriteMessage()](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxrdstoragewriter/writemessage/#writemessage/) method and pass the above [MailMessage](https://reference.aspose.com/email/net/aspose.email/mailmessage/) instance to add the message to Thunderbird storage.
1. Close all streams.

The following code snippet shows you how to write messages to Thunderbird mail storage.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Thunderbird-CreateNewMessagesToThunderbird-WritingNewMessagesToThunderbird.cs" >}}

## **Getting Total Number of Messages from MBox File**

The [MboxrdStorageReader](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxrdstoragereader/) class provides the capability to read the number of items available in an MBox file. This can be used to develop applications for showing the progress of activity while processing such a file.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Thunderbird-GetNumberOfItemsFromMBox-GetNumberOfItemsFromMBox.cs" >}}

## **Get Current Message Size**

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Thunderbird-GetCurrentMessageSize-GetCurrentMessageSize.cs" >}}s

## **Extract Messages from MBOX by Identifiers**

The [MboxStorageReader](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxstoragereader/#mboxstoragereader-class) class includes the [EnumerateMessageInfo()](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxstoragereader/enumeratemessageinfo/) method, which enables you to iterate through each message in an MBOX file. By using this method, it becomes possible to extract individual messages without the need to traverse the entire storage repeatedly. This improves performance and reduces processing time.

The [MboxMessageInfo](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxmessageinfo/#mboxmessageinfo-class) class provides the [EntryId](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxmessageinfo/entryid/) property, which provides access to unique identifiers for each message in the MBOX file. This identifier can be stored in a database or used as a reference to quickly find and extract specific messages when needed.

The [ExtractMessage(string id)](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxstoragereader/extractmessage/) method in the [MboxStorageReader](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxstoragereader/#mboxstoragereader-class) class enables developers to extract messages based on their unique EntryId. With the [ExtractMessage(string id)](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxstoragereader/extractmessage/) method, you can leverage the stored EntryId to retrieve the corresponding message and perform additional operations with it.

The following code sample demonstrates how to extract messages from an MBOX file using identifiers:

```cs
MboxStorageReader reader = MboxStorageReader.CreateReader("my.mbox", new MboxLoadOptions());

foreach (MboxMessageInfo msgInfo in reader.EnumerateMessageInfo())
{
    MailMessage eml = reader.ExtractMessage(msgInfo.EntryId, new EmlLoadOptions());
}
```

## **Converting MBOX to PST Preserving or Removing a Signature**

To remove the signature from a file during the process of conversion, set the [MboxToPstConversionOptions.RemoveSignature](https://reference.aspose.com/email/net/aspose.email.storage/mboxtopstconversionoptions/removesignature/) property to *true*.

The following code sample shows how to utilize this property:

```cs
var pstDataStream = new MemoryStream();
var personalStorage = PersonalStorage.Create(pstDataStream, FileFormatVersion.Unicode);
MailStorageConverter.MboxToPst(new MboxrdStorageReader(new FileStream(fileName, FileMode.Open, FileAccess.Read), new MboxLoadOptions()),
personalStorage,
    "Inbox",
new MboxToPstConversionOptions() { RemoveSignature = true });
```