# Setup guide for a development machine on Windows

This file contains the **Windows configuration** section of my [Setup guide for a development machine on Windows](https://github.com/EnduranceCode/windows-development-machine). The introduction to this guide as well as its full *Table of Contents* can be found on the [README.md](./README.md) file of this repository. The *Table of Contents* of this section is listed below.

## Table of Contents

2. [Windows configuration](#2-windows-configuration)
    1. [Keyboard and Mouse Software](#21-keyboard-and-mouse-software)
    2. [Windows Start Menu](#22-windows-start-menu)
    3. [Power Management](#23-power-management)

## 2. Windows Configuration

### 2.1. Keyboard and Mouse Software

[**Mouse and Keyboard Center**](https://support.microsoft.com/topic/mouse-and-keyboard-center-download-f5b10905-7887-eedb-2f1c-d0737a36a3b2) is an application that helps you personalize and customize how you work on your PC with your keyboard and mouse. Off course that this application shall only be installed on systems that use one of the [supported devices](https://support.microsoft.com/en-us/topic/which-devices-are-supported-by-microsoft-mouse-and-keyboard-center-61ac6d03-9cc1-d7c6-ca9b-c9c8ce4cb303).

#### 2.1.1. Installation

To install [**Mouse and Keyboard Center**](https://support.microsoft.com/topic/mouse-and-keyboard-center-download-f5b10905-7887-eedb-2f1c-d0737a36a3b2), download the latest version from [official downloads page](https://support.microsoft.com/topic/mouse-and-keyboard-center-download-f5b10905-7887-eedb-2f1c-d0737a36a3b2). Then, execute the downloaded file (there will be a prompt for elevated permissions that must be accepted).

Move the application shortcut to the `%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Tools` folder (Create the `Tools` folder if it doesn't exits).

### 2.2. Windows Start Menu

To have the Windows **Start Menu** with a [structure similar](https://specifications.freedesktop.org/menu-spec/latest/apa.html) to the one that have on my [Lubuntu](https://lubuntu.me) machines, the following folders must be created:

+ Audio & Video;
+ Development;
+ Graphics;
+ Network
+ Office
+ Utility

To create the above listed folders on the system wide **Start Menu**, open a Command Prompt console with *Administrator* privileges and execute the following commands:

    mkdir "%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Audio & Video"
    mkdir "%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Development"
    mkdir "%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Graphics"
    mkdir "%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Network"
    mkdir "%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Office"
    mkdir "%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Utility"

On the same Command Prompt console, move all the Office shortcuts to the folder `%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Office`.

To create the above listed folders on the user's **Start Menu**, open a regular Command Prompt console and execute the following commands:

    mkdir "%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Audio & Video"
    mkdir "%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Development"
    mkdir "%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Graphics"
    mkdir "%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Network"
    mkdir "%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Office"
    mkdir "%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Utility"

### 2.3. Power Management

Keeping the Laptop plugged after the battery is fully charged affect its health significantly, therefore its is recommended to keep the battery’s charge between 20% an 80%. On the Windows 10 **Power Management** we can setup an alarm/notification when the Laptop’s battery reaches a given low level. But there is no feature in Windows 10 to notify you when the battery reaches a given high level.

[John Howard](https://learn.microsoft.com/pt-pt/archive/blogs/jhoward/), Senior Program Manager in the Hyper-V team at Microsoft, [created a script](https://learn.microsoft.com/pt-pt/archive/blogs/jhoward/get-an-alert-when-my-battery-reaches-95) that gives an alert when the battery reaches 95%. I've adapted that script to give the alert when the the battery charges reaches 80% of it's capacity and I've stored on my [OneDrive](https://www.microsoft.com/microsoft-365/onedrive/online-cloud-storage), in my `dotfiles` folder.

If a [symlink](https://www.howtogeek.com/16226/complete-guide-to-symbolic-links-symlinks-on-windows-or-linux/) to the folder `%OneDriveCommercial%\dotfiles` isn't yet created the Windows `%USERPROFILE%`, create executing the below command from the Windows Command Line to be able to easily reference the `dotfiles` folder.

    mklink /J %USERPROFILE%\.dotfiles "%OneDriveCommercial%\dotfiles"

Then, to execute the above mentioned script on every Windows start up, inside the folder `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup`, create a *shortcut* pointing to the file `%USERPROFILE%\.dotfiles\scripts\FullBattery.vbs`.
