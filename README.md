# Linux-Cheatsheet
This cheatsheet is summarized from personal experience and other online tutorials.

> Disclaimer:
>   This cheatsheet is summarized from personal experience and other online tutorials.
>   It should not be considered as an official advice.

---

## Basic directory constraction
```
Directory    Description
/            root
├── bin      primitive command of linux
├── boot     boot files
├── dev      device files
├── etc      setting files
├── home     user's home directory
├── lib      shared library
├── lib64    shared library for 64bit system
├── media    media device
├── mnt      temporaly mount directory, e.g. external hdd, sd-card, cd-rom, etc.
├── opt      additional application
├── proc     process information, etc.
├── root     home directory for root
├── sbin     command files for system
├── sys      system files
├── tmp      temporaly files, delete during reboot
├── usr      applications for each users
├── var      variable files
```

## Commands for directory/file
### for directory
| Command | Description |
| --- | --- |
| pwd | display current directory |
| cd | move to home directory |
| cd .. | move to upper directory |
| cd [dir] | move to [dir] |
| mkdir [dir] | make directory named [dir] |

### for file
| Command | Description |
| --- | --- |
| cat [file] | show content of file |
| more [file] | show content of file |
| less [file] | show content of file |
| cp [src] [dst] | copy file from [src] to [dst] |
| cp -r [src] [dst] | copy files include directory from [src] to [dst] |
| mv [src] [dst] | move files from [src] to [dst], rename |
| rm [file] | remove [file] |
| rm -r [dir] | remove [dir], dir+files |

### packaging
| Command | Description |
| --- | --- |
| tar -xvf file.tar | unpack file.tar |
| tar -zvxf file.tar.gz | unpack file.tar.gz |
| zip -r -q file.zip [dir] | compress [dir] to file.zip without display progress(-q) |

### link
| Command | Description |
| --- | --- |
| ln -sf [target] [link-file] | make symblic link[link] of [target] |
| ln [target] [link] | make hard link[link] of [target], copy entity of [target] |

## System management
### General
| Command | Description |
| --- | --- |
| df -h | display file-system information |
| du -h | display usage of storage, display each files' size |
| ps | display processes |
| ps au | display process of all users |
| sudo reboot | reboot system |
| sudo shutdown -h now | shutdown system now |
| date | display system date-time |
| date -s "dd/mm/yy HH:MM" | set date-time |

### Network
| Command | Description |
| --- | --- |
| wget [http://.../hoge.ext] | get file located in network |
| ssh user@example.com | ssh to the [example.com] as [user] |
| ssh -i [private-key] user@example.com | ssh to the [example.com] as [user] with [private-key] |
| scp [local-file] user@example.com:~/ | send [local-file] to user's home directory of example.com |

### User
| Command | Description |
| --- | --- |
| who | display login users |
| whoami | display own account name |
| su [user-name] | switch user to [user-name] |
| sudo [command] | excute [command] as root account |
| adduser [name] | add new user as [name] |
| gpasswd -a [user] sudo | add sudo permission to [user] |

### Path, environment


## Library management

## Text editing

## Misc.
### git
| Command | Description |
| --- | --- |
| git clone https://... | clone repository from 'http://...' |
| git tag | display all tag |
| git branch | display current branch |
| git checkout [branch-name] | checkout [branch-name], change current branch to [branch-name] |
| git checkout -b [new-branch] | create [new-branch] and checkout [new-branch] |
| git pull origin master | pull 'master' branch from 'origin', pull=fetch+merge |
| git submodule update -init | initialize local repository, shold be used after pull latest branch from remote |
| git add . | add all files under '.' |
| git commit | commit all modify |
| git push origin [branch] | push [branch] to origin |


