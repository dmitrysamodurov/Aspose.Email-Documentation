---
title: Read Outlook for Mac OLM File & Get Folders & SubFolders Information
type: docs
weight: 120
url: /net/read-outlook-for-mac-olm-file-and-get-folders-and-subfolders-information/
---


Aspose.Email for .NET provides an API for reading Outlook for Mac data files in OLM format. You can load an OLM file from the disk into an instance of the [OlmStorage](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/) class and get the information about its contents, for example, folders, subfolders, and messages.

## **Read OLM file**

The following code snippet shows you how to load the OLM file and get its content.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-OLM-LoadAndReadOLMFile-LoadAndReadOLMFile.cs" >}}

## **Extract messages from OLM by Identifiers**

For applications storing identifiers in a database, Aspose.Email offers an efficient way to avoid traversing through the entire storage each time to find a specific message to extract. You can extract selected messages by identifiers using the [ExtractMapiMessage()](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/extractmapimessage/#extractmapimessage_1) method of the [OlmStorage](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/#olmstorage-class) class and the [EntryId](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmmessageinfo/entryid/) property of the [OlmMessageInfo](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmmessageinfo/#olmmessageinfo-class) class.

The code sample below shows how to extract MapiMessage objects from an OlmFolder object:

```cs
foreach (OlmMessageInfo msgInfo in olmFolder.EnumerateMessages())
{
    MapiMessage msg = storage.ExtractMapiMessage(msgInfo.EntryId);
}
```

## **Get Folder Path**

You may also get the folder path of folders in the OML file. Aspose.Email provides [OlmFolder.Path](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/path/) property which returns the folder path. The following code snippet demonstrates the use of [OlmFolder.Path](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/path/) property to get the folder paths in the OML file.

{{< gist "aspose-com-gists" "522d47278b8ca448dc1d7eb97193322c" "Examples-CSharp-Outlook-OLM-GetFolderPathInOLM-1.cs" >}}

## **Count the number of items in the folder**

You may also count the number of items in the folder. Aspose.Email provides [OlmFolder.MessageCount](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/messagecount/) property which returns the number of items in the folder. The following code snippet demonstrates the use of [OlmFolder.MessageCount](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/messagecount/) property to get the number of items in the folders of the OML file.

{{< gist "aspose-com-gists" "522d47278b8ca448dc1d7eb97193322c" "Examples-CSharp-Outlook-OLM-CountItemsInOLMFolder-1.cs" >}}
