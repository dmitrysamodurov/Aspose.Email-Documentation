---
title: Working with Appointments
type: docs
weight: 20
url: /net/working-with-appointments/
---

## **Load and Save an Appointment in ICS Format**

The [Appointment](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/) class in Aspose.Email for .NET can be used to load an appointment in ICS format as well as create a new appointment and save it to a disk in ICS format. In this article, we first create an appointment and save it to a disk in ICS format, and then we load it.

### **Create an Appointment and Save to a Disk in MSG or ICS Format**

Following steps are required to create an appointment and save it to a disk.

1. Create an instance of the [Appointment](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/) class and initialize it with this constructor.
1. Pass the following arguments in the above constructor
   1. Location
   1. Summary
   1. Description
   1. Start Date
   1. End Date
   1. Organizer
   1. Attendees
1. Call the [Save()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/save/#save/) method and specify the file name and format in the arguments.

The appointment can be opened in Microsoft Outlook or any program that can load an ICS file. If the file is opened in Microsoft Outlook it automatically adds the appointment in the Outlook calendar.

The following code snippet shows you how to create and save an appointment to a disk in ICS or MSG format.

```cs
// For complete examples and data files, please go to https://github.com/aspose-email/Aspose.Email-for-.NET

// Create and initialize an instance of the Appointment class
Appointment appointment = new Appointment(
    "Meeting Room 3 at Office Headquarters",// Location
    "Monthly Meeting",                      // Summary
    "Please confirm your availability.",    // Description
    new DateTime(2015, 2, 8, 13, 0, 0),     // Start date
    new DateTime(2015, 2, 8, 14, 0, 0),     // End date
    "from@domain.com",                      // Organizer
    "attendees@domain.com");                // Attendees

// Save the appointment to disk in ICS format            
appointment.Save(fileName + ".ics", new AppointmentIcsSaveOptions());
Console.WriteLine("Appointment created and saved to disk successfully.");

// Save the appointment to disk in MSG format
appointment.Save(fileName + ".msg", new AppointmentMsgSaveOptions(););
Console.WriteLine("Appointment created and saved to disk successfully.");
```

### **Create an Appointment with HTML Content**

You can specify alternative representations of the event's description in different content types using the X-ALT-DESC header. It allows recipients of the iCalendar file to choose the representation that best suits their needs. For example, you may include a plain text description using the "text/plain" content type and an HTML description using the "text/html" content type. The X-ALT-DESC header is added for each alternative representation. To create an appointment with HTML content, set the [HtmlDescription](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/htmldescription/#appointmenthtmldescription-property) property.

Try the following code sample to create an appointment with alternative HTML description:

1. Create a new instance of the Appointment class.
2. Provide the necessary parameters to the Appointment constructor:
   - Specify the location of the appointment.
   - Set the start date and time.
   - Set the end date and time.
   - Specify the organizer.
   - Specify the attendee.
3. Set the [HtmlDescription](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/htmldescription/#appointmenthtmldescription-property) property of the appointment object, indicating that the description is in HTML format.
4. Set the Description property of the appointment object to an HTML-formatted string, enclosed within a multiline string:
   - The HTML markup includes a <style> block defining a CSS class named "text" with font styles.
   - The HTML body contains a paragraph tag <p> with the CSS class "text", and the actual invitation message.
5. The appointment object is now ready, and you can perform further operations or save it as an iCalendar file.

```cs
var appointment = new Appointment("Bygget 83",
    DateTime.UtcNow, // start date
    DateTime.UtcNow.AddHours(1), // end date
    new MailAddress("TintinStrom@from.com", "Tintin Strom"), // organizer
    new MailAddress("AinaMartensson@to.com", "Aina Martensson")) // attendee
{
    HtmlDescription = @"
    <html>
     <style type=""text/css"">
      .text {
             font-family:'Comic Sans MS';
             font-size:16px;
            }
     </style>
    <body>
     <p class=""text"">Hi, I'm happy to invite you to our party.</p>
    </body>
    </html>"
};
```

### **Load an Appointment in ICS Format**

To load an appointment in ICS format, the following steps are required:

1. Create an instance of the [Appointment](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/) class.
1. Call the [Load()](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/load/#load/) method by providing the path of the ICS file.
1. Read any property to get any information from the appointment (ICS file).

The following code snippet shows you how to load an appointment in ICS format.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-SMTP-AppointmentInICSFormat-LoadAppointment.cs" >}}

## **Load and Convert an ICS File to a Message Format**

The API allows you easily convert an Appointment to a message object. The following code example shows how to convert an appointment request into a MailMessage or MapiMessage:

```cs
var appointment = Appointment.Load("appRequest.ics");

var eml = appointment.ToMailMessage();
var msg = appointment.ToMapiMessage();
```

## **Read Multiple Events from ICS File**

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-ReadMultilpleEventsFromICS-ReadMultilpleEventsFromICS.cs" >}}

## **Write Multiple Events to ICS File**

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Exchange_EWS-WriteMultipleEventsToICS-WriteMultipleEventsToICS.cs" >}}

## **Create a Draft Appointment Request**

It was shown in our earlier articles how to create and save an appointment in ICS format. It is often required to create an Appointment request in a Draft mode, so as the basic information is added and then the same draft Appointment be forwarded to other users for necessary changes according to individual uses. In order to save an Appointment in a Draft mode, the [MethodType](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/methodtype/) property of Appointment class should be set to [AppointmentMethodType.Publish](https://reference.aspose.com/email/net/aspose.email.calendar/appointmentmethodtype/). The following code snippet shows you how to create a draft appointment request.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-DraftAppointmentRequest-DraftAppointmentRequest.cs" >}}

### **Draft Appointment Creation from Text**

The following code snippet shows you how to create a draft appointment from Text. 

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-DraftAppointmentCreation-DraftAppointmentCreation.cs" >}}

## **Set Participants Status of Appointment Attendees**

Aspose.Email for .NET API lets you set the status of appointment attendees while formulating a reply message. This adds the PARTSTAT property to the ICS file.

{{< gist "aspose-com-gists" "6e5185a63aec6fd70d83098e82b06a32" "Examples-CSharp-Email-SetParticipantStatusOfAppointmentAttendees-SetParticipantStatusOfAppointmentAttendees.cs" >}}

## **Customize Product Identifier for ICalendar**

Aspose.Email for .NET API allows to get or set the product identifier that created iCalendar object.

{{< gist "aspose-com-gists" "522d47278b8ca448dc1d7eb97193322c" "Examples-CSharp-Email-ChangeProdIdOfICS-1.cs" >}}

## **Determine the Appointment Version**

To determine the version of an appointment, you can use the [Appointment.Version](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/version/#appointmentversion-property) property of the [Appointment](https://reference.aspose.com/email/net/aspose.email.calendar/appointment/#appointment-class) class. This property assists to determine which version their files are based on, ensuring integration with other systems and apps.

The following code sample shows how to implement this property in your project:

```cs
var app = Appointment.Load("meeting.ics");

if (app.Version == 1.0)
{
    // do something
}
```