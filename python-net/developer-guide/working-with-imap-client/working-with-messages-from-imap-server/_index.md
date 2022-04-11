---
title: Working with Messages from IMAP Server
type: docs
weight: 70
url: /python-net/working-with-messages-from-imap-server/
---


## **Listing MIME Message IDs from Server**
ImapMessageInfo provides the MIME MessageId for message identification without extracting the complete message. The following code snippet shows you how to list MIME messageId.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-ListingMIMEMessageIdInImapMessageInfo-ListingMIMEMessageIdInImapMessageInfo.py" >}}
## **Listing Messages from Server Recursively**
The IMAP protocol supports listing messages recursively from a mailbox folder. This helps list messages from subfolders of a folder as well. The following code snippet shows you how to list messages recursively.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-ListingMessagesRecursively-ListingMessagesRecursively.py" >}}
## **Fetch Messages from Server and Save to disc**
The ImapClient class can fetch messages from an IMAP server and save the messages in EML format to a local disk. The following steps are required to save the messages to disk:

1. Create an instance of the ImapClient class.
1. Specify hostname, username and password in the ImapClient constructor .
1. Select the folder using SelectFolder() method.
1. Call the ListMessages method to get the ImapMessageInfoCollection object.
1. Iterate through the ImapMessageInfoCollection collection, call the SaveMessage() method and provide the output path and file name.

The following code snippet shows you how to fetch email messages from a server and save them.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-FetchEmailMessageFromServer-FetchEmailMessageFromServer.py" >}}
## **Saving Messages in MSG Format**
In the above example, the emails are saved in EML format. To save emails in MSG format, the ImapClient.FetchMessage() method needs to be called. It returns the message in an instance of the MailMessage class. The MailMessage.Save() method can then be called to save the message to MSG. The following code snippet shows you how to save messages in MSG Format.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-SavingMessageFromIMAPServer-SavingMessageFromIMAPServer.py" >}}
## **Listing Messages with Paging Support**
In scenarios, where the email server contains a large number of messages in mailbox, it is often desired to list or retrieve the messages with paging support. Aspose.Email API's ImapClient lets you retreive the messages from the server with paging support.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-ListingMessagesWithPagingSupport-ListingMessagesWithPagingSupport.py" >}}
## **Retrieving Extra Parameters as Summary Information**


{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-RetreiveExtraParametersAsSummaryInformation-RetreiveExtraParametersAsSummaryInformation.py" >}}
