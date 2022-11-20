---
title: How to use GraphClient for Microsoft Graph
type: docs
weight: 20
url: /net/how-to-use-graphclient-for-microsoft-graph/
---


## **Working with GraphClient**
Microsoft Graph 
The implementation of Graph Client in Aspose.Email for .NET, allows to access Microsoft Graph from our API.
In the examples below we will create an instance of MS Graph Client, providing the token into it. 
Then, we will examine the main methods to manage folders, update them, copy and delete. Messages, their content and 
attachments can also be accessed or changed with our MS Graph Client. Managing categories, rules, notebooks and overrides is an 
extended feature of Microsoft Graph Client by Aspose.Email, which you will learn with ease. 


### **Create GraphClient Object**
Create [IGraphClient](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient) object to make requests against the service.
After you have a [IGraphClient](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient) that is authenticated, you can begin making calls against the service.

A [GetClient](https://reference.aspose.com/email/net/aspose.email.clients.graph/graphclient/getclient/#getclient_1) method requires an [ITokenProvider](https://reference.aspose.com/email/net/aspose.email.clients/itokenprovider/) implementation instance as the first parameter.

To get the token we'll use [Microsoft Authentication Library (MSAL) for .NET](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet).

The following are the steps to get authorization token.

 - Create an AccessParameters class to store credentials.
 - Add the [Microsoft.Identity.Client nuget package](https://www.nuget.org/packages/Microsoft.Identity.Client) that contains the binaries of the MSAL.NET.
 - Implement an ITokenProvider, and create a method accepting access parameters and using MSAL.NET to get an access token.

To keep the credentials add the following `AccessParameters` class:

```csharp
public class AccessParameters
{
    public string TenantId { get; init; }
    public string ClientId { get; init; }
    public string ClientSecret { get; init; }
    public string UserId { get; init; }
    public Uri Authority => new ($"https://login.microsoftonline.com/{TenantId}");
    public string ApiUrl => "https://graph.microsoft.com/.default";
}
```

Create the `GraphTokenProvider` class that implements an [ITokenProvider](https://reference.aspose.com/email/net/aspose.email.clients/itokenprovider/) interface. Use the [Microsoft.Identity.Client](https://www.nuget.org/packages/Microsoft.Identity.Client) library to get a token.
See the example of such implementation:

```csharp
using Microsoft.Identity.Client;
using Microsoft.Identity.Web;
using Aspose.Email.Clients;

public class GraphTokenProvider : ITokenProvider
{
    private readonly IConfidentialClientApplication _app;
    private readonly string[] _scopes;
    private string? _token;

    public GraphTokenProvider(AccessParameters accessParams)
    {
        _app = ConfidentialClientApplicationBuilder.Create(accessParams.ClientId)
            .WithClientSecret(accessParams.ClientSecret)
            .WithAuthority(accessParams.Authority)
            .Build();

        _app.AddInMemoryTokenCache();

        _scopes = new[] { accessParams.ApiUrl };
    }

    public void Dispose()
    {
        throw new NotImplementedException();
    }

    public OAuthToken GetAccessToken()
    {
        return GetAccessToken(false);
    }

    public OAuthToken GetAccessToken(bool ignoreExistingToken)
    {
        if (!ignoreExistingToken && _token != null)
        {
            return new OAuthToken(_token);
        }

        _token = GetAccessTokenAsync().GetAwaiter().GetResult();
        return new OAuthToken(_token);
    }

    private async Task<string?> GetAccessTokenAsync()
    {
        AuthenticationResult? result;

        try
        {
            result = await _app.AcquireTokenForClient(_scopes)
                .ExecuteAsync();

            Console.WriteLine("Token acquired");
        }
        catch (MsalServiceException ex) when (ex.Message.Contains("AADSTS70011"))
        {
            Console.WriteLine("Scope provided is not supported");
            result = null;
        }

        if (result == null) return null;
        _token = result.AccessToken;
        return result.AccessToken;
    }
```

Next, create an `AccessParameters` class instance:

```csharp
var accessParams = new AccessParameters()
{
    TenantId = "Your Tenant ID",
    ClientId = "Your Client ID",
    ClientSecret = "Your Client Secret",
    UserId = "User's Object ID"
};
```

Finally, create an [ITokenProvider](https://reference.aspose.com/email/net/aspose.email.clients/itokenprovider/) instance and call a [GetClient](https://reference.aspose.com/email/net/aspose.email.clients.graph/graphclient/getclient/#getclient_1) method. Pass the `tokenProvider` as its first parameter and `accessParams.TenantId` as the second one:

```csharp
var tokenProvider = new GraphTokenProvider(accessParams);

using var client = GraphClient.GetClient(tokenProvider, accessParams.TenantId);

client.Resource = ResourceType.Users;
client.ResourceId = accessParams.UserId;
```


## **Manage Folders**
### **List Folders**
By calling [ListFolders](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/listfolders) 
method from Ms Graph Client, its possible to get the list of folders. Each folder has a set of parameters like 
DisplayName, which can be read in [FolderInfo](https://apireference.aspose.com/email/net/aspose.email.clients.activesync.transportlayer/folderinfo) type.

```csharp
var folders = client.ListFolders();

foreach (var folder in folders)
{
    Console.WriteLine(folder.DisplayName);
}
```
### **Update Folder**
To create folder with Ms Graph Client, use [CreateFolder](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/createfolder) 
method. You will get [FolderInfo](https://apireference.aspose.com/email/net/aspose.email.clients.activesync.transportlayer/folderinfo) object 
and the possibility to access DisplayName, ItemId, HasSubFolders and other properties.

```csharp
var folderInfo = client.CreateFolder("FolderName");
folderInfo.DisplayName = "FolderAnotherName";
client.UpdateFolder(folderInfo);
```

### **Copy Folder**
[CopyFolder](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/copyfolder) method is the key method to copy the folder object 
with MS Graph.

```csharp
var folderInfo1 = client.CreateFolder("Folder1");
var folderInfo2 = client.CreateFolder("Folder2");
    
// copy Folder2 to Folder1
client.CopyFolder(folderInfo1.ItemId, folderInfo2.ItemId);
```

### **Move and Delete Folder**
Use [MoveFolder](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/movefolder) method is 
used to move the folder, it accepts newParentId and itemId. [Delete](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/delete) 
method is used to delete method by id.

```csharp
var folderInfo1 = client.CreateFolder("Folder1");
var folderInfo2 = client.CreateFolder("Folder2");
    
// move Folder2 to Folder1
client.MoveFolder(folderInfo1.ItemId, folderInfo2.ItemId);
    
// delete Folder1
client.Delete(folderInfo1.ItemId)
```

## **Manage Messages**
MS Graph Client, implemented in Aspose.Email for .NET provides a set of methos to manage messages and attachments:
* [List](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/listmessages) messages
* [Fetch](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/fetchmessage) message
* [Create](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/createmessage) message
* [Send](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/send) message
* [CopyMessage](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/copymessage) message
* [Move](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/movemessage) message
* [CreateAttachment](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/createattachment)
* [FetchAttachment](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/fetchattachment)
* [DeleteAttachment](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/deleteattachment)
* [ListAttachments](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/listattachments)


### **List Messages**

```csharp
var folders = client.ListFolders();

foreach (var folder in folders)
{
    if (folder.DisplayName.Equals("Inbox"))
    {
        // list messages in inbox
        var inboxMessages = client.ListMessages(folder.ItemId);

        foreach (var messageInfo in inboxMessages)
        {
            Console.WriteLine(messageInfo.Subject);
        }
    }
}
```

### **Fetch Message**

```csharp
var folders = client.ListFolders();

foreach (var folder in folders)
{
    if (folder.DisplayName.Equals("Inbox"))
    {
        // list messages in inbox
        var inboxMessages = client.ListMessages(folder.ItemId);

        if (inboxMessages.Count > 0)
        {
            // fetch the first message in inbox
            var msg = client.FetchMessage(inboxMessages[0].ItemId);
            
            Console.WriteLine(msg.BodyHtml);
        }
        
    }
}
```

### **Create Message**

```csharp
var msg = new MapiMessage(OutlookMessageFormat.Unicode)
{
    Subject = "My message",
    Body = "Hi, it is my message"
};

msg.Recipients.Add("sam@to.com", "Sam", MapiRecipientType.MAPI_TO);

// create message in inbox
client.CreateMessage(KnownFolders.Inbox, msg);

```
### **Send Message**

```csharp
// prepare the message
var msg = new MapiMessage(OutlookMessageFormat.Unicode)
{
    Subject = "My message",
    Body = "Hi, it is my message"
};

msg.Recipients.Add("sam@to.com", "Sam", MapiRecipientType.MAPI_TO);
msg.SetProperty(KnownPropertyList.SenderName, "John");
msg.SetProperty(KnownPropertyList.SentRepresentingEmailAddress, "John@from.com");

// send message
client.Send(msg);
```
### **Send Draft Message**

```csharp
// prepare the message
var msg = new MapiMessage(OutlookMessageFormat.Unicode)
{
    Subject = "My message",
    Body = "Hi, it is my message"
};

msg.Recipients.Add("sam@to.com", "Sam", MapiRecipientType.MAPI_TO);
msg.SetProperty(KnownPropertyList.SenderName, "John");
msg.SetProperty(KnownPropertyList.SentRepresentingEmailAddress, "John@from.com");

// add message to Draft folder
var draftMessage = client.CreateMessage(KnownFolders.Drafts, msg);

// send a draft message
client.Send(draftMessage.ItemId);
```
### **Copy Message**

```csharp

// copy message to Inbox folder
var copiedMsg = client.CopyMessage(KnownFolders.Inbox, msg.ItemId);
```
### **Move Message**

```csharp
// move message to Inbox folder
var movedMsg = client.MoveMessage(KnownFolders.Inbox, msg.ItemId);
```
### **Manage Attachments**

```csharp

// create an attachment
var attachment = new MapiAttachment();
attachment.SetProperty(KnownPropertyList.DisplayName, "My Attachment");
attachment.SetProperty(KnownPropertyList.AttachDataBinary, new byte[1024]);

// add an attachment to message
var createdAttachment = client.CreateAttachment(messageInfo.ItemId, attachment);

// fetch a message attachment
var fetchedAttachment = client.FetchAttachment(createdAttachment.ItemId);

// delete a message attachment 
client.DeleteAttachment(createdAttachment.ItemId);

// list the message attachments
var attachments = client.ListAttachments(messageInfo.ItemId);   
```


## **Manage Categories**
To manage categories with MS Graph by Aspose.Email for .NET, use the following methods:
* [CreateCategory](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/createcategory)
* [FetchCategory](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/fetchcategory)
* [ListCategories](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/listcategories)
* [UpdateCategory](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/updatecategory)

```csharp
// create a custom category with Orange color
var category = client.CreateCategory("My custom category", CategoryPreset.Preset1);

// fetch a category
var fetchedCategory = client.FetchCategory(category.Id);

// update category (change color to brown)
fetchedCategory.Preset = CategoryPreset.Preset2;
var updatedCategory = client.UpdateCategory(fetchedCategory);

// list available categories
var categories = client.ListCategories();

foreach (var cat in categories)
{
    Console.WriteLine(cat.DisplayName);
}

// delete a category
client.Delete(fetchedCategory.Id);
```

## **Manage Overrides**
To manage overrides with MS Graph by Aspose.Email for .NET, use the following methods:
* [CreateOrUpdateOverride](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/createorupdateoverride) 
* [ListOverrides](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/listoverrides)
* [UpdateOverride](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/updateoverride)

```csharp
// Create an user's override
var userOverride = client.CreateOrUpdateOverride
    (new MailAddress("JohnBrown@someorg.com", "JohnBrown"), ClassificationType.Focused);

// list the overrides
var overrides = client.ListOverrides();

// update override
userOverride.Sender.DisplayName = "John Brown";
var updatedOverride = client.UpdateOverride(userOverride);

// delete override
client.Delete(updatedOverride.Id);
```
## **Manage Rules**
To manage rules with MS Graph by Aspose.Email for .NET, use the following methods:
* [CreateRule](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/createrule)
* [FetchRule](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/fetchrule)
* [UpdateRule](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/updaterule)
* [ListRules](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/listrules)

```csharp
// Create a rule
var rule = PrepareRule("user@someorg.com", "User");
var createdRule = client.CreateRule(rule);

// List all rules defined for Inbox
var rules = client.ListRules();

// Fetch a rule
var fetchedRule = client.FetchRule(createdRule.RuleId);

// Update a rule
fetchedRule.DisplayName = "Renamed rule";
fetchedRule.IsEnabled = false;
var updatedRule = client.UpdateRule(createdRule);

// Delete a rule
client.Delete(updatedRule.RuleId);
```
```csharp
InboxRule PrepareRule(string email, string displayName)
{
    var rule = new InboxRule()
    {
        DisplayName = "My rule",
        Priority = 1,
        IsEnabled = true,
        Conditions = new RulePredicates(),
        Actions = new RuleActions()
    };

    rule.Conditions.ContainsSenderStrings = new StringCollection { displayName };
    rule.Actions.ForwardToRecipients = new MailAddressCollection
        { new MailAddress(email, displayName, true) };
    rule.Actions.StopProcessingRules = true;

    return rule;
}
```
## **Manage Notebooks**
To manage notebooks with MS Graph by Aspose.Email for .NET, use the following methods:
* [CreateNotebook](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/createnotebook)
* [CopyNotebook](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/copynotebook)
* [FetchNotebook](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/fetchnotebook)
* [ListNotebooks](https://apireference.aspose.com/email/net/aspose.email.clients.graph/igraphclient/methods/listnotebooks)

```csharp
// create a OneNote notebook
var newNotebook = new Notebook()
{
    DisplayName = "My Notebook"
};
var createdNotebook = client.CreateNotebook(newNotebook);

// fetch a notebook
var fetchedNotebook = client.FetchNotebook(createdNotebook.Id);

// list the notebooks
var notebooks = client.ListNotebooks();
```
