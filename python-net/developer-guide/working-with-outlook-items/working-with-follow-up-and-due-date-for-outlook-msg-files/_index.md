---
title: Working with Follow Up and Due Date for Outlook MSG Files
type: docs
weight: 50
url: /python-net/working-with-follow-up-and-due-date-for-outlook-msg-files/
---


A follow up flag marks an email message for some kind of action. Microsoft Outlook lets users flag messages and, in the flag set-up, assign a due date for the follow up. Microsoft Outlook sends a reminder to the recipient to prompt them to follow up the email. Flagging emails and setting due dates programmatically lets software developers automate certain types of emails and help recipients remember to take action. For example, it could be used to send monthly messages to a sales team to remind them to complete their reports; or to send a message to all staff to remind them of a company meeting. Aspose.Email for .NET supports setting follow up flag and due date for the MapiMessage objects using FollowUpManager and FollowUpOptions. There are a number of variants in which the follow up flag can be set on a message. They are all used in the code sample below:

1. Set a follow up flag for a message
1. Add a due date and reminder date to a message
1. Add a flag to a recipient's message.
1. Mark as complete.
1. Remove flag.
1. Read follow up options.
## **Setting a FollowUp flag**
The following code snippet shows you how to set a followUp flag.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-SetFollowUpflag-SetFollowUpflag.cs" >}}
## **Setting Follow Up for Recipients**
The following code snippet shows you how to set follow Up for recipients.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-SetFollowUpForRecipients-SetFollowUpForRecipients.cs" >}}
## **Marking a FollowUp flag as Completed**
The following code snippet shows you how to mark followUp flag as completed.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-MarkFollowUpFlagAsCompleted-MarkFollowUpFlagAsCompleted.cs" >}}
## **Removing a FollowUp flag**
The following code snippet shows you how to remove followUp flag.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-RemoveFollowUpflag-RemoveFollowUpflag.cs" >}}
## **Read followup flag options for a message**
The following code snippet shows you how to read followup flag options for a message.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-ReadFollowupFlagOptionsForMessage-ReadFollowupFlagOptionsForMessage.cs" >}}
