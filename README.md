# AlpineWSL-web
Alpine Linux on WSL (Windows 10 1803 or later) with pre-installed web development tools
based on [wsldl](https://github.com/yuk7/wsldl) and [AlpineWSL](https://github.com/yuk7/AlpineWSL)

![screenshot](https://raw.githubusercontent.com/wiki/yuk7/wsldl/img/Alpine_Arch_Cent.png)

[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/c4software/AlpineWSL-web/build-zip.yaml?style=flat-square)](https://github.com/c4software/AlpineWSL-web/actions/workflows/build-zip.yaml)
[![Github All Releases](https://img.shields.io/github/downloads/c4software/AlpineWSL-web/total.svg?style=flat-square)](https://github.com/c4software/AlpineWSL-web/releases/latest)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
![License](https://img.shields.io/github/license/c4software/AlpineWSL-web.svg?style=flat-square)

### [Download](https://github.com/c4software/AlpineWSL-web/releases/latest)

## What's included?
This distribution comes with essential web development tools pre-installed:
- **PHP 8.3** with extensions:
  - php83-tokenizer
  - php83-session
  - php83-pdo
  - php83-dom
  - php83-xml
  - php83-xmlwriter
  - php83-fileinfo
  - php83-pdo_sqlite
  - php83-pdo_mysql
  - php83-simplexml
- **Node.js & npm** - JavaScript runtime and package manager
- **Git** - Version control system
- **Vim** - Text editor
- **Bash** - Shell environment

Perfect for getting started with web development on WSL without the hassle of setting up your environment!

## Requirements
* Windows 10 1803 April 2018 Update x64 or later.
* Windows Subsystem for Linux feature is enabled.

## Install
#### 1. [Download](https://github.com/c4software/AlpineWSL-web/releases/latest) installer zip

#### 2. Extract all files in zip file to same directory

#### 3.Run Alpine.exe to Extract rootfs and Register to WSL
Exe filename is using to the instance name to register.
If you rename it, you can register with a different name and have multiple installs.


## How-to-Use(for Installed Instance)
#### exe Usage
```dos
Usage :
    <no args>
      - Open a new shell with your default settings.

    run <command line>
      - Run the given command line in that instance. Inherit current directory.

    runp <command line (includes windows path)>
      - Run the given command line in that instance after converting its path.

    config [setting [value]]
      - `--default-user <user>`: Set the default user of this instance to <user>.
      - `--default-uid <uid>`: Set the default user uid of this instance to <uid>.
      - `--append-path <true|false>`: Switch of Append Windows PATH to $PATH
      - `--mount-drive <true|false>`: Switch of Mount drives
      - `--default-term <default|wt|flute>`: Set default type of terminal window.

    get [setting]
      - `--default-uid`: Get the default user uid in this instance.
      - `--append-path`: Get true/false status of Append Windows PATH to $PATH.
      - `--mount-drive`: Get true/false status of Mount drives.
      - `--wsl-version`: Get the version os the WSL (1/2) of this instance.
      - `--default-term`: Get Default Terminal type of this instance launcher.
      - `--lxguid`: Get WSL GUID key for this instance.

    backup [contents]
      - `--tar`: Output backup.tar to the current directory.
      - `--reg`: Output settings registry file to the current directory.

    clean
      - Uninstall that instance.

    help
      - Print this usage message.
```


#### How to uninstall instance
```dos
>Alpine.exe clean

```

## How-to-Build
AlpineWSL-web can build on GNU/Linux or WSL.

`curl`,`bsdtar`,`tar`(gnu) and `sudo` is required for build.
```shell
$ make
```

### Basic Params
|  Parameter |  Value  |  Default  |
| ---- | ---- | ---- |
|  LNCR_EXE  |  launcher file name  | Alpine.exe |
|  OUT_ZIP  |  zip file name  | Alpine.zip |
|  DLR  |  file downloader  | curl |
|  DLR_FLAGS  |  downloader flags  | -L |
|  BASE_URL  |  base rootfs url  | https:~ |
|  ROOTFS_TARBALL_CKSM_URL  |  sha-sum for the base rootfs tarball  |  https:~ |
