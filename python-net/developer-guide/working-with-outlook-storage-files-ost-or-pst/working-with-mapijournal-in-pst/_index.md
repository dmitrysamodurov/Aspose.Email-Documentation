---
title: Working with MapiJournal in PST
type: docs
weight: 70
url: /python-net/working-with-mapijournal-in-pst/
---


## **Adding MapiJournal to PST**
Create a New PST File and Add Subfolders showed how to create a PST file and add a subfolder to it. With Aspose.Email you can add MapiJournal to hte Journal subfolder of a PST file that you have created or loaded. Below are the steps to add MapiJournal to a PST:

1. Create a MapiJournal object
1. Set the MapiJournal properties using a constructor and methods.
1. Create a PST using the PersonalStorage.Create() method.
1. Create a pre-defined folder (Journals) at the root of the PST file by accessing the root folder and then calling the AddMapiMessageItem() method.

The following code snippet shows you how to create a MapiJournal and then add it to the journal folder of a newly created PST file.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookStorageFiles-CreateNewMapiJournalAndAddToPST-CreateNewMapiJournalAndAddToPST.py" >}}
## **Adding Attachments to MapiJournal**
The following code snippet shows you how to add attachments to MapiJournal.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-AddAttachmentsToMapiJournal-AddAttachmentsToMapiJournal.cs" >}}
