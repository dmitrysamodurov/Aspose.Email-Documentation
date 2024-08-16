---
title: Mail Services
ArticleTitle: Mail Services
type: docs
weight: 8
url: /net/mail-services/
---

## **API to Access Mail Services**

### **Exchange Web Dav (has been officially deprecated)**

**Exchange WebDAV (Web Distributed Authoring and Versioning)** was a protocol extension used by Microsoft Exchange Server to allow clients to access and manipulate mail, calendar, and contact items stored on the server via HTTP. Although it has been officially deprecated, it played a significant role in the development of web-based and remote access to Exchange data.

### **EWS**

**Exchange Web Services (EWS)** is an API provided by Microsoft to interact with Microsoft Exchange Server. It allows developers to access and manipulate Exchange data such as emails, calendar events, contacts, and tasks programmatically. EWS was introduced to replace older protocols like WebDAV and provides a more robust and efficient way to work with Exchange data. 

It uses the SOAP (Simple Object Access Protocol) over HTTP and HTTPS to send and receive messages between the client and the Exchange server. The SOAP-based nature of EWS can be complex to implement and debug compared to RESTful APIs. Microsoft is gradually shifting towards Microsoft Graph API, which provides a more modern and RESTful approach to accessing Microsoft 365 data, including Exchange Online.

### **Microsoft Graph**

**Microsoft Graph** is a powerful API that provides a unified endpoint for accessing a wide range of data and services in the Microsoft 365 ecosystem. It allows developers to interact with a variety of Microsoft services, including Office 365, Azure Active Directory, SharePoint, OneDrive, Outlook, Microsoft Teams, and more. It serves as a gateway to data and insights across Microsoft 365.

**Key Features**

- The base URL for the API is https://graph.microsoft.com.
- Uses OAuth 2.0 for authentication and authorization.
- Leverages Microsoft's AI and machine learning capabilities for enhanced data insights.

### **Gmail API**

**Gmail API** is a RESTful API provided by Google that allows developers to interact programmatically with Gmail mailboxes and perform various operations on email data (read, send, delete, and organize email messages). It offers a more flexible and powerful alternative to the traditional IMAP and SMTP protocols, enabling developers to access and manage Gmail messages, threads, labels, drafts, and more. It is available through the Google Cloud Platform.

**Key Features**

- Perform multiple API requests in a single HTTP call to improve efficiency and reduce the number of network requests.
- Uses OAuth 2.0 for secure authentication and authorization, ensuring that applications only access data that users have explicitly granted permission for.
- Provides various permission scopes, allowing applications to request only the level of access they need (e.g., read-only access, full access).
- All API interactions occur over HTTPS to ensure secure communication between the application and Google’s servers.

## **Advanced Technologies**

### **S/MIME**

**Secure/Multipurpose Internet Mail Extensions (S/MIME)** is a widely used standard for securing email communication. It provides a method for sending and receiving signed and encrypted email messages, ensuring message integrity, authenticity, and confidentiality.

**Key Features**

- S/MIME ensures that only the intended recipient can read the email content. It uses a combination of symmetric (for speed) and asymmetric (for key exchange) encryption algorithms. Commonly used algorithms include RSA (used for asymmetric encryption), AES or Advanced Encryption Standard (one of the symmetric algorithms), and Triple DES.
- Confirms the identity of the sender. 
- Verifies that the email content has not been tampered with during transit. Prevents the sender from denying the authorship of the email. 
- Uses the sender’s private key to create a signature and the recipient's client uses the sender's public key to verify it.
- S/MIME relies on a Public Key Infrastructure (PKI) for key management and exchange. Digital certificates, issued by Certificate Authorities (CAs), bind public keys to individual identities. Certificates usually follow the X.509 standard.

### **DKIM**

**DomainKeys Identified Mail (DKIM)** is an email authentication mechanism designed to detect forged sender addresses, a common technique used in phishing and email spoofing. It allows an organization to take responsibility for an email during its transit by associating a domain name with the message, thereby ensuring its authenticity and integrity. DKIM verifies that an email purportedly coming from a specific domain was indeed authorized by the domain owner, primarily focusing on the authenticity of the "From" email address. This is achieved by enabling the sender to electronically sign their email with a private key, while the recipient verifies this signature using a public key published in the sender's DNS records.

**Key Features**

- DKIM adds a "DKIM-Signature" header to the email which contains the digital signature and several key parameters. The email body and select headers are hashed using a hashing algorithm like SHA-256. This hash is then encrypted using the sender’s private key to generate the digital signature.
- The sender publishes the public key in their DNS records. The recipient’s email server looks up the sender’s public key in DNS to verify the digital signature.

### **AMP Email**

**Accelerated Mobile Pages (AMP)** for Email is an open-source framework designed to create dynamic, interactive, and engaging email experiences. It's designed to make emails more dynamic and functional, transforming a medium that has traditionally been static and passive.

**Key features**

- Allows users to take actions directly within the email, such as RSVPing to events, filling out forms, or interacting with product carousels.
- Emails can serve dynamic content that updates at the time of opening. This ensures that users see the most current information whether it be the latest pricing, stock status, or news updates.
- AMP emails is supported by several major email clients including Gmail, Yahoo Mail, Outlook.com. Each email client that supports AMP emails maintains its own set of requirements and rendering rules.
- AMP emails need to be sent in a multi-part MIME format containing a plain text version for basic accessibility, an HTML version for rich and visually appealing content, and an AMP version for dynamic and interactive elements, ensuring compatibility and an enhanced user experience across various email clients.
- Only verified senders can send AMP emails, ensuring that emails are secure and trusted.

### **AntiSpam**

AntiSpam refers to a range of techniques, technologies, and strategies designed to detect, prevent, and mitigate unsolicited and often harmful email messages, commonly known as spam. 

**AntiSpam Techniques**

1. **Filtering Methods**
   - Content-Based Filtering: Analyzes the content of the email for common spam indicators.
   - Blacklists: Lists of known spam IP addresses or domains that are automatically blocked.
   - Whitelists: Lists of approved senders that are always allowed through.
   - Heuristic Filtering: Uses rules and algorithms to detect spam based on patterns.
   - Bayesian Filtering: Uses statistical methods to identify spam based on historical data.
   - Greylisting: Temporarily rejects emails from unknown senders and accepts them if they are sent again after a delay.
   - Machine Learning: Uses complex models trained on large datasets to identify spam.

2. **Authentication Methods**
   - SPF (Sender Policy Framework): Verifies that the sender's IP address is authorized to send emails for the domain.
   - DKIM (DomainKeys Identified Mail): Uses digital signatures to verify that the email has not been altered during transit and is indeed from the domain it claims to be.
   - DMARC (Domain-based Message Authentication, Reporting & Conformance): Builds upon SPF and DKIM to provide a standardized method for email senders to indicate that their messages are protected and how receiving servers should handle authentication failures.

### **Email bounces**

**Types of Email Bounces**

1. **Hard Bounces.** Permanent delivery failures indicating that the email cannot be delivered to the intended recipient's address.
   - Common Causes:
     - Invalid or non-existent email addresses.
     - The recipient’s domain does not exist.
     - Permanent server issues on the recipient's end.
     - Typos or formatting errors in the email address.

2. **Soft Bounces.** Temporary delivery failures indicating that the email could not be delivered at the time but may be successful if retried later.
   - Common Causes:
     - The recipient's mailbox is full.
     - Temporary server issues on the recipient's end.
     - The recipient’s email server is down or offline.
     - Emails too large for the recipient’s email system.

Email servers typically return bounce codes that can help diagnose the reason for a bounce.

### **Email threading**

Email threading is a method used by email clients and applications to group related emails together based on their subject or conversation, making it easier for users to follow and manage email exchanges.

**Key features**

- **In-Reply-To and References Headers**. Email headers that point to previous messages in the thread, helping the email client to link replies and forwards to the original email.
- Subject Lines. Often used to group emails into threads. Emails with the same subject line, typically prefixed with "Re:" (reply) or "Fwd:" (forward), are grouped together.
- Users can expand or collapse threads, focusing only on the relevant portions of a conversation.
