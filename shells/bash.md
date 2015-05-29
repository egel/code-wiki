# Bash tricks

## Table of Content
  - [Find ID of process that listen on given port](#find-id-of-process-that-listen-on-given-port)
  - [Check state of disc](#check-state-of-disc)
  - [Change permissions to files and separately to folders]

### Find ID of process that listen on given port
To find ID of process that running on specyfic port jjust run below command and change sample port 8080 to suite your needs.

    $ lsof -wni tcp:8080

### Check state of disc
To check state of partitions, usb and others

    $ df -Th

To check state of files and folders use

    $ du -hs some-folder-or-file

### Change permisions to files and separetly to folders
How to change permissions only for catalogs (and subcatalogs)

    $ find ~/public_html -type d -exec chmod 755 {} \;

and same only for files

    $ find ~/public_html -type f -exec chmod 644 {} \;

