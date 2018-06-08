# Windows Context Menu 

Small tutorial on how to add programs to the context menu in the Windows Explorer file manager.

## Disclaimer

The obligatory "***If you are doing it wrong don't do it, because this could potentially break your computer!!***". If you never done anything like this make at least a backup of your computer before doing anything with the registry.

## Links to the tutorials

Here a list of links of tutorials that inspired me to do this:

- [Manual approach](https://stackoverflow.com/a/39194769/782712) by [Shaswat Rungta](https://stackoverflow.com/users/2697556/shaswat-rungta)
- [Fast approach](https://stackoverflow.com/a/44019893/7827128) by [Ozesh](https://stackoverflow.com/users/3436775/ozesh) and [Bruno Bieri](https://stackoverflow.com/users/1306012/bruno-bieri)

## Script for the fast approach by [Ozesh](https://stackoverflow.com/users/3436775/ozesh) and [Bruno Bieri](https://stackoverflow.com/users/1306012/bruno-bieri)

[`addToContextMenu_GitBash.reg`](/addToContextMenu_GitBash.reg):

```bash
Windows Registry Editor Version 5.00

; Open files
; Default Git-Bash Location C:\Program Files\Git\git-bash.exe

[HKEY_CLASSES_ROOT\*\shell\Open Git Bash]
@="Open Git Bash"
"Icon"="C:\\Program Files\\Git\\git-bash.exe"

[HKEY_CLASSES_ROOT\*\shell\Open Git Bash\command]
@="\"C:\\Program Files\\Git\\git-bash.exe\" \"--cd=%1\""


; This will make it appear when you right click ON a folder
; The "Icon" line can be removed if you don't want the icon to appear

[HKEY_CLASSES_ROOT\Directory\shell\bash]
@="Open Git Bash"
"Icon"="C:\\Program Files\\Git\\git-bash.exe"

[HKEY_CLASSES_ROOT\Directory\shell\bash\command]
@="\"C:\\Program Files\\Git\\git-bash.exe\" \"--cd=%1\""


; This will make it appear when you right click INSIDE a folder
; The "Icon" line can be removed if you don't want the icon to appear

[HKEY_CLASSES_ROOT\Directory\Background\shell\bash]
@="Open Git Bash"
"Icon"="C:\\Program Files\\Git\\git-bash.exe"

[HKEY_CLASSES_ROOT\Directory\Background\shell\bash\command]
@="\"C:\\Program Files\\Git\\git-bash.exe\" \"--cd=%v.\""
```

The same can be done with any other program - just replace the texts and paths or commands and execute it with admin rights to add it.