---
title: Convert ICS to EML
type: docs
weight: 60
url: /net/converting-between-formats/convert-ics-to-other-formats
---


Converting ICS files to other formats like EML, MSG, or PST offers several advantages. Firstly, it allows for better compatibility with different email clients and systems, making it easier to share and access calendar information. Second, it enables users to backup and store their calendar data in a more versatile and easily accessible format. [Aspose.Email for .NET](https://products.aspose.com/email/net/) provides a powerful and efficient solution for converting ICS files to various formats. With its comprehensive API, developers can easily integrate this functionality into their applications, allowing users to seamlessly convert their calendar data with minimal effort. Additionally, Aspose.Email for .NET offers extensive documentation and support, making it a reliable and user-friendly tool for handling email conversion tasks.   

## **Convert ICS to EML**

To convert an ICS file to EML format, Aspose.Email for .NET provides several tools. For a calendar event or appointment representation, it has the [Appointment](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/#appointment-class) class. This class provides a structured way to store and manage information related to appointments, such as start and end times, location, description, attendees, recurrence patterns, and more. With the Appointment class, users can create, update, and retrieve appointment details programmatically. Then, to include a calendar appointment from an ICS file within an email message, you can use the [AlternateView]() class which adds the appointment as an alternate view, so that the resulting EML file could preserve its details in a format that can be viewed and managed by email clients that support multiple content views. The following code sample demonstrates the process of ICS to EML conversion in C# with the tools provided by Aspose.Email for .NET:

1. Load the ICS file to be converted using the [Calendar.Appointment.Load](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load_3) method.
2. Create a new [MailMessage](https://reference.aspose.com/email/net/aspose.email/mailmessage/#mailmessage-class) object to hold the converted data. 
3. Add the appointment from the ICS file to the EML as an alternate view using the [RequestApointment()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/requestapointment/#requestapointment) method. 
4. Save the EML file with the converted data using the [Save](https://reference.aspose.com/email/net/aspose.email/mailmessage/save/#save_3) method with the [EmlSaveOptions](https://reference.aspose.com/email/net/aspose.email/emlsaveoptions/emlsaveoptions/#emlsaveoptions-constructor) specifying the save type as EmlFormat. 


```cs
// load the ICS file to be converted
var ics = Calendar.Appointment.Load("My File.ics");
// create an EML
var eml = new MailMessage();
// add appointment to EML
eml.AlternateViews.Add(ics.RequestApointment());
// save the EML
eml.Save("Saved File.eml", new EmlSaveOptions(MailMessageSaveType.EmlFormat));
```

## **Convert ICS to EMLX**

To convert an ICS file to EMLx format, follow the instructions from [Convert ICS to EML](#convert-ics-to-eml) article and save the .emlx file as shown in the following line of code:

```cs
// save as a EMLX
eml.Save("Saved File.emlx", new EmlSaveOptions(MailMessageSaveType.EmlxFormat));
```

## **Convert ICS to HTML**

In case you need to view your calendar events and appointments in a visually appealing and interactive format directly in a web browser without the need for specific calendar application, convert them to HTML format. Aspose.Email for .NET provides a powerful set of tools for converting ICS files to HTML format. You can load ICS files, create a new MailMessage object to store the appointment details, add the appointment as an alternate view to the MailMessage, and then save the resulting HTML file with the specified format. The following code sample demonstrates the conversion process using Aspose.Email:

1. Load the ICS file to be converted using the [Calendar.Appointment.Load](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load_3) method.
2. Create a new [MailMessage](https://reference.aspose.com/email/net/aspose.email/mailmessage/#mailmessage-class) object to hold the converted data. 
3. Add the appointment from the ICS file to the EML as an alternate view using the [RequestApointment()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/requestapointment/#requestapointment) method. 
4. Save the EML file with the converted data using the [Save](https://reference.aspose.com/email/net/aspose.email/mailmessage/save/#save_3) method with the [HtmlSaveOptions](https://reference.aspose.com/email/net/aspose.email/htmlsaveoptions/#htmlsaveoptions-class) to provide formatting options for the saved HTML file. In this specific case, the [HtmlFormatOptions.WriteHeader](https://reference.aspose.com/email/net/aspose.email/htmlformatoptions/#htmlformatoptions-enumeration) is used to include the HTML header in the output file, while [HtmlFormatOptions.RenderCalendarEvent](https://reference.aspose.com/email/net/aspose.email/htmlformatoptions/#htmlformatoptions-enumeration) is used to render any calendar events contained in the EML message in a format suitable for display. 

```cs
// load the ICS file to be converted
var ics = Aspose.Email.Calendar.Appointment.Load("My File.ics");
// create an EML
var eml = new MailMessage();
// add appointment to EML
eml.AlternateViews.Add(ics.RequestApointment());
// save EML as a HTML
eml.Save("Saved File.html", new HtmlSaveOptions { HtmlFormatOptions = HtmlFormatOptions.WriteHeader | HtmlFormatOptions.RenderCalendarEvent });
```

Use other values and properties of the [HtmlFormatOptions](https://reference.aspose.com/email/net/aspose.email/htmlformatoptions/#htmlformatoptions-enumeration) enumeration and [HtmlSaveOptions](https://reference.aspose.com/email/net/aspose.email/htmlsaveoptions/#htmlsaveoptions-class) class to set format options as required.


## **Convert ICS to MBOX**

MBOX is a common file format supported by a lot of email clients including Thunderbird. It is widely used for archival and backup purposes. To convert an ICS file to MBOX format, Aspose.Email for .NET offers the [MboxrdStorageWriter](https://reference.aspose.com/email/net/aspose.email.storage.mbox/mboxrdstoragewriter/#mboxrdstoragewriter-class) class to create a new MboxrdStorageWriter object, which is used to write messages in MBOX format. The following code sample demonstrates the process of ICS to MBOX conversion. It loads an ICS file, creates an EML message, adds the appointment details from the ICS file to the EML message, and then writes the EML message to an MBOX storage file.

1. Load the ICS file to be converted using the [Calendar.Appointment.Load](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load_3) method.
2. Create a new [MailMessage](https://reference.aspose.com/email/net/aspose.email/mailmessage/#mailmessage-class) object to hold the converted data. 
3. Add the appointment from the ICS file to the EML as an alternate view using the [RequestApointment()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/requestapointment/#requestapointment) method.
4. Create a new FileStream object to represent the MBOX file named "Saved File.mbox". The FileMode.Create parameter indicates that if the file already exists, it should be overwritten.
5. Create a new MboxrdStorageWriter object with parameters: the FileStream object and a boolean value (false in this case) indicating that the storage should not append to an existing file.
6. Add the EML message (eml) to the storage (mboxStorage) by writing the message content in MBOX format to the MBOX file specified.


```cs
// load the ICS file to be converted
var ics = Aspose.Email.Calendar.Appointment.Load("My File.ics");
// create an EML
var eml = new MailMessage();
// add appointment to EML
eml.AlternateViews.Add(ics.RequestApointment());
// create an MBOX storage
using var mboxStorage = new MboxrdStorageWriter(new FileStream("Saved File.mbox", FileMode.Create), false);
// add EML to MBOX storage
mboxStorage.WriteMessage(eml);
```


## **Convert ICS to MHTML**

Similarly to the conversion described in the [Convert ICS to HTML](#convert-ics-to-html) article, converting appointments or calendar data to MHTML format involves loading the target ICS file, creating an EML message, incorporating the appointment into it. The critical step involves saving the EML message as MHTML specifying format options. The following code sample demonstrates the representation of all these steps in the conversion process using Aspose.Email for .NET library:

1. Load the ICS file to be converted using the [Calendar.Appointment.Load](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load_3) method.
2. Create a new [MailMessage](https://reference.aspose.com/email/net/aspose.email/mailmessage/#mailmessage-class) object to hold the converted data. 
3. Add the appointment from the ICS file to the EML as an alternate view using the [RequestApointment()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/requestapointment/#requestapointment) method.
4. Save the EML file with the converted data using the [Save](https://reference.aspose.com/email/net/aspose.email/mailmessage/save/#save_3) method with [MhtSaveOptions](https://reference.aspose.com/email/net/aspose.email/mhtsaveoptions/#mhtsaveoptions-class) to provide saving options for the MHTML file. In this specific case, the [MhtFormatOptions.WriteHeader](https://reference.aspose.com/email/net/aspose.email/mhtformatoptions/#mhtformatoptions-enumeration) is used to include the email message header in the output file, while [MhtFormatOptions.RenderCalendarEvent](https://reference.aspose.com/email/net/aspose.email/mhtformatoptions/#mhtformatoptions-enumeration) is used to render any calendar events contained in the EML message in a format suitable for display.


```cs
// load the ICS file to be converted
var ics = Aspose.Email.Calendar.Appointment.Load("My File.ics");
// create an EML
var eml = new MailMessage();
// add appointment to EML
eml.AlternateViews.Add(ics.RequestApointment());
// save EML as a MHTML
eml.Save("Saved File.mht", new MhtSaveOptions{MhtFormatOptions = MhtFormatOptions.WriteHeader | MhtFormatOptions.RenderCalendarEvent});
```

This approach ensures that the converted MHTML file retains the calendar event details and formatting, enabling efficient sharing and viewing across various platforms and email clients.

Feel free to use other values and properties of the [MhtFormatOptions](https://reference.aspose.com/email/net/aspose.email/mhtformatoptions/#mhtformatoptions-enumeration) enumeration and [MhtSaveOptions](https://reference.aspose.com/email/net/aspose.email/mhtsaveoptions/#mhtsaveoptions-class) class to set format options as required.

## **Convert ICS to MSG**

Converting ICS (iCalendar) files to MSG format is reasonable for better compatibility with Microsoft Outlook and other email clients, as MSG files are commonly used for storing email messages, appointments, and other Outlook-related data. Aspose.Email for .NET provides powerful tools for performing this conversion seamlessly. The following code sample demonstrates how to load an ICS file, manipulate its content, and save it as an MSG file without losing any data or formatting:

1. Load the ICS file ("My File.ics") using the [Calendar.Appointment.Load()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load_3) and create an [Appointment](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/#appointment-class) object from the calendar data stored in the file.
2. Specify the path and file name where you want to save the converted MSG file e.g. "Saved File.msg".
3. Specify the save format for the output file. In the code snippet, the [AppointmentSaveFormat.Msg](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/save/) parameter indicates that the appointment data should be saved in MSG format.
4. Call the [Save](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/save/#save_4) method on the Appointment object to convert and save the loaded appointment data from the ICS file to an MSG file at the specified location.

```cs
// load the ICS file to be converted
// save ICS as a MSG
Aspose.Email.Calendar.Appointment.Load("My File.ics").Save("Saved File.msg", AppointmentSaveFormat.Msg);
```


## **Convert ICS to OFT**

Aspose.Email can help you create reusable email templates from ICS files that can be easily customized and shared across different platforms and email clients. The process involves loading ICS files and saving them as MSG files with further conversion to OFT format. For this purpose, Aspose.Email provides the following functionality:

- [Calendar.Appointment](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/#appointment-class): Represents an appointment in a calendar. The [Load()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load_3) method is used to load appointment data from various sources, such as ICS files, and the [Save](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/save/#save_4) method is used to save the appointment data to different formats.
  
- [MapiMessage](https://reference.aspose.com/email/net/aspose.email.mapi/mapimessage/#mapimessage-class): Represents a message in the Outlook messaging API (MAPI) format. It is used to work with Outlook messages and properties.
  
- [SaveOptions](https://reference.aspose.com/email/net/aspose.email/saveoptions/#saveoptions-class): Provides options for saving MAPI messages. In this case, [SaveOptions.DefaultOft](https://reference.aspose.com/email/net/aspose.email/saveoptions/defaultoft/) specifies the default options for saving the message as an Outlook template file (.oft).

The code sample below demonstrates the use of these components in the conversion process: 

1. Create a new MemoryStream object named msgStream to store the appointment data in memory.
2. Load the appointment data from the ICS file "My File.ics" using the Appointment.Load() method. Save the appointment data to the msgStream object in MSG format using the Save() method.
3. Load the appointment data from the msgStream memory stream by creating a new MapiMessage object using the [MapiMessage.Load()](https://reference.aspose.com/email/net/aspose.email.mapi/mapimessage/load/#load) method, specifying the msgStream memory stream object.
4. Save the loaded MapiMessage data as an Outlook template file ("Saved File.oft") in Unicode format using the [Save()](https://reference.aspose.com/email/net/aspose.email.mapi/mapimessage/save/#save_3) method with the provided format options SaveOptions.DefaultOft.

```cs
// load the ICS file to be converted
// save ICS as a MSG
using var msgStream = new MemoryStream();
Aspose.Email.Calendar.Appointment.Load("My File.ics").Save(msgStream, AppointmentSaveFormat.Msg);
// save MSG as an OFT
MapiMessage.Load(ms).Save("Saved File.oft", SaveOptions.DefaultOft);
```

## **Convert ICS to OST**

Aspose.Email offers a straightforward solution for converting files with calendar data to storage format for better compatibility with Microsoft Outlook and other email clients. It provides functionality to load an ICS file, save it as a MSG file, then open an OST file, access calendar folders within the file, and easily add MSG files to the calendar folder. The following code sample demonstrates how this functionality works for ICS to OST conversion:

1. Create a MemoryStream (msgStream) to store the appointment data.
2. Load the appointment data from an ICS file named "My File.ics" using the [Appointment.Load()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load_3) method and save it to the msgStream in MSG format with the [Appointment.Save](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/save/#save_4) method.
3. Load the Personal Storage file named "Saved File.ost" using the [FromFile](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/fromfile/#fromfile) method of the [PersonalStorage](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/#personalstorage-class) class.
4. Retrieve the calendar folder from the Personal Storage file with the [PersoanlStorage.GetPredefinedFolder](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/getpredefinedfolder/) method.
5. Use the [FolderInfo.AddMessage](https://reference.aspose.com/email/net/aspose.email.storage.pst/folderinfo/addmessage/) method to add the appointment message stored in the msgStream to the calendar folder in the OST file.

```cs
// load the ICS file to be converted
// save ICS as a MSG
using var msgStream = new MemoryStream();
Aspose.Email.Calendar.Appointment.Load("My File.ics").Save(msgStream, AppointmentSaveFormat.Msg);
// open an OST file
using var pst = PersonalStorage.FromFile("Saved File.ost");
// get a calendar folder
var calendarFolder = pst.GetPredefinedFolder(StandardIpmFolder.Appointments);
// add MSG to the calendar folder
calendarFolder.AddMessage(MapiMessage.Load(msgStream));
```

## **Convert ICS to PST**

Converting ICS files to PST format involves a few steps. Aspose.Email provides classes and methods to perform these steps with ease. The [Appointment](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/#appointment-class) class represents a calendar item. The [Load()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load_3) method of this class allows you to load calendar data from various sources, such as ICS files, and the [Save](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/save/#save_4) method is used to save the calendar data to different formats.

The [PersonalStorage](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/#personalstorage-class) class is a key component used for working with Outlook Personal Storage files. It allows you to create, access, and manipulate PST files. 

The following code sample demonstrates the use of these components in the conversion process:

1. Create a new MemoryStream to hold the appointment data.
2. Load the appointment data from an ICS file named "My File.ics" using the [Appointment.Load()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load_3) method and save it to the msgStream in MSG format with the [Appointment.Save](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/save/#save_4) method.
3. Create a new PST file with the file name "Saved File.pst" using the [PersonalStorage.Create](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/create/#create_4) method.
4. Create a calendar folder within the PST file to store appointments using the [CreatePredefinedFolder](https://reference.aspose.com/email/net/aspose.email.storage.pst/personalstorage/createpredefinedfolder/#createpredefinedfolder) method with the folder type set to StandardIpmFolder.Appointments.
5. Add the appointment message loaded from the MemoryStream to the calendar folder within the PST file using the [FolderInfo.AddMessage](https://reference.aspose.com/email/net/aspose.email.storage.pst/folderinfo/addmessage/) method.

```cs
// load the ICS file to be converted
// save ICS as a MSG
using var msgStream = new MemoryStream();
Aspose.Email.Calendar.Appointment.Load("My File.ics").Save(msgStream, AppointmentSaveFormat.Msg);
// create a PST file
using var pst = PersonalStorage.Create("Saved File.pst", FileFormatVersion.Unicode);
// create a calendar folder
var calendarFolder = pst.CreatePredefinedFolder("Calendar", StandardIpmFolder.Appointments);
// add MSG to the calendar folder
calendarFolder.AddMessage(MapiMessage.Load(msgStream));
```



