---
title: Create New Email in Jython
ArticleTitle: Create New Email in Jython
type: docs
weight: 20
url: /java/create-new-email-in-jython/
---

## **Aspose.Email - Create New Email**
To Create new Email using **Aspose.Email Java for Jython**, simply invoke **CreateNewEmail** module. Here you can see example code.

**Jython Code**

``` python

 from aspose-email import Settings

from com.aspose.email import MailMessage

from com.aspose.email import MailAddress

from com.aspose.email import MailMessageSaveType

class CreateNewEmail:

    def __init__(self):



        dataDir = Settings.dataDir + 'ProgrammingEmail/CreateNewEmail/'



        # Create a instance of MailMessage class

        message = MailMessage()

        # Set subject of the message

        message.setSubject("New message created by Aspose.Email for Java")

        mail_address = MailAddress

        # Set Html body

        message.setHtmlBody("<b>This line is in bold.</b> <br/> <br/>" +

            "<font color=blue>This line is in blue color</font>")

        # Set sender information

        message.setFrom(MailAddress("from@domain.com", "Sender Name", False))

        # Add TO recipients

        message.getTo().add(MailAddress("to1@domain.com", "Recipient 1", False))

        message.getTo().add(MailAddress("to2@domain.com", "Recipient 2", False))

        # Add CC recipients

        message.getCC().add(MailAddress("cc1@domain.com", "Recipient 3", False))

        message.getCC().add(MailAddress("cc2@domain.com", "Recipient 4", False))

        # Save message in EML and MSG formats

        mail_message_save_type = MailMessageSaveType()

        message.save(dataDir + "Message.eml", mail_message_save_type.getEmlFormat())

        message.save(dataDir + "Message.msg", mail_message_save_type.getOutlookMessageFormat())

        # Display Status

        print "Created email messages Successfully."



if __name__ == '__main__':        

    CreateNewEmail()

```
## **Download Running Code**
Download **Create New Email (Aspose.Email)** from any of the below mentioned social coding sites:

- [GitHub](https://github.com/aspose-email/Aspose.Email-for-Java/releases/tag/Aspose.Email_Java_for_Jython-v1.0)
- [CodePlex](https://archive.codeplex.com/?p=asposeemailjavajython)
