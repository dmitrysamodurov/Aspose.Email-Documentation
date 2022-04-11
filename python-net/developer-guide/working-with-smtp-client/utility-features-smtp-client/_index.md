---
title: Utility Features - SMTP Client
type: docs
weight: 30
url: /python-net/utility-features-smtp-client/
---


## **Listing Extension Servers using Smtp Client**
Aspose.Email's Pop3Client lets you retrieve the server extensions that a server supports such as IDLE, UNSELECT,QUOTA, etc. This helps in identifying the availability of an extension before using the client for that particular functionality. The GetCapabilities() method returns the supported extension types in the form of a string array.
### **Retrieving Server Extensions**
The following code snippet shows you how to retrieve server extensions.



{{< gist "aspose-email" "356f0e128b9d45a7ee779fc813eb87e5" "Examples-SMTP-RetrieveSMTPServerExtensions-RetrieveSMTPServerExtensions.py" >}}
