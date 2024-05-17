# Drive Client FAQ

## \[Mac] How to uninstall SeaDrive

> When I try the normal uninstall method of dragging the SeaDrive app from my app folder to the recycle bin I get the following error message:
> "The item “SeaDrive” can’t be moved to the Trash because some of its extensions are in use."

In system settings -> Extension, disable the SeaDrive Finder extension. Then try to uninstall SeaDrive again.

## \[Win] How to uninstall SeaDrive in Windows

If you have a problem in uninstall SeaDrive, you can try the following method:

Open the command line tool using Administrator privilege. Then type the following command:

```
msiexec /x {BCF9F43A-A306-427D-B312-38F5A3D8F6A5}

```

{BCF9F43A-A306-427D-B312-38F5A3D8F6A5} is the ID of the SeaDrive version.

| Version | ID                                   |
| :------ | :----------------------------------- |
| 1.0.0   | BCF9F43A-A306-427D-B312-38F5A3D8F6A5 |

## How to clean internal cache of SeaDrive

Delete `~/.seadrive` on Mac

Delete `~/Library/Preferences/com.seafile.Seafile Drive Client.plist` and `~/Library/Preferences/com.seafile.seadrive.plist` 

Delete `C:\Users\<username>\seadrive` on Windows

## Manually file lock can't work

If you lock a file in the client, please check the Web interface to see if the file is really locked.

If the file lock icon doesn't shown at other clients, this may be caused by delay. The clients check the file lock status every 10 seconds. Please wait about half minute and click other folder then click back, then check if the icon is updated. 

## Automatically file lock can't work for Word

Auto file locking not work for Word in Windows is a known compatibility issue with latest Word software. We are still trying to solve the problem.

It should work for Word on Mac.

## \[Win] System reboot when upgrade Drive client

When you upgrade SeaDrive client, if the underlying library Dokany need to be updated, the installer will popup a message warning you that the system will be rebooted during the install. If you continue the installation, the system will be reboot without any further confirm. 


