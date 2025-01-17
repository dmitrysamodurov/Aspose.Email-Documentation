---
title: Importing Email
ArticleTitle: Importing Email
type: docs
weight: 170
url: /net/importing-email/
---


## **VSTO**
Below is the code to import email using VSTO Outlook.

``` cs

  string FilePath = @"E:\Aspose\Aspose VS VSTO\Sample Files\ImportEmail.msg";

 Outlook.MailItem email = (Outlook.MailItem)Application.Session.OpenSharedItem(FilePath);       

```
## **Aspose.Email**
Below is the code to import email using aspose.email for .NET.

``` cs

  string FilePath = @"E:\Aspose\Aspose VS VSTO\Sample Files\ImportEmail.msg";  

 // loading with default options

  load from msg

   MailMessage eml = MailMessage.Load(FilePath, new MsgLoadOptions());

```
## **Download Source Code**
- [CodePlex](https://asposeemailvsto.codeplex.com/SourceControl/latest#Code)
- [GitHub](https://github.com/aspose-email/Aspose.Email-for-.NET/tree/master/Plugins/Aspose.Email%20Vs%20VSTO%20Outlook/Code%20Comparison%20of%20Common%20Features/Import%20Email)
- [Code.MSDN](https://code.msdn.microsoft.com/Code-Comparison-of-common-4e0f39b8/view/SourceCode#content)
## **Download Running Example**
- [CodePlex](https://asposeemailvsto.codeplex.com/releases/view/620910)
- [GitHub](https://github.com/aspose-email/Aspose.Email-for-.NET/releases/tag/AsposeEmailVsVSTOv1.2)
- [Code.MSDN](https://code.msdn.microsoft.com/Code-Comparison-of-common-4e0f39b8)
