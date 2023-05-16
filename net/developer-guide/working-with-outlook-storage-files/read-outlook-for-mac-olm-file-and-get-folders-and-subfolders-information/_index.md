---
title: Read Outlook for Mac OLM File & Get Folders & SubFolders Information
type: docs
weight: 120
url: /net/read-outlook-for-mac-olm-file-and-get-folders-and-subfolders-information/
---

# **Read MS Outlook for Mac OLM Files**

OLM is a specific file format used by Microsoft Outlook for storing local data such as emails, attachments, notes, calendar data, contacts, tasks, history, and more. OLM files are only compatible with Outlook for Mac and cannot be opened or accessed by Outlook for Windows, which uses the PST file format instead.

Opening OLM format files(Opening-OLM-format-files)
Opening file by constructor(Opening-files-by-constructor)
Opening file using static method FromFile
Getting folders
List of emails
Using EnumerateMessages method
Using EnumerateMapiMessages method
Other useful properties
Extracting emails

## **Opening OLM format files**

OLM format files can be opened in two ways:

- using constructor
- using static FromFile method

There are differences in behavior between these methods. See section below.

### **Opening files by constructor**

To open a file, call constructor of the [OlmStorage](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/) class and pass full file name or stream as an argument to it:

```cs
var fileName = "MyStorage.olm";
var olm = new OlmStorage(fileName);
```

### **Opening files using static method FromFile**

To open a file, use static method [FromFile](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/fromfile/) and pass full file name or stream as an argument to it:

```cs
var fileName = "MyStorage.olm";
var olm = OlmStorage.FromFile(fileName);
```

## **Getting folders**

To access the directory structure of an OLM file, create an instance of the [OlmStorage](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/) class using its constructor and pass in the path to the file.
Once the file is open, access its directory structure using the [FolderHierarchy](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/folderhierarchy/) property. This property returns a list of [OlmFolder](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/) objects, each representing a directory in the OLM file. 
To further explore the directory structure, access the [SubFolders](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/subfolders/) property of each object, which returns a list of its subdirectories. By using these properties, you can navigate through the entire directory hierarchy of the OLM file and access all the directories and subdirectories it contains.

The example below displays the list of all folders in hierarchical order:

```cs
using (var olm = new OlmStorage(fileName))
{
    PrintAllFolders(olm.FolderHierarchy, string.Empty);
}

private void PrintAllFolders(List<OlmFolder> folderHierarchy, string indent)
{
    foreach (var folder in folderHierarchy)
    {
        Console.WriteLine($"{indent}{folder.Name}");
        PrintAllFolders(folder.SubFolders, indent+"-");
    }
}
``` 

When using the [FromFile](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/fromfile/) method to open an OLM file, the [FolderHierarchy](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/folderhierarchy/) property will not be initialized by default and will return null. In this case, call the GetFolders method explicitly to initialize the [FolderHierarchy](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/folderhierarchy/) property and retrieve the list of directories in the OLM file:

```cs
using (var olm = OlmStorage.FromFile(fileName))
{
    var folders = olm.GetFolders();
}
```

Also, it’s possible to get any folder by name:

1. Call [GetFolder](https://reference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/getfolder/) method.
2. Pass folder name as the first argument and value, which shows whether to ignore case sensitivity when searching for a folder, as the second parameter.

```cs
using (var olm = OlmStorage.FromFile(fileName))
{
    // get inbox folder by name
    OlmFolder folder = olm.GetFolder("Inbox", true);
}
```

## **List of emails**

[OlmFolder](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/) class, which represents a folder, has the following methods to get the list of emails:

- [EnumerateMessages]() implements iteration of emails in a folder. In this case, every iteration returns [OlmMessageInfo](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmmessageinfo/) object, which provides short info about email.
- [EnumerateMapiMessages](), also implements iteration of emails in a folder, but in this case, every iteration returns [MapiMessage](https://reference.aspose.com/email/net/aspose.email.mapi/mapimessage/) object, which represents the email itself, with all properties.

### **Using EnumerateMessages method**

```cs
using (var olm = OlmStorage.FromFile(fileName))
{
    var folder = olm.GetFolder("Inbox", true);
    foreach (var messageInfo in folder.EnumerateMessages())
    {
        Console.WriteLine(messageInfo.Subject);
    }
}
```

### **Using EnumerateMapiMessages method**

```cs
using (var olm = OlmStorage.FromFile(fileName))
{
    var folder = olm.GetFolder("Inbox", true);

    foreach (var msg in folder.EnumerateMapiMessages())
    {
        // save message in MSG format
        msg.Save($"{msg.Subject}.msg");
    }
}
```

### **Other useful properties**

The other useful properties of the OlmFolder class are: [HasMessages](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/hasmessages/) and [MessageCount](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/messagecount/) properties, which return the presence of messages in the folder and their count.

```cs
using (var olm = OlmStorage.FromFile(fileName))
{
    var folder = olm.GetFolder("Inbox", true);

    if (folder.HasMessages)
    {
        Console.WriteLine($"Message count: {folder.MessageCount}");
    }
}
```

## **Extracting emails**

[OlmStorage](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/) class has [ExtractMapiMessage](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/extractmapimessage/) method which allows to extract emails. This method receives an [OlmMessageInfo](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmmessageinfo/) object.

```cs
using (var olm = OlmStorage.FromFile(fileName))
{
    var folder = olm.GetFolder("Inbox", true);

    foreach (var messageInfo in folder.EnumerateMessages())
    {
        if (messageInfo.Date == DateTime.Today)
        {
            // Extracts today's messages form Inbox
            var msg = olm.ExtractMapiMessage(messageInfo);
        }
    }
}
```

## **Get Folder Path**

You may also get the folder path of folders in the OML file. Aspose.Email provides [OlmFolder.Path](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/path/) property which returns the folder path. The following code snippet demonstrates the use of [OlmFolder.Path](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/path/) property to get the folder paths in the OML file.

```cs
var storage = new OlmStorage("SampleOLM.olm");
PrintPath(storage, storage.FolderHierarchy);

public static void PrintPath(OlmStorage storage, List<OlmFolder> folders)
{
    foreach (OlmFolder folder in folders)
    {
        // print the current folder path
        Console.WriteLine(folder.Path);

        if (folder.SubFolders.Count > 0)
        {
            PrintPath(storage, folder.SubFolders);
        }
    }
}
```

## **Count the number of items in the folder**

You may also count the number of items in the folder. Aspose.Email provides [OlmFolder.MessageCount](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/messagecount/) property which returns the number of items in the folder. The following code snippet demonstrates the use of [OlmFolder.MessageCount](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmfolder/messagecount/) property to get the number of items in the folders of the OML file.

```cs
var storage = new OlmStorage("SampleOLM.olm");
PrintMessageCount(storage.FolderHierarchy);

public static void PrintMessageCount(List<OlmFolder> folders)
{
    foreach (OlmFolder folder in folders)
    {
        Console.WriteLine("Message Count [" + folder.Name + "]: " + folder.MessageCount);
    }
}
```

### **Get Total Items Count of OlmStorage**

[OlmStorage](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/) class also has GetTotalItemsCount() method which returns the total number of message items contained in the OLM storage.
  
```cs
  using (var olm = new OlmStorage("storage.olm"))
  {
     var count = olm.GetTotalItemsCount();
  }
```

### **Extract messages from OLM by identifiers**
  
Sometimes it is required to extract selected messages by identifiers. For example, your application stores identifiers in a database and extracts a message on demand. This is the efficient way to avoid traversing through the entire storage each time to find a specific message to extract. This feature is available for OLM storages.

The code below shows how to extract messages from OLM by identifiers. 

The code performs the following steps:

1. Initiates a foreach loop to iterate through a list of [OlmMessageInfo](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmmessageinfo/) objects. The loop uses the [EnumerateMessages](https://reference.aspose.com/email/net/aspose.email.storage.pst/folderinfo/enumeratemessages/) method of the olmFolder object to retrieve a list of all messages in the current folder being iterated.
2. The loop extracts the corresponding MapiMessage object from the storage by calling the [ExtractMapiMessage(string id)](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/extractmapimessage/#extractmapimessage_1) method of [OlmStorage](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmstorage/) class, passing in the [EntryId](https://reference.aspose.com/email/net/aspose.email.storage.olm/olmmessageinfo/entryid/) of the current message as a parameter.

The retrieved MapiMessage object can be used to access and manipulate the contents of the message. The loop continues until all messages in the folder have been processed.

```cs
  foreach (OlmMessageInfo msgInfo in olmFolder.EnumerateMessages())
  {
      MapiMessage msg = storage.ExtractMapiMessage(msgInfo.EntryId);
  }
```
