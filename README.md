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
#### for directory
| Command | Description |
| --- | --- |
| pwd | display current directory |
| cd | move to home directory |
| cd .. | move to upper directory |
| cd [dir] | move to [dir] |
| mkdir [dir] | make directory named [dir] |

#### for file
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

#### packaging
| Command | Description |
| --- | --- |
| tar -xvf file.tar | unpack file.tar |
| tar -zvxf file.tar.gz | unpack file.tar.gz |
| zip -r -q file.zip [dir] | compress [dir] to file.zip without display progress(-q) |

#### link
| Command | Description |
| --- | --- |
| ln -sf [target] [link-file] | make symblic link[link] of [target] |
| ln [target] [link] | make hard link[link] of [target], copy entity of [target] |

## System management
#### General
| Command | Description |
| --- | --- |
| df -h | display file-system information |
| du -h | display usage of storage, display each file size |
| ps | display processes |
| ps au | display process of all users |
| sudo reboot | reboot system |
| sudo shutdown -h now | shutdown system now |
| date | display system date-time |
| date -s "dd/mm/yy HH:MM" | set date-time |

#### Permission
| Command | Description |
| --- | --- |
| chmod u+w [file] | add write permission to user |
| chmod ug+r [file] | add read permission to user&group |
| chmod o-w [file] | delete write permission from others |

[note]
 - u: user, g: group,  o: others, a: all
 - r: read, w: write,  x: execute
 - +: add,  -: delete, =: set

| Command | Description |
| --- | --- |
| chown root:root [file] | change [file]'s owner to root |

#### Network
| Command | Description |
| --- | --- |
| wget [http://.../hoge.ext] | get file located in network |
| ssh user@example.com | ssh to the [example.com] as [user] |
| ssh -i [private-key] user@example.com | ssh to the [example.com] as [user] with [private-key] |
| scp [local-file] user@example.com:~/ | send [local-file] to user's home directory of example.com |
| scp -i [private-key] [local-file] user@example.com:~/ | send [local-file] to user's home directory of example.com with [private-key] |

#### User
| Command | Description |
| --- | --- |
| who | display login users |
| whoami | display own account name |
| su [user-name] | switch user to [user-name] |
| sudo [command] | excute [command] as root account |
| adduser [name] | add new user as [name] |
| gpasswd -a [user] sudo | add sudo permission to [user] |

#### Environment variable
| Command | Description |
| echo 'export ...' >> ~/.bashrc | add path setting 'export ...' |
| source ~/.bashrc | reload .bashrc file |


## Library management
<!--
There are mainly two library management systems. One is "dep" format system, another is "rpm" format system.
| Lib-management system | Linux distribution |
| --- | --- |
| dep format | Debian, Ubuntu, Raspbian, etc. |
| rpm format | RedHat, CentOS, etc. |
-->
#### "dep" format system: apt (for Debian, Ubuntu, Raspbian, etc.)
| Command | Description |
| --- | --- |
| apt-get install [lib-name] | install [lib-name] |


#### "rpm" format system: yum (for RedHat, CentOS, etc.)
| Command | Description |
| --- | --- |
| yum install [lib-name] | install [lib-name] |


## Text editing
"vi" is default text editor in Linux. We can also use "vim" instead. "vim" is more powerful editor. Here is summary of "vim" command.
If there is no "vim", you can install "vim" by following command.
```
sudo apt-get update         # update package list
sudo apt-get install vim    # install vim
vim [file]                  # open [file] in vim
```

There are mainly three mode in vim; normal mode, visual mode and insert mode.
- normal mode: can modify text by various commands. part of commands will be introduced in following table.
- visual mode: can select text in visual. part of commands will be introduced in following table.
- insert mode: can input text as is.

#### command for text editing
| Command | Description |
| --- | --- |

**move**
| j | move to next line |
| k | move to previous line |
| h | move to left char |
| l | move to right char |
| w | move to next word |
| b | back to previous word |
| 0 | move to head of the current line |
| ^ | move to the head of the current sentense |
| $ | move to the tail of the current line |
| L | move to the bottom of the screen |
| H | move to the top of the screen |
| gg | move to the top of the file |
| G  | move to the bottom of the file |
| :7 | move to the 7th line, or can use any number |

**edit**
| x | delete char under the cursor |
| yy | copy current line |
| dd | delete current line |
| p  | paste |
| u  | undo previous command |
| [Ctrl]v | redo canceled command |
| [Ctrl]a | increment the value under the cursor |
| [Ctrl]x | decrement the value under the cursor |
| [Ctrl]p | completion the word |



## Misc.
#### git
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
| git commit -m "commit-comment" | commit all modify with comment |
| git push origin [branch] | push [branch] to origin |


<!--
#### c/c++

#### python

#### virtualenv

#### Deep Learning framework

#### Tips for trouble shooting

-->

