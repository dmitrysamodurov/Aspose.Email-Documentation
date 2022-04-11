---
title: Create New PST File and Add SubFolders
type: docs
weight: 10
url: /python-net/create-new-pst-file-and-add-subfolders/
---


As well as parsing an existing PST file, Aspose.Email provides the means to create a PST file from scratch. This article demonstrates how to create an Outlook PST file and add a subfolder to it.

1. Creating a new PST file.
1. Changing Container class of a folder.

Use the PersonalStorage class to create a PST file at some location on a local disk. To create a PST file from scratch:

1. Create a PST using the PersonalStorage.Create() method.
1. Add a sub-folder at the root of the PST file by accessing the Root folder and then calling the AddSubFolder method.

The following code snippet shows you how to create a PST file and add a subfolder called Inbox.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-CreateNewPSTFileAndAddingSubfolders-CreateNewPSTFileAndAddingSubfolders.py" >}}
## **Changing a Folder's Container Class**
Sometimes it is necessary to change a folder's folder class. A common example is where messages of different types (appointments, messages, etc.) are added to the same folder. In such cases, the folder class needs to be changed for all elements in the folder to display properly. The following code snippet shows you how to change the container class of a folder in PST for this purpose.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-ChangeFolderContainerClass-ChangeFolderContainerClass.py" >}}
