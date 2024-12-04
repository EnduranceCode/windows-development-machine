# Setup guide for a development machine on Windows

This file contains the **Desktop Software** section of my [Setup guide for a development machine on Windows](https://github.com/EnduranceCode/windows-development-machine). The introduction to this guide as well as its full *Table of Contents* can be found on the [README.md](./README.md) file of this repository. The *Table of Contents* of this section is listed below.

## Table of Contents

3. [Desktop Software](#3-desktop-software)
    1. [Autenticação.gov](#31-autenticaçãogov)
    2. [Ferdium](#32-ferdium)
    3. [GIMP](#33-gimp)
    4. [Inkscape](#34-inkscape)
    5. [PDFsam](#35-pdfsam)
    6. [SpeedCrunch](#36-speedcrunch)
    7. [Spotube](#37-spotube)
    8. [VLC](#38-vlc)

## 3. Desktop Software

### 3.1. Autenticação.gov

[**Autenticação.gov App**](https://www.autenticacao.gov.pt/) application allows the Portuguese citizens to take advantage of the electronic features of their Citizen Card.

#### 3.1.1. Installation

Download the [**Autenticação.gov App**](https://www.autenticacao.gov.pt/) from the [official downloads page](https://www.autenticacao.gov.pt/web/guest/cc-aplicacao).
Then, execute the downloaded file (there will be a prompt for elevated permissions that must be accepted).

It will, probably, be necessary to restart the machine to complete the [**Autenticação.gov App**](https://www.autenticacao.gov.pt/) installation.

Download the [**Autenticação.gov Plugin**](https://autenticacao.gov.pt/fa/ajuda/autenticacaogovpt.aspx) from the [official downloads page](https://autenticacao.gov.pt/fa/ajuda/autenticacaogovpt.aspx). Then, execute the downloaded file (there will be a prompt for elevated permissions that must be accepted).

Rename the [**Autenticação.gov App**](https://www.autenticacao.gov.pt/) *Start Menu* shortcut to *Autenticação.gov - App* and rename the [**Autenticação.gov Plugin**](https://www.autenticacao.gov.pt/) *Start Menu* shortcut to *Autenticação.gov - Plugin*. Then, move both shortcuts to the `%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Tools` folder (Create the `Tools` folder if it doesn't exits).

#### 3.1.2. Configuration

Go through the [**Autenticação.gov App**](https://www.autenticacao.gov.pt/) configuration options and set it as desired, but make sure that the auto start is disabled. Do the same with the [**Autenticação.gov Plugin**](https://autenticacao.gov.pt/fa/ajuda/autenticacaogovpt.aspx).

### 3.2. Ferdium

[**Ferdium**](https://ferdium.org/) is an application that helps to organize multiple web apps in one place for quick and easy access. It is very useful when, *e,g.*, you need to manage more than one [Team's](https://www.microsoft.com/microsoft-teams/group-chat-software/) account. Nonetheless, [**Ferdium**](https://ferdium.org/) can be replaced (probably with advantage) by Firefox's [Multi-Account Containers](https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/) extension.

#### 3.2.1. Installation

Download [**Ferdium**](https://ferdium.org/) from the [official downloads page](https://ferdium.org/download). Then, execute the downloaded file.

Move the [**Ferdium**](https://ferdium.org/) *Start Menu* *shortcut* to the `%APPDATA%\Microsoft\Windows\Start Menu\Programs\Tools` folder (Create the `Tools` folder if it doesn't exits).

To enable sound on [**Ferdium**](https://ferdium.org/), at least with [Team's](https://www.microsoft.com/microsoft-teams/group-chat-software/) and bluetooth sound devices, on the [Windows](https://www.microsoft.com/en-us/windows) settings, select `System->Sound`. On the `Sound`tab, scroll down and click on the option `App volume and devices preferences`. Then, for the [**Ferdium**](https://ferdium.org/), replace `Default` in the *Output* and *Input* dropdowns with the device you want to use with [**Ferdium**](https://ferdium.org/).

### 3.3. GIMP

[**GIMP**](https://www.gimp.org/), an acronym for GNU Image Manipulation Program, is a multi-platform photo manipulation tool.

#### 3.3.1. Installation

To install [**GIMP**](https://www.gimp.org/), open a PowerShell console and execute the upcoming command to execute the installation from the [Microsoft Store](https://apps.microsoft.com/detail/XPDM27W10192Q0).

    winget install XPDM27W10192Q0 -s msstore

Rename the [**GIMP**](https://www.gimp.org/) *Start Menu* shortcut to *GIMP* and then move it to the `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Graphics` folder (Create the `Graphics` folder if it doesn't exits).

### 3.4. Inkscape

[**Inkscape**](https://inkscape.org/) is a Free and open source vector graphics multi-platform editor that uses the standardized SVG file format as its main format, which is supported by many other applications including web browsers.

#### 3.4.1. Installation

To install [**Inkscape**](https://inkscape.org/), open a PowerShell console and execute the upcoming command to execute the installation from the [Microsoft Store](https://apps.microsoft.com/detail/9PD9BHGLFC7H).

    winget install 9PD9BHGLFC7H -s msstore

### 3.5. PDFsam

[**PDFsam Basic**](https://pdfsam.org/pdfsam-basic/) is a free and open-source cross-platform desktop application to split, merge, extract pages, rotate and mix PDF documents.

#### 3.5.1. Installation

To install [**PDFsam Basic**](https://pdfsam.org/pdfsam-basic/), execute the upcoming commands on a PowerShell console.

    scoop bucket add extras
    scoop install extras/pdfsam

Move the [**PDFsam Basic**](https://pdfsam.org/pdfsam-basic/) *Start Menu* shortcut from the folder `C:\Users\rferrcan\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Scoop Apps`to the folder `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Office` (Create the `Office` folder if it doesn't exits).

### 3.6. SpeedCrunch

[**SpeedCrunch**](http://www.speedcrunch.org) is a high-precision scientific calculator featuring a fast, keyboard-driven user interface. It is free and open-source software, licensed under the GPL.

#### 3.6.1. Installation

To install [**SpeedCrunch**](http://www.speedcrunch.org), execute the upcoming commands on a PowerShell console.

    scoop bucket add extras
    scoop install extras/speedcrunch

Move the [**SpeedCrunch**](http://www.speedcrunch.org) *Start Menu* shortcut from the folder `C:\Users\rferrcan\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Scoop Apps` to the folder `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Utility` (Create the `Utility` folder if it doesn't exits).

If the keyboard in use has a special key to start a calculator, edit the [Windows Registry](https://learn.microsoft.com/troubleshoot/windows-server/performance/windows-registry-advanced-users) to assign [**SpeedCrunch**](http://www.speedcrunch.org) to the mentioned key.

To open the [Registry Editor](https://www.bleepingcomputer.com/tutorials/how-to-use-the-windows-registry-editor/) as an administrator, click the Windows *Start Menu*, type `regedit` in the search field and then click on the *Run as an administrator* option that is shown. Then, navigate to the [key](https://www.lifewire.com/what-is-a-registry-key-2625999) `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\AppKey\18` and add a new string [registry value](https://www.lifewire.com/what-is-a-registry-value-2626042) with the value *ShellExecute* in the `Name` field and with value of the full path of the [**SpeedCrunch**](http://www.speedcrunch.org) executable file in the `Data` field.

### 3.7. Spotube

[**Spotube**](https://spotube.krtirtho.dev/) is a fast, modern, lightweight & efficient Spotify Music Client for every platform.

#### 3.7.1. Installation

To install [**Spotube**](https://spotube.krtirtho.dev/), open a PowerShell console and execute the upcoming command to execute the installation with the [official package](https://spotube.krtirtho.dev/other-downloads/package-manager).

    winget install --id KRTirtho.Spotube

### 3.8. VLC

VLC is a free and open source cross-platform multimedia player and framework that plays most multimedia files as well as DVDs, Audio CDs, VCDs, and various streaming protocols.

#### 3.8.1. Installation

To install [**VLC**](https://www.videolan.org/), open a PowerShell console and execute the following commands:

    scoop bucket add extras
    scoop install extras/vlc

Move the [**VLC**](https://www.videolan.org/) *Start Menu* shortcut from the folder `C:\Users\rferrcan\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Scoop Apps` to the `%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs\Audio & Video` folder (Create the `Audio & Video` folder if it doesn't exits).
