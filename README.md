# Sample project for remote Raspberry Pi debugging

## Overview

* Currently remote development is not supported on Raspberry Pi. Hence, the development must be done on local machine, files should be copied on remote desktop and then we can debug remotely
* The project includes sample setup to ease the environment setup

## Getting started

### Desktop (Work machine)

* Install the .NET SDK on your Desktop
* Install VSCode
* Install C# Extension in VSCode
* Install WinSCP (used for synchronizing files to remote)

### Remote (Raspberry Pi)

* Install .NET SDK. For example, follow instructions from https://www.petecodes.co.uk/install-and-use-microsoft-dot-net-5-with-the-raspberry-pi/

Note: The given link is for .NET5 SDK , if you are using different version make sure to install the right SDK 
```
wget -O - https://raw.githubusercontent.com/pjgpetecodes/dotnet5pi/master/install.sh | sudo bash
```
* Install the .NET runtime on your Remote machine (such as RPi) (Reference: https://docs.microsoft.com/en-us/dotnet/iot/debugging?pivots=vscode)
```
curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
```

## Project Setup on local

### If creating a new project

* Create a folder such as "hello-world"

```
md hello-world
```
* Create a new dot net console application

```
dotnet new console
```

### Setup for debugging

* Setup for debugging:
    * Copy .vscode folder from this sample project
    * Copy winscp.txt file from this sample project
    * Edit .vscode/settings.json file to modify the settings for your project such as remote url, username and password

## Project Setup on remote

* Choose/ create a work directory for your project. For example, if your project is called RPi

```
mkdir -p ~/work/RPi
```

* Now you should have a folder such as /home/pi/work/RPi

## Start debugging

In VSCode, you should be able to go to debug and choose .NET Core Launch (Remote)
