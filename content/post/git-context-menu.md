---
date: "2022-03-03T19:49:09+08:00"
draft: false
tags:
- windows
- git
title: Git Context Menu
---

If install git via scoop, the "Open Bash Here" option is missing in right click menu. The below registry script is to add back the missing option

```bat
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\*\shell\Open Git Bash]
@="Open Git Bash"
"Icon"="C:\\scoop_folder\\scoop\\apps\\git\\current\\git-bash.exe"

[HKEY_CLASSES_ROOT\*\shell\Open Git Bash\command]
@="\"C:\\scoop_folder\\scoop\\apps\\git\\current\\git-bash.exe\" \"--cd=%1\""

; This will make it appear when you right click ON a folder
; The "Icon" line can be removed if you don't want the icon to appear

[HKEY_CLASSES_ROOT\Directory\shell\bash]
@="Open Git Bash"
"Icon"="C:\\scoop_folder\\scoop\\apps\\git\\current\\git-bash.exe"


[HKEY_CLASSES_ROOT\Directory\shell\bash\command]
@="\"C:\\scoop_folder\\scoop\\apps\\git\\current\\git-bash.exe\" \"--cd=%1\""

; This will make it appear when you right click INSIDE a folder
; The "Icon" line can be removed if you don't want the icon to appear

[HKEY_CLASSES_ROOT\Directory\Background\shell\bash]
@="Open Git Bash"
"Icon"="C:\\scoop_folder\\scoop\\apps\\git\\current\\git-bash.exe"

[HKEY_CLASSES_ROOT\Directory\Background\shell\bash\command]
@="\"C:\\scoop_folder\\scoop\\apps\\git\\current\\git-bash.exe\" \"--cd=%v.\""
```