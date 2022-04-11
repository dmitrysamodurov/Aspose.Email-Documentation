---
title: Working with Messages in a PST File
type: docs
weight: 100
url: /python-net/working-with-messages-in-a-pst-file/
---


## **Adding Messages to PST Files**
Create a New PST File and Add Subfolders showed how to create a PST file and add a subfolder to it. With Aspose.Email you can add messages to subfolders of a PST file that you have created or loaded. This article adds two messages from disk to the Inbox subfolder of a PST. Use the PersonalStorage and FolderInfo classes to add messages to PST files. To add messages to a PST file's Inbox folder:

1. Create an instance of the FolderInfo class and load it with the contents of the Inbox folder.
1. Add messages from disk to the Inbox folder by calling the FolderInfo.AddMessage() method. The FolderInfo class exposes the AddMessages method that enables to add large number of messages to the folder, reducing I/O operations to disc and improving performance. A complete example can be found below, in Adding Bulk Messages.

The code snippets below shows how to add messages to a PST subfolder called Inbox.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-AddMessagesToPSTFiles-AddMessagesToPSTFiles.py" >}}
### **Adding Bulk Messages**
Adding individual messages to a PST implies more I/O operations to disc and hence may slow down performance. For improved performance, messages can be added to the PST in bulk mode to minimize I/O operations. The AddMessages(IEnumerable<MapiMessage> messages) method allows you to define a range of message be added to the PST for improved performance and can be used as in the following scenarios. In addition, the MessageAdded event occurs when a message is added to the folder.
### **Loading Messages from Disc**
The following code snippet shows you how to loading messages from disc.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-AddingBulkMessagesWithImprovedPerformance-AddingBulkMessages.cs" >}}
### **IEnumerable Implementation**
The following code snippet shows you how to IEnumerable Implementation.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-AddingBulkMessagesWithImprovedPerformance-IEnumerableImplementation.cs" >}}
### **Adding Messages from Other PST**
For adding messages from the another PST, use the FolderInfo.EnumerateMapiMessages() method that returns IEnumerable<MapiMessage>. The following code snippet shows you how to add messages from other PST.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-AddMessagesFromOtherPST-AddMessagesFromOtherPST.py" >}}
## **Get Messages Information from an Outlook PST File**
In Read Outlook PST File and Get Folders and Subfolders Information, we discussed loading an Outlook PST file and browse its folders to get the folder names and the number of messages in them. This article explains how to read all the folders and subfolders in the PST file and display the information about messages, for example, subject, sender, and recipients. The Outlook PST file may contain nested folders. To get message information from these, as well as the top-level folders, use a recursive method to read all the folders. The following code snippet shows you how to reads an Outlook PST file and display the folder and message contents recursively.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-GetMessagesInformation-GetMessagesInformation.py" >}}
## **Extracting Messages Form PST Files**
This article shows how to read Microsoft Outlook PST files and extract messages. The messages are then saved to disk in MSG format. The article also shows how to extract a specific number of messages from a PST file. Use a recursive method to browse all the folders (including any nested folders) and call the PersonalStorage.ExtractMessage() method to get Outlook messages into an instance of the MapiMessage class. After that, call the MapiMessage.Save() method to save the message to either disk or stream in MSG format. The following code snippet shows you how to extract messages from PST file is give below.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-WorkingWithOutlookStorageFiles-AddMessagesFromOtherPST-AddMessagesFromOtherPST.py" >}}
### **Saving Messages Directly from PST to Stream**
To save messages from a PST file directly to stream, without extracting the MsgInfo for messages, use the SaveMessageToStream() method. The following code snippet shows you how to save messages directly from PST to stream.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-SaveMessagesDirectlyFromPSTToStream-SaveMessagesDirectlyFromPSTToStream.cs" >}}
### **Extracting n Number of Messages from a PST File**
The following code snippet shows you how to extract a given number of messages from a PST. Simply provide the index for the first message, and the total number of messages to be extracted.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-ExtractNumberOfMessages-ExtractNumberOfMessages.py" >}}
## **Delete Messages from PST Files**
Add Messages to PST Files showed how to add messages to PST files. It is, of course, also possible to delete items (contents) from a PST file and it may also be desirable to delete messages in bulk. Items from a PST file can be deleted using the FolderInfo.DeleteChildItem() method. The API also provides FolderInfo.DeleteChildItems() method to delete items in bulk from the PST file.
### **Deleting Messages from PST Files**
This articles shows how to Use the FolderInfo class to access specific folders in a PST file. To delete messages from the Sent subfolder of a previously loaded or created PST file:

1. Create an instance of the FolderInfo class and load it with the contents of the sent subfolder.
1. Delete messages from the Sent folder by calling the FolderInfo.DeleteChildItem() method and passing the MessageInfo.EntryId as a parameter. The following code snippet shows you how to delete messages from a PST file's Sent subfolder.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-DeleteMessagesFromPSTFile-DeleteMessagesFromPSTFile.py" >}}
### **Delete Items in Bulk from PST File**
Aspose.Email API can be used to delete items in bulk from a PST file. This is achieved using the DeleteChildItems() method which accepts a list of Entry ID items referring to the items to be deleted. The following code snippet shows you how to delete Items in bulk from PST file.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-DeleteBulkItemsFromPst-DeleteBulkItemsFromPst.py" >}}
## **Search Messages and Folders in a PST by Criterion**
Personal Storage (PST) files can contain a huge amount of data and searching for data that meets a specific criteria in such large files needs to include multiple check points in the code to filter the information. With the PersonalStorageQueryBuilder class, Aspose.Email makes it possible to search for specific records in a PST based on a specified search criteria. A PST can be searched for messages based on search parameters such as sender, receiver, subject, message importance, presence of attachments, message size, and even message ID. The PersonalStorageQueryBuilder can also be used to search for subfolders.
### **Searching Messages and Folders in PST**
The following code snippet shows you how to use the PersonalStorageQueryBuilder class to search for contents in a PST based on different search criteria. For example, it shows searching a PST based on:

- Message importance.
- Message class.
- Presence of attachments.
- Message size.
- Unread messages.
- Unread messages with attachments, and
- folders with specific subfolder name.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-SearchMessagesAndFoldersInPST-SearchMessagesAndFoldersInPST.cs" >}}
### **Searching for a String in PST with the Ignore Case Parameter**
The following code snippet shows you how to search for a string in PST with the ignore case parameter.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-SearchingStringInPSTWithIgnoreCaseParameter-SearchingStringInPSTWithIgnoreCaseParameter.py" >}}
## **Move Items to Other Folders of PST File**
Aspose.Email makes it possible to move items from a source folder to another folder in the same Personal Storage (PST) file. This includes:

- Moving a specified folder to a new parent folder.
- Moving a specified messages to a new folder.
- Moving the contents to a new folder.
- Moving subfolders to a new parent folder.

The following code snippet shows you how to move items such as messages and folders from a source folder to another folder in the same PST file.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-MoveItemsToOtherFolders-MoveItemsToOtherFolders.py" >}}
## **Updating Message Properties in a PST File**
It's sometimes required to update certain properties of messages such as changing the subject, marking message importance and similarly others. Updating a message in a PST file, with such changes in the message properties, can be achieved using the FolderInfo.ChangeMessages method. This article shows how to update messages in bulk in a PST file for changes in the properties. The following code snippet shows you how to update properties of messages in bulk mode for multiple messages in a PST file.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-UpdateBulkMessagesInPSTFile-UpdateBulkMessagesInPSTFile.cs" >}}
## **Updating Custom Properites in a PST File**
Sometimes its required to mark items that are processed with in the PST file. Aspose.Email API allows to achieve this using the MapiProperty and MapiNamedProperty. The following methods are helpful in achieving this.

- ctor MapiNamedProperty(long propertyTag, string nameIdentifier, Guid propertyGuid, byte[] propertyValue)
- ctor MapiNamedProperty(long propertyTag, long nameIdentifier, Guid propertyGuid, byte[] propertyValue)
- FolderInfo.ChangeMessages(MapiPropertyCollection updatedProperties) - changes all messages in folder
- PersonalStorage.ChangeMessage(string entryId, MapiPropertyCollection updatedProperties) - change message properties



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-PST-UpdatePSTCustomProperites-UpdatePSTCustomProperites.cs" >}}
## **Extract Attachments without Extracting Complete Message**
Aspose.Email API can be used to extract attachments from PST messages without extracting the complete message first. The ExtractAttachments method of IEWSClient can be used to do this. The following code snippet shows you how to extract attachments without extracting complete message.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-ExtractAttachmentsFromPSTMessages-ExtractAttachmentsFromPSTMessages.cs" >}}
## **Adding Files to PST**
Microsoft Outlook's key functionality is managing emails, calendars, tasks, contacts and journal entries. In addition, files can also be added to a PST folder and the resulting PST keeps record of the documents added. Aspose.Email provides the facility to add files to a folder in the same way in addition to adding messages, contacts, tasks and journal entries to PST. The following code snippet shows you how to add documents to a PST folder using Aspose.Email.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-AddFilesToPST-AddFilesToPST.py" >}}
