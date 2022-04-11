---
title: Filter Messages from Server using IMAP Client
type: docs
weight: 30
url: /python-net/filter-messages-from-server-using-imap-client/
---


The ImapClient class provides the ListMessages() method which gets all the messages from a mailbox. To get only messages which match some condition, use the overloaded ListMessages() method which takes MailQuery as an argument. The MailQuery class provides various properties for specifying the conditions, for example, date, subject, sender, recipient and so on. The first example illustrates how to filter messages based on date and subject. We also show how to filter on other criteria and how to build more complex queries. The API also provides the capability to apply case-sensitive searching criteria to match exact filtering criteria. The API also allows to specify the search string encoding for filtering messages from the mailbox.
## **Filtering Messages from Mailbox**
1. Connect and log in to an IMAP server
1. Create an instance of the MailQuery and set the properties
1. Call the ImapClient.ListMessages(MailQuery query) method and pass the MailQuery with the parameters to get filtered messages only.

The following code snippet shows you how to connect to an IMAP mailbox and get messages that arrived to day and have the word "newsletter" in the subject.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-FilteringMessagesFromIMAPMailbox-FetchEmailMessageFromServer.py" >}}
## **Case-Sensitive Emails Filtering**
The following code snippet shows you how to use case-sensitive emails filtering.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-IMAP-CaseSensitiveEmailsFiltering-.py" >}}
