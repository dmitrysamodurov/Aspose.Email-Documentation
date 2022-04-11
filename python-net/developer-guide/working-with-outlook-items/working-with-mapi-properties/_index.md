---
title: Working with MAPI Properties
type: docs
weight: 60
url: /python-net/working-with-mapi-properties/
---


## **Accessing and Setting Outlook MAPI Property**
The MapiProperty class represents a MAPI property, which contains:

- Name: a string that represents the property's name.
- Tag: a long that represents the property's tag.
- Data: a byte array which represents the property's data.
### **Getting MAPI Property using the MAPI Property Tag**
To get MAPI properties:

1. Create an instance of MapiMessage by loading from files or stream.
1. Get the MapiProperty from MapiMessage.Properties by MapiPropertyTag keys.
1. Get the Data of the MapiProperty by method GetX.

The following code snippet shows you how to get MAPI property using the MAPI property tag.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookMSGs-GetMapiProperty-GetMapiProperty.py" >}}
### **Setting MAPI Properties**
The following code snippet shows you how to set MAPI properties.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookMSGs-SetMapiProperties-SetMapiProperties.py" >}}



where the definition of convertDateTime method is as follow:



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-WorkingWithOutlookMSGs-ConvertDateTime-ConvertDateTime.py" >}}
