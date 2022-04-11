---
title: Working with PST Password Protection Properties
type: docs
weight: 110
url: /python-net/working-with-pst-password-protection-properties/
---


Microsoft Outlook lets users password protect PST files to restrict access to them. Aspose.Email can detect password protection on a PST file. This article shows how to:

- Check for Password Protection of a PST
- Remove/Reset the Password property from the PST
- Setting/Changing PST Password
## **Check for Password protection**
The MapiPropertyTag.PR_PST_PASSWORD value from the MapiPropertyTag class is used to check if a file is password protected. The CRC-32 hash of the password string is stored in the PidTagPstPassword (tag = 0x67ff0003) property in the MessageStore. If this property exists and is nonzero, then the PST is password protected. The following code snippet shows you how to check if the PST is password protected. It also shows how to check whether the provided password is correct or not.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-CheckPasswordProtection-CheckPasswordProtection.cs" >}}
## **Removing/Reseting PR_PST_PASSWORD Property**
Removal of the PR_PST_PASSWORD property cannot be achieved as other properties are removed from a message store. Instead, we need to set its value to zero (0) in order to get it removed. The "Store" property of the PST class allows to access store properties of PST instead of MessageStoreProperties of PST in this case. The following code snippet shows you how to Remove/Reset PR_PST_PASSWORD Property.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-RemovingPaswordProperty-RemovingPaswordProperty.cs" >}}
## **Setting Password on PST Files**
The following code snippet shows you how to set password on PST files.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-SetPasswordOnPST-SetPasswordOnPST.cs" >}}
