# Bash tricks

## Table of Content
-   Bash tricks
    -   [Find ID of process that listen on given port](#find-id-of-process-that-listen-on-given-port)
    -   [Check state of disc](#check-state-of-disc)
    -   [Change permissions to files and separately to folders](#change-permisions-to-files-and-separetly-to-folders)
    -   [Move many files to directory using find + xargs + mv](#move-many-files-to-directory-using-find--xargs--mv)
-  Writing bash scripts
    -   [Basic advices](#basic-advices)

### Find ID of process that listen on given port
To find ID of process that running on specyfic port jjust run below command and change sample port 8080 to suite your needs.
```bash
lsof -wni tcp:8080
```

### Check state of disc
To check state of partitions, usb and others
```bash
df -Th
```

To check state of files and folders use

```bash
du -hs some-folder-or-file
```

### Search into files with regular expressions
It will seach for links with http or https in current directory (due to `.` on the end)
```bash
egrep -r "https?//api" .
```


### Change permisions to files and separetly to folders
How to change permissions only for catalogs (and subcatalogs)

```bash
find ~/public_html -type d -exec chmod 755 {} \;
```

and same only for files

```bash
find ~/public_html -type f -exec chmod 644 {} \;
```


### Move many files to directory using find + xargs + mv
Move files with sample extension of `m4a` (music file) to directory `~/my_folder`

```bash
find ./ -name "*.m4a" -print0 | xargs {} mv -t ~/my_folder
```

***

## Writing bash scripts

### Basic advices
-   While writing use syntax checkers: `sh` & `shellcheck`

### Exec script but not print on screen
```
echo "This will not show" > /dev/null
```
