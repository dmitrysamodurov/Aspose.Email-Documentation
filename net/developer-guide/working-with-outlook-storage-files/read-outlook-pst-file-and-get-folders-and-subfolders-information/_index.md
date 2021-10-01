---
title: Read Outlook PST File and Get Folders and SubFolders Information
type: docs
weight: 110
url: /net/read-outlook-pst-file-and-get-folders-and-subfolders-information/
---


Aspose.Email for .NET provides an API for reading Microsoft Outlook PST files. You can load a PST file from disk or stream into an instance of the [PersonalStorage](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage) class and get the information about its contents, for example, folders, subfolders, and messages. The API also provides the capability to include search folders while traversing for messages from the PST folders.
## **Loading a PST File**
An Outlook PST file can be loaded in an instance of the [PersonalStorage](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage) class. The following code snippet shows you how to load the PST file.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Outlook-PST-LoadingPSTFile-LoadingPSTFile.cs" >}}
## **Displaying Folders Information**
After loading the PST file in the [PersonalStorage](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage) class, you can get the information about the file display name, root folder, subfolders and messages count. The following code snippet shows you how to display the name of PST file, folders and number of messages in the folders.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Outlook-PST-DisplayInformationOfPSTFile-DisplayInformationOfPSTFile.cs" >}}
## **Get user-defined folders only**
A PST/OST files may contain folders which were created by the user. Aspose.Email provides the ability to access only user-defined folders by using the [PersonalStorageQueryBuilder.OnlyFoldersCreatedByUser](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstoragequerybuilder/properties/onlyfolderscreatedbyuser) property. You can set the [PersonalStorageQueryBuilder.OnlyFoldersCreatedByUser](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstoragequerybuilder/properties/onlyfolderscreatedbyuser) property to **true** to get only user-defined folders. The following code snippet demonstrates the use of [PersonalStorageQueryBuilder.OnlyFoldersCreatedByUser](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstoragequerybuilder/properties/onlyfolderscreatedbyuser) to get user-defined folders.



{{< gist "aspose-com-gists" "522d47278b8ca448dc1d7eb97193322c" "Examples-CSharp-Outlook-PST-GetFoldersCreatedByUserOnly-1.cs" >}}
## **Parsing Searchable Folders**
A PST/OST may contain searchable folders in addition to the normal type of folders. Aspose.Email provides the [FolderKind](https://apireference.aspose.com/email/net/aspose.email.storage.pst/folderkind) enumerator for specifying the messages from such search folders with [EnumerateFolders](https://apireference.aspose.com/email/net/aspose.email.storage.pst/folderinfo/methods/enumeratefolders/index) and [GetSubFolders](https://apireference.aspose.com/email/net/aspose.email.storage.pst/folderinfo/methods/getsubfolders/index) methods. The following code snippet shows you how to parse searchable folders.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Outlook-ParseSearchableFolders-ParseSearchableFolders.cs" >}}
## **Retrieving Parent Folder Information from MessageInfo**
The following code snippet shows you how to retrieve parent folder information from [MessageInfo](https://apireference.aspose.com/email/net/aspose.email.storage.pst/messageinfo).



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-PST-RetreivingParentFolderInformationFromMessageInfo-RetreivingParentFolderInformationFromMessageInfo.cs" >}}
