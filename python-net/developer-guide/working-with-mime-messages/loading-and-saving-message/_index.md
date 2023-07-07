---
title: Loading and Saving Message
type: docs
weight: 30
url: /python-net/loading-and-saving-message/
---


## **Detecting File Formats**
Aspose.Email API provides the capability to detect file format of provided message file. The DetectFileFormat method of FileFormatUtil class can be used to achieve this. The following classes and methods can be used to detect the loaded file format.

- Class Aspose.Email.FileFormatType
- Class Aspose.Email.FileFormatInfo
- Class Aspose.Email.FileFormatUtil
- Method Aspose.Email.FileFormatUtil.DetectFileFormat(Stream)
- Method Aspose.Email.FileFormatUtil.DetectFileFormat(String)

The following code snippet shows you how to detecting file formats.

```py
from aspose.email.tools import FileFormatUtil

# Detect file format and get the detected load format
info = FileFormatUtil.detect_file_format(data_dir + "message.msg")
print("The message format is: " + str(info.file_format_type))
```
## **Loading a Message with Load Options**
The following code snippet shows you how to load a message with load options.

```py
from aspose.email import MailMessage, EmlLoadOptions, HtmlLoadOptions, MhtmlLoadOptions, MsgLoadOptions

# Load Eml, html, mhtml, msg, and dat files
mail_message = MailMessage.load(data_dir + "message.eml", EmlLoadOptions())
MailMessage.load(data_dir + "description.html", HtmlLoadOptions())
MailMessage.load(data_dir + "message.mhtml", MhtmlLoadOptions())
MailMessage.load(data_dir + "message.msg", MsgLoadOptions())

# Loading with custom options
eml_load_options = EmlLoadOptions()
eml_load_options.preferred_text_encoding = "utf-8"
eml_load_options.preserve_tnef_attachments = True

MailMessage.load(data_dir + "description.html", eml_load_options)

html_load_options = HtmlLoadOptions()
html_load_options.preferred_text_encoding = "utf-8"
html_load_options.should_add_plain_text_view = True
html_load_options.path_to_resources = data_dir

MailMessage.load(data_dir + "description.html", html_load_options)
```
### **Preserving Embedded Message Format during Loading**

```py
from aspose.email import MailMessage, EmlLoadOptions, HtmlLoadOptions, MhtmlLoadOptions, MsgLoadOptions
from aspose.email.tools import FileFormatUtil

eml_load_options = EmlLoadOptions()
eml_load_options.preserve_embedded_message_format = True

mail = MailMessage.load(data_dir + "message.eml", eml_load_options)

file_format = FileFormatUtil.detect_file_format(mail.attachments[0].content_stream).file_format_type

print("Embedded message file format: " + str(file_format))
```
## **Saving and Converting Messages**
Aspose.Email makes it easy to convert any message type to another format. To demonstrate this feature, the code in this article loads three types of messages from disk and saves them back in other formats. The base class SaveOptions and the classes EmlSaveOptions, MsgSaveOptions, MhtSaveOptions, HtmlSaveOptions for additional settings when saving MailMessage can be used for saving messages to other formats. The article shows how to use these classes to save a sample email as:

- EML format.
- Outlook MSG.
- MHTML format.
- HTML format.
### **Loading EML and Saving as EML**
The following code snippet shows you how to loads an EML message and saves it to the disc in the same format.

```py
from aspose.email import MailMessage, SaveOptions

# Initialize and Load an existing EML file by specifying the MessageFormat
mail_message = MailMessage.load(data_dir + "message.eml")

mail_message.save(data_dir + "LoadAndSaveFileAsEML_out.eml", SaveOptions.default_eml)
```
### **Loading EML and Saving as EML Preserving the Original Boundaries**
The following code snippet shows you how to loading EML and saving as EML preserving the original boundaries.

```py
from aspose.email import MailMessage, EmlSaveOptions, MailMessageSaveType

mail_message = MailMessage.load(data_dir + "message.eml")

# Save as eml with preserved original boundaries
eml_save_options = EmlSaveOptions(MailMessageSaveType.eml_format)

mail_message.save(data_dir + "PreserveOriginalBoundaries_out.eml", eml_save_options)
```
### **Saving as EML Preserving TNEF Attachments**
The following code snippet shows you how to saving as EML preserving TNEF attachments.

```py
from aspose.email import MailMessage, EmlSaveOptions, MailMessageSaveType, FileCompatibilityMode

mail_message = MailMessage.load(data_dir + "message.eml")

# Save as eml with preserved attachment
eml_save_options = EmlSaveOptions(MailMessageSaveType.eml_format)
eml_save_options.file_compatibility_mode = FileCompatibilityMode.PRESERVE_TNEF_ATTACHMENTS

mail_message.save(data_dir + "PreserveTNEFAttachment_out.eml", eml_save_options)
```
### **Loading EML, Saving to MSG**
The following code snippet shows you how to loads an EML message and converts it to MSG using the appropriate option from SaveOptions.

```py
from aspose.email import MailMessage, SaveOptions, MailMessageSaveType, FileCompatibilityMode

# Initialize and Load an existing EML file by specifying the MessageFormat
eml = MailMessage.load(data_dir + "message.eml")

# Save the Email message to disk in ASCII format and Unicode format
eml.save(data_dir + "AnEmail_out.msg", SaveOptions.default_msg_unicode)
```
### **Saving as MSG with Preserved Dates**
The MsgSaveOptions class allows you to save the source message as an Outlook Message file (MSG) preserving dates. The following code snippet shows you how to Saving as MSG with Preserved Dates.

```py
from aspose.email import MailMessage, MsgSaveOptions, MailMessageSaveType, FileCompatibilityMode

# Initialize and Load an existing EML file by specifying the MessageFormat
eml = MailMessage.load(data_dir + "message.eml")

# Save as msg with preserved dates
msg_save_options = MsgSaveOptions(MailMessageSaveType.outlook_message_format_unicode)
msg_save_options.preserve_original_dates = True

eml.save(data_dir + "outTest_out.msg", msg_save_options)
```
### **Saving MailMessage as MHTML**
Different options of MHTML can be used to obtain the desired results. The following code snippet shows you how to loads an EML message into MailMessage and converts it to MHTML.

```py
from aspose.email import MailMessage, SaveOptions, MailMessageSaveType, FileCompatibilityMode

# Initialize and Load an existing EML file by specifying the MessageFormat
eml = MailMessage.load(data_dir + "message.eml")

eml.save(data_dir + "AnEmail_out.mhtml", SaveOptions.default_mhtml)
```
#### **Converting to MHTML with Optional Settings**

The MhtSaveOptions class provides additional options for saving email messages to MHTML format. The enumerator MhtFormatOptions makes it possible to write additional email information to the output MHTML. The following additional fields can be written:

- WriteHeader – writes the email header to the output file.
- WriteOutlineAttachments – writes outline attachments to the output file.
- WriteCompleteEmailAddressToMht – writes complete email address to the output file.
- WriteCompleteEmailAddress – writes complete email address to the output file.
- HideExtraPrintHeader – hides extra print header from the top of output file.
- WriteCompleteToEmailAddressToMht – writes the complete recipient email address to the output file.
- WriteCompleteFromEmailAddressToMht – writes the complete sender email address to the output file.
- WriteCompleteCcEmailAddressToMht – writes the complete email addresses of any carbon-copied recipients to the output file.
- WriteCompleteBccEmailAddressToMht – writes the complete email address of any blind carbon-copied recipients to the output file.

The following code snippet shows you how to converting eml file to MHTML with optional settings.

```py
from aspose.email import MailMessage, MhtSaveOptions, MhtFormatOptions, MailMessageSaveType, FileCompatibilityMode

# Load an existing EML file
eml = MailMessage.load(data_dir + "message.eml")

# Save as mht with header
mht_save_options = MhtSaveOptions()

# Specify formatting options required
# Here we are specifying to write header information to output without writing extra print header
# and the output headers should be displayed as the original headers in the message
mht_save_options.mht_format_options = MhtFormatOptions.WRITE_HEADER | MhtFormatOptions.HIDE_EXTRA_PRINT_HEADER | MhtFormatOptions.DISPLAY_AS_OUTLOOK

# Check the body encoding for validity.
mht_save_options.check_body_content_encoding = True

eml.save(data_dir + "outMessage_out.mht", mht_save_options)
```
#### **Rendering Calendar Events while Converting to MHTML**
The MhtFormatOptions.RenderCalendarEvent renders the Calendar events to the output MTHML. Furthermore, the formatting of the output MHTML can be controlled by various properties available as part of MhtMessageFormatter class. The following options are available to format the calendar event output to MHTML, 

- MhtMessageFormatter.StartFormat - Gets or sets the Start format.
- MhtMessageFormatter.EndFormat - Gets or sets the End format.
- MhtMessageFormatter.ShowTimeAsFormat - Gets or sets the ShowTimeAs format.
- MhtMessageFormatter.RecurrenceFormat - Gets or sets the Recurrence format.
- MhtMessageFormatter.RecurrencePatternFormat - Gets or sets the RecurrencePattern format.
- MhtMessageFormatter.OrganizerFormat - Gets or sets the Organizer format.
- MhtMessageFormatter.RequiredAttendeesFormat - Gets or sets the RequiredAttendees format.

The following code snippet shows you how to render calendar events while converting to MHTML.

```py
from aspose.email import MailMessage, MhtSaveOptions, MhtFormatOptions, MhtTemplateName, MailMessageSaveType, FileCompatibilityMode

file_name = "message.msg"

# Load the MSG file
msg = MailMessage.load(data_dir + file_name)

# Create MHT save options
options = MhtSaveOptions()
options.mht_format_options = MhtFormatOptions.WRITE_HEADER | MhtFormatOptions.RENDER_CALENDAR_EVENT

# Save the message as MHTML
msg.save(data_dir + "Meeting with Recurring Occurrences.mhtml", options)
```
#### **Exporting Email to MHT without Inline Images**

```py
from aspose.email import MailMessage, MhtSaveOptions, MhtFormatOptions, MhtTemplateName, MailMessageSaveType, FileCompatibilityMode

# Load the EML file
eml = MailMessage.load(data_dir + "message.eml")

# Create MHT save options
mht_save_options = MhtSaveOptions()
mht_save_options.skip_inline_images = True

# Save the message as MHTML without inline images
eml.save(data_dir + "EmlToMhtmlWithoutInlineImages_out.mht", mht_save_options)
```
#### **Exporting Email to MHT with customized TimeZone**
MailMessage class provides the TimeZoneOffset property to set customized Timezone while exporting to MHT. The following code snippet shows you how to export an email to MHT with customized TimeZone.

```py
from aspose.email import MailMessage, MhtSaveOptions, MhtFormatOptions, MhtTemplateName, MailMessageSaveType, FileCompatibilityMode
from datetime import timedelta

# Load the EML file
eml = MailMessage.load(data_dir + "message.eml")

# Set the local time for message date
eml.time_zone_offset = timedelta(hours=-8)

# The dates will be rendered by the local system time zone
mht_save_options = MhtSaveOptions()
mht_save_options.mht_format_options = MhtFormatOptions.WRITE_HEADER
eml.save(data_dir + "ExportEmailToMHTWithCustomTimezone_out.mhtml", mht_save_options)
```
### **Exporting Email to EML**
The following code snippet shows you how to export email to eml.

```py
from aspose.email import MailMessage, SaveOptions

# Load the EML file
msg = MailMessage.load(data_dir + "message.eml")

# Save the Email message as EML
msg.save(data_dir + "ExporttoEml_out.eml", SaveOptions.default_eml)
```
### **Saving Message as HTML**
The HtmlSaveOptions class allows you to export the message body to HTML with the option to save embedded resources. The following code snippet shows you how to Saving Message as HTML where the default value of EmbedResources is true.

```py
from aspose.email import MailMessage, SaveOptions, HtmlSaveOptions, HtmlFormatOptions

# Load the EML file
message = MailMessage.load(data_dir + "message.eml")

# Save the Email message as HTML
message.save(data_dir + "SaveAsHTML_out.html", SaveOptions.default_html)

# OR

eml = MailMessage.load(data_dir + "message.eml")
options = HtmlSaveOptions()
options.embed_resources = False
options.html_format_options = (
    HtmlFormatOptions.WRITE_HEADER
    | HtmlFormatOptions.WRITE_COMPLETE_EMAIL_ADDRESS
)  # save the message headers to output HTML using the formatting options
eml.save(data_dir + "SaveAsHTML1_out.html", options)
```

### **Saving Message as Outlook Template (.oft) file**
The following code snippet shows you how to save message as outlook template (.oft) file.

```py
from aspose.email import MailMessage, SaveOptions

eml = MailMessage("test@from.to", "test@to.to", "template subject", "Template body")

oft_eml_file_name = "EmlAsOft_out.oft"
options = SaveOptions.default_msg_unicode
options.save_as_template = True
eml.save(data_dir + oft_eml_file_name, options)
```
