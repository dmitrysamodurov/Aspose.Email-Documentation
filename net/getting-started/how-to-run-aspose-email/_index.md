---
title: How to Run Aspose.Email
type: docs
weight: 90
url: /net/how-to-run-aspose-email/
---

## **How to Run Aspose.Email for .NET**

Aspose.Email for .NET is a comprehensive and versatile email processing library that provides a wide range of features for creating, sending, receiving, and managing email messages within .NET applications. The library supports various email formats and protocols, making it a complete toolkit for email handling. Below, we provide a step-by-step guide for setting up and running Aspose.Email on Linux and in a Docker container, starting with a simple "Hello World" example.

To start utilizing the library, just follow the steps.

### **Hello World**

1. **Create a New Project:** Open Visual Studio and create a new Console Application project.

2. **Install Aspose.Email:**
Use NuGet Package Manager to install Aspose.Email. Open the Package Manager Console and run:
```
Install-Package Aspose.Email
```
3. **Write the Code:**
Add the following code to your Program.cs file:

```csharp

using System;
using Aspose.Email;

class Program
{
    static void Main(string[] args)
    {
        // Create a new email message
        MailMessage message = new MailMessage();
        message.Subject = "Hello World!";
        message.Body = "This is the body of the email.";

        // Specify sender and recipient
        message.From = "sender@example.com";
        message.To = "recipient@example.com";

        // Display the message
        Console.WriteLine("Subject: " + message.Subject);
        Console.WriteLine("Body: " + message.Body);
    }
}
```
4. **Run the Application:**
Execute the application. You should see the email subject and body printed to the console.

### **Run Aspose.Email for .NET on Linux**

Running Aspose.Email for .NET on Linux involves setting up a .NET environment on your Linux machine. Follow these steps:

1. **Install .NET SDK:**
Download and install the .NET SDK from the official Microsoft .NET website.

For example, on Ubuntu, you can install the .NET SDK using the following commands:

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install -y dotnet-sdk-6.0
```
2. **Create a New Project:**
Open a terminal and create a new .NET Console Application:

```bash
dotnet new console -n HelloWorldAspose
cd HelloWorldAspose
```

3. **Add Aspose.Email Package:**
Add Aspose.Email to your project:

```bash
dotnet add package Aspose.Email
```

4. **Write the Code:**
Replace the content of Program.cs with the "Hello World" example code provided above.

5. **Run the Application:**
Execute the application:

```bash
dotnet run
```

### **Run Aspose.Email in Docker**
Running Aspose.Email in a Docker container provides an isolated environment. Follow these steps:

1. **Create a Dockerfile:**
In your project directory, create a file named Dockerfile with the following content:

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj .
RUN dotnet restore

# Copy the remaining source code and build the application
COPY . .
RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app
COPY --from=build /app/out .

ENTRYPOINT ["dotnet", "HelloWorldAspose.dll"]
```
2. **Build the Docker Image:**
Open a terminal, navigate to your project directory, and run:

```bash
docker build -t helloworldaspose .
```
3. **Run the Docker Container:**
Run the container using the following command:

```bash
docker run --rm helloworldaspose
```

By following these steps, you can successfully run Aspose.Email for .NET on various platforms, ensuring that you can integrate its powerful email processing capabilities into your applications regardless of the environment. For further information and updates, refer to the Aspose.Email for .NET [documentation](https://docs.aspose.com/email/net/).

