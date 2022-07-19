---
title: Migrating from Aspose.Network for .NET to Aspose.Email for .NET
type: docs
weight: 10
url: /net/migrating-from-aspose-network-for-net-to-aspose-email-for-net/
---

## **Overview**
Aspose.Network for .NET 6.8 and earlier versions consisted of several network protocols, email, and Exchange related features. We split it into two different products based on features: 

1. Aspose.Email for .NET: a commercial product that contains email message storage and processing related features.
1. Aspose.Network for .NET: a free product that contained the network protocols and social services network related features. (Discontinued from March, 2012)

The two products' main features are summarized below.
### **Aspose.Email for .NET Features**
- EML, MSG and MHT file handling.
- Read PST and OST files and extract items including messages, contacts, appointments, etc.
- Create, load, edit and save messages.
- Convert message from one format to another.
- Manage emails on POP3, IMAP and Exchange Servers.
- Send emails and meeting invites using SMTP and Exchange Servers.
- SSL authentication support for POP3, IMAP, SMTP and Exchange Servers.
- Verify email address.
- Generate recurrence pattern using iCalendar specifications.
### **Aspose.Network for .NET Features**
- Connect and manage files using FTP, FTPS or SFTP protocol.
- Query WhoIs servers.
- Send and receive ICMP messages.
- Send DNS queries.
- Connect using proxy.
- Twitter client.
## **Changes Required for Migration**
### **Download Aspose.Email and Add References**
We have moved all the email processing related classes to the Aspose.Email for .NET product. To use these:

1. Uninstall Aspose.Network for .NET 6.8 or any previous version.
1. Download and install the latest version of Aspose.Email for .NET.
1. Remove references to Aspose.Network.dll and add references to Aspose.Email.dll in your projects.
### **Update Namespaces**
Use Aspose.Email and its related namespaces instead of Aspose.Network. Below is a list of the namespaces that are now part of Aspose.Email:

**C# - Old Code**

``` cs

 using Aspose.Network.Exchange;

using Aspose.Network.Formats;

using Aspose.Network.Imap;

using Aspose.Network.Mail;

using Aspose.Network.Mime;

using Aspose.Network.Outlook;

using Aspose.Network.Pop3;

using Aspose.Network.Verify;



```

**C# - Code after Migration**

``` cs

 using Aspose.Email.Exchange;

using Aspose.Email.Formats;

using Aspose.Email.Imap;

using Aspose.Email.Mail;

using Aspose.Email.Mime;

using Aspose.Email.Outlook;

using Aspose.Email.Pop3;

using Aspose.Email.Verify;



```

**VB.NET - Old Code**

``` cs

 Imports Aspose.Network.Exchange

Imports Aspose.Network.Formats

Imports Aspose.Network.Imap

Imports Aspose.Network.Mail

Imports Aspose.Network.Mime

Imports Aspose.Network.Outlook

Imports Aspose.Network.Pop3

Imports Aspose.Network.Verify



```

**VB.NET - Code after Migration**

``` cs

 Imports Aspose.Email.Exchange

Imports Aspose.Email.Formats

Imports Aspose.Email.Imap

Imports Aspose.Email.Mail

Imports Aspose.Email.Mime

Imports Aspose.Email.Outlook

Imports Aspose.Email.Pop3

Imports Aspose.Email.Verify



```

{{% alert color="primary" %}} 

Please note that when using FTP, DNS, proxy or Twitter features, you also need to download and install Aspose.Network for .NET 6.9 or later. In this case, you may add references to both Aspose.Email for .NET and Aspose.Network for .NET. 

{{% /alert %}} 
### **Update Fully Qualified Class Names**
If you have not used fully qualified class names anywhere, [updating the namespaces](#update-namespaces) is enough to migrate the code. If fully qualified class Names are used, each occurrence must be updated to get the class name from Aspose.Email.

**C# - Old Code**

``` cs

 Aspose.Network.Mail.MailMessage message = new Aspose.Network.Mail.MailMessage();



```

**C# - Code After Migration**

``` cs

 Aspose.Email.Mail.MailMessage message = new Aspose.Email.Mail.MailMessage();



```

**VB.NET - Old Code**

``` cs

 Dim message As New Aspose.Network.Mail.MailMessage



```

**VB.NET - Code After Migration**

``` cs

 Dim message As New Aspose.Email.Mail.MailMessage



```

{{% alert color="primary" %}} 

To make the process easier, do a global find/replace in Visual Studio and replace all occurrences of “Aspose.Network.” with “Aspose.Email.”. Take care when doing this as some namespaces, for example Aspose.Network.Ftp, are still part of Aspose.Network for .NET. 

{{% /alert %}} 
### **Update Licensing Code**
Aspose.Network for .NET is a free (and discontinued) product and does not require any licensing code. However, a license is required for Aspose.Email. To set it:

**C# - Old Code**

``` cs

 Aspose.Network.License licEmail = new Aspose.Network.License();



```

**C# - Code After Migration**

``` cs

 Aspose.Email.License licEmail = new Aspose.Email.License();



```

**VB.NET - Old Code**

``` cs

 Dim licEmail As New Aspose.Network.License



```

**VB.NET - Code After Migration**

``` cs

 Dim licEmail As New Aspose.Email.License



```
