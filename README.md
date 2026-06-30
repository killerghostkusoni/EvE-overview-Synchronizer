# EvE-overview-Synchronizer
an application that makes synchronizing your overview over multiple accounts in eve simple and fast
# File Content Copier

File Content Copier is a Windows desktop app for copying the contents of two master files into selected target files while keeping each target file's original name and location.

## What The App Does

- Selects one target folder.
- Selects one backup folder.
- Selects two master files:
  - Master Core User
  - Master Core Char
- Provides 10 target groups.
- Each group contains:
  - Group Name
  - Core User target path
  - Core Char target path
- Copies the raw contents of Master Core User into each Core User target.
- Copies the raw contents of Master Core Char into each Core Char target.
- Keeps target filenames unchanged.
- Supports text files and binary files.
- Can save and load all entered app settings as a JSON file.

## Important Safety Behavior

- The app does not rename, move, or delete target files.
- Missing target files are skipped.
- Target paths must stay inside the selected target folder.
- If a target path points outside the selected target folder, the app rejects it.
- If a target file is the same file as its master file, the app skips it to prevent wiping the file.
- Master file contents are read before opening the target for writing.
- If backups are enabled, the app copies all files from the selected target folder to the selected backup folder before overwriting anything.
- The backup is stored in a timestamped snapshot folder inside the selected backup destination.
- The backup folder cannot be the same as the target folder or inside the target folder.

## how to get the Core User and Core Char
open the C:\Users\"your user here"\AppData\Local\CCP\EVE\c_ccp_eve_tq_tranquility\settings_Default
or were ever your eve settings_Default is then open your eve client and pick the character you want to use as the master copy let the character load in and wait 5 seconds then close the client complety to find the 
ex.Core_User_11111111 and ex.Core_Char_1111111111 look in the C:\Users\"your user here"\AppData\Local\CCP\EVE\c_ccp_eve_tq_tranquility\settings_Default
file path and sort the files to most recent then find the ex.Core_User_11111111 and ex.Core_Char_1111111111 write it down in a note pad with the corrispding character name repeat the prosses for the charicetre you want to copy your mastrer copy from


## How To Use

1. Open `FileContentCopier.exe`.
2. Click `Choose Folder` beside `Target folder`.
3. Choose the folder containing the files you want to update.
4. Optional: click `Choose Folder` beside `Backup folder`.
5. Optional: check `Create backups before overwriting`.
6. Enter a `Master group name`.
7. Click `Choose File` beside `Master Core User`.
8. Click `Choose File` beside `Master Core Char`.
9. For each group you want to process:
   - Enter a group name.
   - Browse to or type the Core User target path.
   - Browse to or type the Core Char target path.
10. Click `Run Copy`.
11. Read the status log for copied, skipped, backed up, or failed files.

## Save And Load Info

Use `Save Info` to save the current form values to a `.json` file.

The saved info includes:

- target folder
- backup folder
- master group name
- Master Core User path
- Master Core Char path
- backup checkbox state
- all 10 group names
- all Core User and Core Char target paths

Use `Load Info` later to restore those values.

## Backup Files

When backups are enabled, the app creates one timestamped backup folder inside the selected backup destination. It copies all files from the selected target folder into that backup folder while preserving subfolder paths.

Example:

```text
MyTargetFolder_backup_20260630_143522_123456
```

## Included Files

- `FileContentCopier.exe` - the Windows desktop app.
- `file_content_copier.py` - the Python source code.
- `README.md` - this guide.
- `backups/` - timestamped source-code backups made during revisions.

## Notes

This app was built with Python, Tkinter, and PyInstaller. It does not require paid libraries.
