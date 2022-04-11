---
title: Programming with Thunderbird
type: docs
weight: 80
url: /python-net/programming-with-thunderbird/
---


## **Reading Messages**
Mozilla Thunderbird is an open source, cross-platform email client, developed by the Mozilla Foundation. It stores emails in its own file structure, managing messages indices and subfolders through proprietary file formats. Aspose.Email can work with Thunderbird mail storage structures. The MboxrdStorageReader class lets developers read messages from Mozilla Thunderbird’s mail storage file. This article shows how to read the messages from Thunderbird email storage:

1. Open the Thunderbird’s storage file
1. Create an instance of the MboxrdStorageReader class and pass the above stream to the constructor.
1. Call read_next_message() to get the first message.
1. Use the same read_next_message() in a while loop to read all the messages.
1. Close all the streams.

The following code snippet shows you how to read all the messages from a Thunderbird mail storage.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-Thunderbird-ReadMessagesFromThunderbird-ReadMessagesFromThunderbird.py" >}}
## **Writing Messages**
The MboxrdStorageWriter class provides the facility to write new messages to Thunderbird’s mail storage file. To write messages:

1. Open the Thunderbird storage file in FileStream.
1. Create an instance of the MboxrdStorageWriter class and pass the above stream to the constructor.
1. Prepare a new message using the MailMessage class.
1. Call the write_message() method and pass the above MailMessage instance to add the message to Thunderbird storage.
1. Close all streams.

The following code snippet shows you how to writes messages to Thunderbird’s mail storage.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-Thunderbird-CreateNewMessagesToThunderbird-CreateNewMessagesToThunderbird.py" >}}
## **Getting Total Number of Messages from MBox File**
The MboxrdStorageReader class provides the capability to read the number of items available in an MBox file. This can be used to develop applications for showing progress of activity while processing such a file.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-Thunderbird-GetNumberOfItemsFromMBox-GetNumberOfItemsFromMBox.py" >}}
## **Get Current Message Size**
{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-Thunderbird-GetCurrentMessageSize-GetCurrentMessageSize.py" >}}
