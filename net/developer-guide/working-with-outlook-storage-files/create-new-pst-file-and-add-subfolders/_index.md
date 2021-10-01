---
title: Create New PST File and Add SubFolders
type: docs
weight: 10
url: /net/create-new-pst-file-and-add-subfolders/
---


As well as parsing an existing PST file, Aspose.Email provides the means to create a PST file from scratch. This article demonstrates how to create an Outlook PST file and add a subfolder to it.

1. [Creating a new PST file](#creating-a-new-pst-file-and-add-subfolders).
1. [Changing Container class of a folder](#changing-a-folders-container-class).

Use the [PersonalStorage](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage) class to create a PST file at some location on a local disk. To create a PST file from scratch:

1. Create a PST using the [PersonalStorage.Create()](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/methods/create/index) method.
1. Add a sub-folder at the root of the PST file by accessing the Root folder and then calling the [AddSubFolder](https://apireference.aspose.com/email/net/aspose.email.storage.pst/folderinfo/methods/addsubfolder/index) method.

The following code snippet shows you how to create a PST file and add a subfolder called Inbox.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Outlook-CreateNewPSTFileAndAddingSubfolders-CreateNewPSTFileAndAddingSubfolders.cs" >}}
## **Changing a Folder's Container Class**
Sometimes it is necessary to change a folder's folder class. A common example is where messages of different types (appointments, messages, etc.) are added to the same folder. In such cases, the folder class needs to be changed for all elements in the folder to display properly. The following code snippet shows you how to change the container class of a folder in PST for this purpose.



{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Outlook-ChangeFolderContainerClass-ChangeFolderContainerClass.cs" >}}
