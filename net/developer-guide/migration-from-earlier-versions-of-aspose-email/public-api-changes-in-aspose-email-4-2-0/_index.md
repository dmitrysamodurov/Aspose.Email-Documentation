---
title: Public API Changes in Aspose.Email 4.2.0
type: docs
weight: 70
url: /net/public-api-changes-in-aspose-email-4-2-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.
## **Adds EWSClient.Send(MailMessage message, FollowUpOptions messageOptions) method**
Sends the message with additional options
## **Adds FollowUpOptions.Categories property**
Gets or sets string that represents list of the categories, separated by semicolon
## **Adds FollowUpOptions.VotingButtons property**
Gets or sets string that represents list of the voting buttons names, separated by semicolon
## **Adds FollowUpManager.SetOptions(MapiMessage message, FollowUpOptions options) and FollowUpManager.GetOptions(MapiMessage message) methods**
Gets and sets the additional follow-up options for a message.

FollowUpManager.SetFlag(MapiMessage message, FollowUpOptions options) and FollowUpManager.GetFlag(MapiMessage message) marked as obsolete.
Please use GetOptions(MapiMessage message) and SetOptions(MapiMessage message, FollowUpOptions options) methods instead
## **Adds FollowUpManager.AddVotingButton(MapiMessage message, string displayName) method**
Adds the voting button in MapiMessage
## **Adds FollowUpManager.RemoveVotingButton(MapiMessage message, string displayName) method**
Removes the specified voting button in MapiMessage
## **Adds FollowUpManager.ClearVotingButtons(MapiMessage message) method**
Removes the voting buttons in MapiMessage
## **Adds FollowUpManager.GetVotingButtons(MapiMessage message) method**
Get the available message voting buttons
## **Adds MapiTask.Attachments property**
Get the collection of MapiAttacments in MapiTask
