---
title: Public API Changes in Aspose.Email 5.0.0
type: docs
weight: 150
url: /net/public-api-changes-in-aspose-email-5-0-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.

**Class Aspose.Email.Outlook.Pst.MessageStore**

Method Aspose.Email.Outlook.Pst.MessageStore.ChangeDisplayName(System.String)
Method Aspose.Email.Outlook.Pst.MessageStore.SetProperty(Aspose.Email.Outlook.MapiProperty)
Property Aspose.Email.Outlook.Pst.MessageStore.DisplayName
Property Aspose.Email.Outlook.Pst.MessageStore.Properties
Property Aspose.Email.Outlook.Pst.PersonalStorage.Store

**Obsoleted**

Property PersonalStorage.DisplayName - Please use PersonalStorage.Store.DisplayName instead
Property PersonalStorage.MessageStoreProperties - Please use PersonalStorage.Store.Properties instead
Method PersonalStorage.ChangeDisplayName(string newName) - Please use PersonalStorage.Store.ChangeDisplayName method instead
