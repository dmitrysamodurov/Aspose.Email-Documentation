---
title: Public API Changes in Aspose.Email 3.7.0
type: docs
weight: 20
url: /net/public-api-changes-in-aspose-email-3-7-0/
---

{{% alert color="primary" %}} 

These page list public API changes that were introduced in Aspose.Email 3.7.0. It includes new and obsolete public methods, as well as a description of any changes in the behavior of the API that may affect existing code.

{{% /alert %}} 
## **Calendar support using EWS**
The EWS Client has been enhanced to include functionality of creating, fetching, updating, listing and cancelling appointments. Following new methods have been introduced:

- Aspose.Email.Exchange.IEWSClient.CreateAppointment
- Aspose.Email.Exchange.IEWSClient.FetchAppointment
- Aspose.Email.Exchange.IEWSClient.UpdateAppointment
- Aspose.Email.Exchange.IEWSClient.ListAppointments
- Aspose.Email.Exchange.IEWSClient.CancelAppointment
## **New Namespace Aspose.Email.Google added**
A new Aspose.Email.Google namespace has been added, while the old Aspose.Email.Services.Google.GmailClient class has been marked as obsolete.
## **MapiCalendar.RemainderSet and MapiCalendar.RemainderDelta added**
The MapiCalendar class has been further enhanced with 2 new fields which makes it possible now to set reminders using MapiCalendar class.
## **Appointment.Attachments collection available now**
Appointment class has been further modified to support adding/retrieving attachments.
