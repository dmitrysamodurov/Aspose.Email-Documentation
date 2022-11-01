---
title: Working with Contacts in PST File
type: docs
weight: 40
url: /net/working-with-contacts-in-pst-file/
---


## **Adding Contact to PST**
[Create a New PST File and Add Subfolders](/email/net/create-new-pst-file-and-add-subfolders/#creating-a-new-pst-file-and-add-subfolders) showed how to create a PST file and add a subfolder to it. With Aspose.Email you can add a MapiContact to the Contacts subfolder of a PST file that you have created or loaded. Below are the steps to add MapiContact to a PST:

1. Create a [MapiContact](https://apireference.aspose.com/email/net/aspose.email.mapi/mapicontact) object.
1. Set the [MapiContact properties](https://apireference.aspose.com/email/net/aspose.email.mapi/mapicontact/properties/index) using different constructors and methods.
1. Create a PST using the [PersonalStorage.Create()](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/methods/create/index) method.
1. Create a pre-defined folder (Contacts) at the root of the PST file by accessing the root folder and then calling the [AddMapiMessageItem()](https://apireference.aspose.com/email/net/aspose.email.storage.pst/folderinfo/methods/addmapimessageitem) method.

The following code snippet shows you how to create a MapiContact and then add it to the contacts folder of a newly created PST file.

```csharp
// Create three Contacts 
var contact1 = new MapiContact("Sebastian Wright", "SebastianWright@dayrep.com");
var contact2 = new MapiContact("Wichert Kroos", "WichertKroos@teleworm.us", "Grade A Investment");
var contact3 = new MapiContact("Christoffer van de Meeberg", "ChristoffervandeMeeberg@teleworm.us", "Krauses Sofa Factory", "046-630-4614046-630-4614");

// Contact #4
var contact4 = new MapiContact{NameInfo = new MapiContactNamePropertySet("Margaret", "J.", "Tolle")};
contact4.PersonalInfo.Gender = MapiContactGender.Female;
contact4.ProfessionalInfo = new MapiContactProfessionalPropertySet("Adaptaz", "Recording engineer");
contact4.PhysicalAddresses.WorkAddress.Address = "4 Darwinia Loop EIGHTY MILE BEACH WA 6725";
contact4.ElectronicAddresses.Email1 = new MapiContactElectronicAddress("Hisen1988", "SMTP", "MargaretJTolle@dayrep.com");
contact4.Telephones.BusinessTelephoneNumber = "(08)9080-1183";
contact4.Telephones.MobileTelephoneNumber = "(925)599-3355(925)599-3355";

// Contact #5
var contact5 = new MapiContact{NameInfo = new MapiContactNamePropertySet("Matthew", "R.", "Wilcox")};
contact5.PersonalInfo.Gender = MapiContactGender.Male;
contact5.ProfessionalInfo = new MapiContactProfessionalPropertySet("Briazz", "Psychiatric aide");
contact5.PhysicalAddresses.WorkAddress.Address = "Horner Strasse 12 4421 SAASS";
contact5.Telephones.BusinessTelephoneNumber = "0650 675 73 300650 675 73 30";
contact5.Telephones.HomeTelephoneNumber = "(661)387-5382(661)387-5382";

// Contact #6
var contact6 = new MapiContact
{
    NameInfo = new MapiContactNamePropertySet("Bertha", "A.", "Buell"),
    ProfessionalInfo = new MapiContactProfessionalPropertySet("Awthentikz", "Social work assistant")
};
contact6.PersonalInfo.PersonalHomePage = "B2BTies.com";
contact6.PhysicalAddresses.WorkAddress.Address = "Im Astenfeld 59 8580 EDELSCHROTT";
contact6.ElectronicAddresses.Email1 = new MapiContactElectronicAddress("Experwas", "SMTP", "BerthaABuell@armyspy.com");
contact6.Telephones = new MapiContactTelephonePropertySet("06605045265");

using (PersonalStorage personalStorage = PersonalStorage.Create("SampleContacts_out.pst", FileFormatVersion.Unicode))
{
    var contactFolder = personalStorage.CreatePredefinedFolder("Contacts", StandardIpmFolder.Contacts);
    contactFolder.AddMapiMessageItem(contact1);
    contactFolder.AddMapiMessageItem(contact2);
    contactFolder.AddMapiMessageItem(contact3);
    contactFolder.AddMapiMessageItem(contact4);
    contactFolder.AddMapiMessageItem(contact5);
    contactFolder.AddMapiMessageItem(contact6);
}
```

## **Save contacts information from PST file in MSG Format**
This article explains how to access contact information from an Outlook PST file and save the contact to disk in MSG format. The steps to get the contact information are:

1. Load the PST file in the [PersonalStorage](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage) object.
1. Browse the Contacts folder.
1. Get the contents of the Contacts folder via Loop through the messages.
1. Verify that the [MessageInfo.MessageClass](https://reference.aspose.com/email/net/aspose.email.storage.pst/messageinfo/messageclass/) property value matches the "IPM.Contact".
1. Call the [PersonalStorage.ExtractMessage()](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/methods/extractmessage/index) method to get the [MapiMessage](https://reference.aspose.com/email/net/aspose.email.mapi/mapimessage/) object.
1. Call the MapiMessage.Save() method to save the contact to disk in MSG format.

The following code snippet shows you how to retrieve all the contact information from the PST file and save to disk in MSG format.


```csharp
// Load the Outlook PST file
var pst = PersonalStorage.FromFile("SampleContacts.pst");

// Get the Contacts folder
var contactsFolder = pst.RootFolder.GetSubFolder("Contacts");

// Loop through all the contacts in this folder
foreach (MessageInfo messageInfo in contactsFolder.EnumerateMessages())
{
    if (messageInfo.MessageClass == "IPM.Contact")
    {
        // Get the contact information
        var msg = pst.ExtractMessage(messageInfo);
        
        // Save to disk in msg format
        string contactName = msg.Subject.Replace(":", " ").Replace("\\", " ").Replace("?", " ").Replace("/", " ");
        msg.Save($"{contactName}.msg", SaveOptions.DefaultMsgUnicode);
    }
}
```

## **Save Contacts information from PST file in VCF Format**
This article shows how to access contact information from a Microsoft Outlook PST file and save the contact to disk in vCard (VCF) format. Use the [PersonalStorage](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage) and [MapiContact](https://apireference.aspose.com/email/net/aspose.email.mapi/mapicontact) classes to get contact information from the PST file. To get the contact information:

1. Load the PST file in the [PersonalStorage](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage) class.
1. Browse the Contacts folder.
1. Get the contents of the Contacts folder via Loop through the messages.
1. Verify that the [MessageInfo.MessageClass](https://reference.aspose.com/email/net/aspose.email.storage.pst/messageinfo/messageclass/) property value matches the "IPM.Contact".
1. Call the [PersonalStorage.ExtractMessage()](https://apireference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/methods/extractmessage/index) method to get the [MapiMessage](https://reference.aspose.com/email/net/aspose.email.mapi/mapimessage/) object.
1. Call the [MapiMessage.ToMapiMessageItem()](https://reference.aspose.com/email/net/aspose.email.mapi/mapimessage/tomapimessageitem/) and cast the [IMapiMessageItem](https://reference.aspose.com/email/net/aspose.email.mapi/imapimessageitem/) to [MapiContact](https://reference.aspose.com/email/net/aspose.email.mapi/mapicontact/) type.
1. Call the [MapiContact.Save()](https://reference.aspose.com/email/net/aspose.email.mapi/mapicontact/save/#save_1) method to save the contact to disk in VCard format.

The program below loads a PST file from disk and saves all the contacts to vCard (VCF) format. The VCF files can then be used in any other program that can load the standard vCard contact file. If you open any VCF file in Microsoft Outlook, it looks like the one in the below screenshot.

|![todo:image_alt_text](working-with-contacts-in-pst-file_1.png)|
| :- |
The following code snippet shows you how to export contacts from Outlook PST to vCard (VCF) format.

```csharp
// Load the Outlook PST file
var pst = PersonalStorage.FromFile("SampleContacts.pst");

// Get the Contacts folder
var contactsFolder = pst.RootFolder.GetSubFolder("Contacts");

// Loop through all the contacts in this folder
foreach (MessageInfo messageInfo in contactsFolder.EnumerateMessages())
{
    if (messageInfo.MessageClass == "IPM.Contact")
    {
        // Get the contact information
        var msg = pst.ExtractMessage(messageInfo);
        var contact = (MapiContact)msg.ToMapiMessageItem();

        // Display some contents on screen
        Console.WriteLine("Name: " + contact.NameInfo.DisplayName);

        // Save to disk in VCard format
        string contactName = contact.Subject.Replace(":", " ").Replace("\\", " ").Replace("?", " ").Replace("/", " ");
        contact.Save($"{contactName}.vcf", ContactSaveFormat.VCard);
    }
}
```

See also: [Working with Distribution Lists](/email//net/working-with-distribution-lists-in-pst/)
