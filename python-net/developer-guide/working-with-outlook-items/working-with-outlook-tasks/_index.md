---
title: Working with Outlook Tasks
type: docs
weight: 110
url: /python-net/working-with-outlook-tasks/
---


## **Creating, Saving and Reading Tasks**
Aspose.Email for .NET allows you to create Outlook tasks and save them to MSG format. The MapiTask class provides a number of properties such as Percentcomplete, Estimatedeffort, ActualEffort, History, LastUpdate, and others, to accommodate and set information required for an Outlook task. This article shows how to create, save and read a MapiTask from disc. To create and save a task to disc:

1. Instantiate a new object of the MapiContact class.
1. Enter task property information.
1. Save the task to disc in MSG format.

The following code snippet shows you how to create, save and read Tasks.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookMSGs-CreatingAndSavingOutlookTask-CreatingAndSavingOutlookTask.py" >}}
### **Reading a MapiTask**
The MapiContact class object is used to cast the MapiMessage object that loads a task from disc as MSG format. The following code snippet shows you how to reading a MapiTask.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookMSGs-LoadingContactFromMSG-LoadingContactFromMSG.py" >}}
### **Reading a VToDo Task**
Google Tasks exported in iCalendar format as VToDo events can be loaded using the MapiTask class as shown in the following code sample. The following code snippet shows you how to reading a VToDo Task.



{{< gist "aspose-email" "9e8fbeb51a8cbc4129dc71ca8cd55f0b" "Examples-CSharp-Outlook-ReadingVToDoTask-ReadingVToDoTask.cs" >}}
### **Adding Reminder Information to a MapiTask**
Similar to Microsoft Outlook, Aspose.Email can add reminder information to a MapiTask. The following code snippet shows you how to adding reminder information to a MapiTask.

{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookMSGs-AddReminderInformationToMapiTask-AddReminderInformationToMapiTask.py" >}}
### **Adding Recurrence to MapiTask**
Aspose.Email allows to create a recurring task where the recurrence can be daily, weekly, monthly, or yearly. The following code snippet shows you how to creating a task with different recurrence types.

{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookMSGs-AddRecurrenceToMapiTask-AddRecurrenceToMapiTask.py" >}}
