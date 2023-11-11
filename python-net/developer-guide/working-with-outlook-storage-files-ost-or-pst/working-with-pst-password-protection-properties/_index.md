---
title: Working with PST Password Protection Properties
type: docs
weight: 110
url: /python-net/working-with-pst-password-protection-properties/
---


Microsoft Outlook lets users password protect PST files to restrict access to them. Aspose.Email can detect password protection on a PST file. This article shows how to:

- Check for Password Protection of a PST
- Remove/Reset the Password property from the PST
- Setting/Changing PST Password
## **Check for Password protection**
The MapiPropertyTag.PR_PST_PASSWORD value from the MapiPropertyTag class is used to check if a file is password protected. The CRC-32 hash of the password string is stored in the PidTagPstPassword (tag = 0x67ff0003) property in the MessageStore. If this property exists and is nonzero, then the PST is password protected. The following code snippet shows you how to check if the PST is password protected. It also shows how to check whether the provided password is correct or not.



```py
import aspose.email as ae
from zlib import crc32

# Determines whether the specified PST is password protected.
def is_password_protected(pst):
    # If the property exists and is nonzero, then the PST file is password protected.
    if ae.mapi.MapiPropertyTag.PST_PASSWORD in pst.store.properties.keys:
        password_hash = pst.store.properties[ae.mapi.MapiPropertyTag.PST_PASSWORD].get_long()
        return password_hash != 0
    return False

# Determines whether the specified string is a valid password for the PST.
def is_password_valid(password, pst):
    # If the property exists and is nonzero, then the PST file is password protected.
    if ae.mapi.MapiPropertyTag.PST_PASSWORD in pst.store.properties.keys:
        # The property value contains the CRC-32 hash of the password string of PST.
        password_hash = pst.store.properties[ae.mapi.MapiPropertyTag.PST_PASSWORD].get_long()
        return password_hash != 0 and password_hash == compute_crc32(password.encode("ascii"))
    return False

# Compute CRC-32 hash for the given bytes
def compute_crc32(data):
    return crc32(data) & 0xffffffff

# Usage
pst_file_path = "backup.pst"

with ae.storage.pst.PersonalStorage.from_file(pst_file_path) as pst:
    is_protected = is_password_protected(pst)
    is_valid = is_password_valid("password", pst)

    print("Is Password Protected:", is_protected)
    print("Is Password Valid:", is_valid)
```
## **Removing/Reseting PR_PST_PASSWORD Property**
Removal of the PR_PST_PASSWORD property cannot be achieved as other properties are removed from a message store. Instead, we need to set its value to zero (0) in order to get it removed. The "Store" property of the PST class allows to access store properties of PST instead of MessageStoreProperties of PST in this case. The following code snippet shows you how to Remove/Reset PR_PST_PASSWORD Property.



```py
import aspose.email as ae

data_dir = "D:\\"
pst_file_path = data_dir + "my.pst"

with ae.storage.pst.PersonalStorage.from_file(pst_file_path) as personal_storage:
    if ae.mapi.MapiPropertyTag.PST_PASSWORD in personal_storage.store.properties.keys:
        property = ae.mapi.MapiProperty(
            ae.mapi.MapiPropertyTag.PST_PASSWORD,
            bytearray([0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00])
        )
        personal_storage.store.set_property(property)
```
## **Setting Password on PST Files**
The following code snippet shows you how to set password on PST files.



```py
import aspose.email as ae

data_dir = "D:\\"
output_file_path = data_dir + "my.pst"

with ae.storage.pst.PersonalStorage.create(output_file_path, ae.storage.pst.FileFormatVersion.UNICODE) as pst:
    # Set the password
    password = "Password1"
    pst.store.change_password(password)
    # Remove the password
    pst.store.change_password(None)
```
