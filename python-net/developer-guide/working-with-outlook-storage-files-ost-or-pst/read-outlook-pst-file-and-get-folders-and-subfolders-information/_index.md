---
title: Read Outlook PST File and Get Folders and SubFolders Information
type: docs
weight: 30
url: /python-net/read-outlook-pst-file-and-get-folders-and-subfolders-information/
---


Aspose.Email for .NET provides an API for reading Microsoft Outlook PST files. You can load a PST file from disk or stream into an instance of the PersonalStorage class and get the information about its contents, for example folders, subfolders and messages. The API also provides the capability to include search folders while traversing for messages from the PST folders.
## **Loading a PST File**
An Outlook PST file can be loaded in an instance of the PersonalStorage class. The following code snippet shows you how to load the PST file.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-ReadingOSTFiles-ReadingOSTFiles.py" >}}
## **Displaying PST Information**
After loading the PST file in the PersonalStorage class, you can get the information about the file display name, root folder, subfolders and messages count. The following code snippet shows you how to display the name of PST file, folders and number of messages in the folders.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-DisplayInformationOfPSTFile-DisplayInformationOfPSTFile.py" >}}

## **Get user-created folders only**

PST/OST files may contain folders which were created by a user, i.e. excluding all standard IPM folders. Aspose.Email provides the ability to access only user-created folders by using the *only_folders_created_by_user* property of the [PersonalStorageQueryBuilder](https://reference.aspose.com/email/python-net/aspose.email.storage.pst/personalstoragequerybuilder/#personalstoragequerybuilder-class) class. You can set the *only_folders_created_by_user* property to True to get only user-created folders. The following code snippet demonstrates how you can use the *only_folders_created_by_user* property in your project:

```python
import aspose.email as ae

pst = ae.storage.pst.PersonalStorage.from_file("my.pst")

query_builder = ae.storage.pst.PersonalStorageQueryBuilder()
query_builder.only_folders_created_by_user.equals(True)

folders = pst.root_folder.get_sub_folders(query_builder.get_query())

for folder in folders:
    print(f"Folder: {folder.display_name}")
```

## **Checking whether the folder is in a predefined folder**

The "get_predefined_type" method of the [FolderInfo](https://reference.aspose.com/email/python-net/aspose.email.storage.pst/folderinfo/#folderinfo-class) class allows you to find out if a folder within a PST file is a standard folder. Standard (or predefined) folders, as opposed to user-created folders, are folders that are created by Outlook when you add an email account such as Inbox, Sent Items, Drafts, Deleted Items, Calendar, Tasks, Notes etc. 

The code sample below demonstrates how to use this method in a project. If set to True, it returns the predefined type for the top-level parent folder. This determines whether the current folder is a subfolder of a predefined folder. If set to False, it returns the predefined type for the current folder.


```python
import aspose.email as ae

pst = ae.storage.pst.PersonalStorage.from_file("my.pst")

folders = pst.root_folder.get_sub_folders()

for folder in folders:
    print(f"Folder: {folder.display_name}")
    print(f"Is predefined: {folder.get_predefined_type(False) != ae.storage.pst.StandardIpmFolder.UNSPECIFIED}")
    print("-----------------------------------")
```
## **Getting and adding a standard RSS Feeds folder in PersonalStorage**

Aspose.Email provides functionality to retrieve a reference to a RSS Feeds predefined folder, allowing developers to programmatically access and manipulate the RSS feeds stored in an Outlook PST file. By obtaining a reference to the "RSS Feeds folder," developers can work with the RSS feed data, which may include subscribing to new feeds, updating existing feeds, or extracting information from the feeds.

The value of RssFeeds in the StandardIpmFolder enum would typically represent the predefined folder type specifically designed for storing RSS feeds within an Outlook PST file. Using this enum value, developers can target and interact with the "RSS Feeds folder" programmatically. The following code samples will demonstrate how to implement this feature into your project:

```python
import aspose.email as ae

pst = ae.storage.pst.PersonalStorage.from_file("my.pst")

rss_folder = pst.get_predefined_folder(ae.storage.pst.StandardIpmFolder.RSS_FEEDS)
```
To add an RSS Feeds folder, use the following code snippet:

```python
import aspose.email as ae

pst = ae.storage.pst.PersonalStorage.from_file("my.pst")

rss_folder = pst.create_predefined_folder("RSS Feeds", ae.storage.pst.StandardIpmFolder.RSS_FEEDS)
```

## **Parsing Searchable Folders**


```python
import aspose.email as ae

pst = ae.storage.pst.PersonalStorage.from_file("my.pst")

folders = pst.root_folder.get_sub_folders(ae.storage.pst.FolderKind.SEARCH | ae.storage.pst.FolderKind.NORMAL)

# Browse through each folder to display folder name and number of messages
for folder in folders:
    print(f"Folder: {folder.display_name}")
    sub_folders = folder.get_sub_folders(ae.storage.pst.FolderKind.SEARCH | ae.storage.pst.FolderKind.NORMAL)
    for sub_folder in sub_folders:
        print(f"Sub-folder: {folder.display_name}")
```

## **Retrieving Parent Folder Information from MessageInfo**
The following code snippet shows you how to retrieve parent folder information from MessageInfo.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-RetrievingParentFolderInformationFromMessageInfo-RetrievingParentFolderInformationFromMessageInfo.py" >}}
