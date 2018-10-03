# Chocolatey

Use for all CLI inputs the admin powershell.

## Install it

Enter the provided code from https://chocolatey.org/install:

```ps1
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

## Install packages

Install either one package or more than one or load packages from a file:

```ps1
choco install [PACKAGE]
choco install [PACKAGE] [PACKAGE]
choco install [PACKAGE_LIST_FILE]
```

Read at *Backup installed packages* how to create a `[PACKAGE_LIST_FILE]`.

```ps1
choco install -y [PACKAGE]
choco install -y [PACKAGE] [PACKAGE]
choco install -y [PACKAGE_LIST_FILE]
```

Use the option `-y` if you want to automatically accept all the scripts and files.

## Update installed packages

Update the package managment system or any other package:

```ps1
choco upgrade [PACKAGE]
# choco upgrade chocolatey
```

Upgrade all packages:

```ps1
choco upgrade all
```

## Backup installed packages

### Save a list

Save all `choco install [package]` packages in a file

```ps1
choco list -lo -r > [PACKAGE_LIST_FILE]
# choco list -lo -r > list.txt
```

### Save a config file via `choco-package-list-backup`

```ps1
choco install choco-package-list-backup
choco-package-list-backup
```

`choco-package-list-backup` backups up your Chocolatey packages list every Monday at 6 AM in the background so you don't have to be bothered with it.

Enter the following and then open the file `choco-package-list-backup.xml` to configure this addon:

```ps1
cd \ProgramData\chocolatey\bin
start .
```

## Search for packages

```ps1
choco search [keyword]
```
