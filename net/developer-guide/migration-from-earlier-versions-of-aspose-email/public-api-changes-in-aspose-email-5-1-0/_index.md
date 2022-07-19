---
title: Public API Changes in Aspose.Email 5.1.0
type: docs
weight: 160
url: /net/public-api-changes-in-aspose-email-5-1-0/
---


The following is a list of any changes made to the public API such as added, renamed, removed or deprecated members as well as any non-backward compatible change made to Aspose.Email for .NET. If you have concerns about any change listed, please raise it on the Aspose.Email support forum.
## **Added APIs**
Class Aspose.Email.OAuth.BaseTokenProvider
Class Aspose.Email.OAuth.OutlookTokenProvider
Method Aspose.Email.Exchange.IEWSClient.ResolveContacts(System.String,Aspose.Email.Exchange.ExchangeListContactsOptions)
Method Aspose.Email.Mime.HeaderCollection.GetDecodedValue(System.String)
Method Aspose.Email.OAuth.BaseTokenProvider.Dispose
Method Aspose.Email.OAuth.BaseTokenProvider.GetAccessToken
Method Aspose.Email.OAuth.BaseTokenProvider.GetAccessToken(System.Boolean)
Method Aspose.Email.OAuth.OutlookTokenProvider.GetInstance(System.String,System.String,System.String)
Property Aspose.Email.License.IsLicensed
Property Aspose.Email.Mail.MailMessage.HtmlBodyText
Property Aspose.Email.OAuth.BaseTokenProvider.ClientId
Property Aspose.Email.OAuth.BaseTokenProvider.ClientSecret
Property Aspose.Email.OAuth.BaseTokenProvider.RefreshToken
Property Aspose.Email.Outlook.MapiConversionOptions.PreserveOriginalAddresses
## **Removed APIs**
Class Aspose.Email.Common.Commands.BaseAsyncCommand
Event Aspose.Email.Common.Commands.BaseAsyncCommand.ExecutionCompleted
Method Aspose.Email.Common.Commands.BaseAsyncCommand.#ctor
Method Aspose.Email.Common.Commands.BaseAsyncCommand.Cancel
Method Aspose.Email.Common.Commands.BaseAsyncCommand.Dispose
Method Aspose.Email.Common.Commands.BaseAsyncCommand.ExecuteAsync
Method Aspose.Email.OAuth.GoogleTokenProvider.Dispose
Method Aspose.Email.OAuth.GoogleTokenProvider.GetAccessToken
Method Aspose.Email.OAuth.GoogleTokenProvider.GetAccessToken(System.Boolean)
Method Aspose.Email.Outlook.AppointmentMailMessageInterpretor.LoadMessageHeader(Aspose.Email.Mail.MailMessage,Aspose.Email.Outlook.MapiMessage)
Property Aspose.Email.OAuth.GoogleTokenProvider.ClientId
Property Aspose.Email.OAuth.GoogleTokenProvider.ClientSecret
Property Aspose.Email.OAuth.GoogleTokenProvider.RefreshToken
