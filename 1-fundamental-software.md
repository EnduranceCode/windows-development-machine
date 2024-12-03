# Setup guide for a development machine on Windows

This file contains the **Fundamental Software** section of my [Setup guide for a development machine on Windows](https://github.com/EnduranceCode/windows-development-machine). The introduction to this guide as well as its full *Table of Contents* can be found on the [README.md](./README.md) file of this repository. The *Table of Contents* of this section is listed below.

## Table of Contents

1. [Fundamental Software](#1-fundamental-software)
    1. [Browser](#11-browser)
    2. [Windows Subsystem for Linux](#12-windows-subsystem-for-linux)
    3. [Windows Terminal](#13-windows-terminal)
    4. [Package Manager](#14-package-manager)
    5. [Git & Git Bash](#15-git--git-bash)
    6. [KeePassXC](#16-keepassxc)

## 1. Fundamental Software

### 1.1. Browser

With [Lubuntu](https://lubuntu.me) I normally choose [Firefox](https://www.mozilla.org/firefox/new/) as my default browser and on Windows I used to choose [**Google Chrome**](https://www.google.com/chrome/). At the moment, I'm also trying to use [Firefox](https://www.mozilla.org/firefox/new/) on Windows.

#### 1.1.1. Firefox

[**Firefox**](https://www.mozilla.org/firefox/new/) is a cross-platform web browser developed by [Mozilla](https://en.wikipedia.org/wiki/Mozilla).

##### 1.1.1.1. Installation

To install [**Firefox**](https://www.mozilla.org/firefox/new/), start by downloading the latest version from [official downloads page](https://www.mozilla.org/firefox/new/). Then, execute the downloaded file (there will be a prompt for elevated permissions that must be accepted).

##### 1.1.1.2. Configuration

Set [**Google Chrome**](https://www.google.com/chrome/) preferences as desired and then install the following extensions:

+ [AWS Extend Switch Roles](https://addons.mozilla.org/firefox/addon/aws-extend-switch-roles3/)
+ [ColorZilla](https://addons.mozilla.org/firefox/addon/colorzilla/)
+ [Firefox Multi-Account Containers](https://addons.mozilla.org/firefox/addon/multi-account-containers/)
+ [KeePassXC-Browser](https://addons.mozilla.org/firefox/addon/keepassxc-browser/)
+ [Omnivore](https://addons.mozilla.org/firefox/addon/omnivore/)
+ [Proxy SwitchyOmega](https://addons.mozilla.org/firefox/addon/switchyomega/)
+ [Raindrop.io](https://addons.mozilla.org/firefox/addon/raindropio/)
+ [Tab Session Manager](https://addons.mozilla.org/firefox/addon/tab-session-manager/)
+ [Wapplyzer](https://addons.mozilla.org/firefox/addon/wappalyzer/)

Set the options of all the above extensions. Use the extensions settings backups/exports stored in the folder `%OneDriveCommercial%\dotfiles\browser\extensions` to better customize the relevant extension.

#### 1.1.2. Google Chrome

[**Google Chrome**](https://www.google.com/chrome/) is a cross-platform web browser developed by [Google](https://en.wikipedia.org/wiki/Google).

##### 1.1.2.1. Installation

To install [**Google Chrome**](https://www.google.com/chrome/), start by downloading the latest version from [official downloads page](https://www.google.com/chrome/). Then, execute the downloaded file (there will be a prompt for elevated permissions that must be accepted).

##### 1.1.2.2. Configuration

Set [**Google Chrome**](https://www.google.com/chrome/) preferences as desired and then install the following extensions:

+ [AWS Extend Switch Roles](https://chrome.google.com/webstore/detail/aws-extend-switch-roles/jpmkfafbacpgapdghgdpembnojdlgkdl)
+ [ColorZilla](https://chromewebstore.google.com/detail/colorzilla/bhlhnicpbhignbdhedgjhgdocnmhomnp)
+ [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa)
+ [KeePassXC-Browser](https://chrome.google.com/webstore/detail/keepassxc-browser/oboonakemofpalcgghocfoadofidjkkk)
+ [Omnivore](https://chromewebstore.google.com/detail/omnivore/blkggjdmcfjdbmmmlfcpplkchpeaiiab)
+ [Proxy SwitchyOmega](https://chrome.google.com/webstore/detail/proxy-switchyomega/padekgcemlokbadohgkifijomclgjgif)
+ [Raindrop.io](https://chromewebstore.google.com/detail/raindropio/ldgfbffkinooeloadekpmfoklnobpien)
+ [Tab Session Manager](https://chrome.google.com/webstore/detail/tab-session-manager/iaiomicjabeggjcfkbimgmglanimpnae)
+ [Wapplyzer](https://chromewebstore.google.com/detail/wappalyzer-technology-pro/gppongmhjkpfnbhagpmjfkannfbllamg)

Set the options of all the above extensions. Use the extensions settings backups/exports stored in the folder `%OneDriveCommercial%\dotfiles\browser\extensions` to better customize the relevant extension.

### 1.2. Windows Subsystem for Linux

[Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/windows/wsl/) lets developers run a GNU/Linux environment directly on Windows.

#### 1.2.1. Installation

Follow the [Official instructions](https://learn.microsoft.com/windows/wsl/install-manual) to manually [enable](https://learn.microsoft.com/windows/wsl/install-manual#step-1---enable-the-windows-subsystem-for-linux) the [**WSL**](https://learn.microsoft.com/windows/wsl/), executing the upcoming command on a PowerShell console with *administrator privileges*.

    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

Before restarting the machine, execute the below command on the same PowerShell console to [enable the Virtual Machine feature](https://learn.microsoft.com/windows/wsl/install-manual#step-3---enable-virtual-machine-feature).

    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

Reboot the machine to be able to proceed with the [**WSL**](https://learn.microsoft.com/windows/wsl/) installation.

After rebooting your machine, set [**WSL 2**](https://learn.microsoft.com/windows/wsl/basic-commands#set-wsl-version-to-1-or-2) as your default version. executing the below command on a standard PowerShell console.

    wsl --set-default-version 2

[List all available Linux distributions](https://learn.microsoft.com/windows/wsl/basic-commands#list-available-linux-distributions) executing the bellow command on a standard PowerShell console.

    wsl --list --online

From the output of the above command, get the latest available [Ubuntu LTS version](https://ubuntu.com/about/release-cycle) and use it to replace the label **{DISTRO_NAME}** in the upcoming command. Then, execute it on a standard PowerShell console to set the [default distribuition](https://learn.microsoft.com/windows/wsl/basic-commands#set-default-linux-distribution).

    wsl --set-default {DISTRO_NAME}

Replace the label **{DISTRO_NAME}**, in the upcoming command, with the name of the latest available [Ubuntu LTS version](https://ubuntu.com/about/release-cycle) and then execute it on a standard PowerShell console to [install](https://learn.microsoft.com/windows/wsl/install#install-wsl-command) the latest available [Ubuntu LTS version](https://ubuntu.com/about/release-cycle).

    wsl --install -d {DISTRO_NAME}

The execution of the above command will [require elevation](https://learn.microsoft.com/windows/security/application-security/application-control/user-account-control/how-it-works), and therefore, Windows will prompt you to [elevate](https://learn.microsoft.com/windows/security/application-security/application-control/user-account-control/how-it-works#the-uac-user-experience). If you choose not to [elevate](https://learn.microsoft.com/windows/security/application-security/application-control/user-account-control/how-it-works#the-uac-user-experience), the [**WSL**](https://learn.microsoft.com/windows/wsl/) installation will fail.

To [update](https://learn.microsoft.com/windows/wsl/troubleshooting#updating-wsl) the [**WSL**](https://learn.microsoft.com/windows/wsl/) installation, execute the following command on a standard PowerShell console.

    wsl --update

On a regular PowerShell console, execute the below command to list the installed Linux distributions and check if everything is correct:

    wsl --list --verbose

If [Ubuntu](https://ubuntu.com/) is not running with [**WSL 2**](https://learn.microsoft.com/windows/wsl/), replace the **{LABEL}** in the below command as appropriate and execute it on a standard PowerShell console.

    wsl --set-version {DISTRO_NAME} 2

> **Label Definition**
>
> + **{DISTRO_NAME}** : Name of the Linux distribution to be executed with WSL 2

#### 1.2.2. Configuration

Once the process of installing [Ubuntu](https://ubuntu.com/) on [**WSL**](https://learn.microsoft.com/windows/wsl/) is complete, open the distribution using the *Start Menu*. You will be asked to [create a User and Password](https://learn.microsoft.com/windows/wsl/setup/environment#set-up-your-linux-username-and-password) for your [Ubuntu](https://ubuntu.com/) installation.

Configure the settings for your [Ubuntu](https://ubuntu.com/) installation, by using the `wsl.conf` file that is stored on `/etc` folder of every [**WSL**](https://learn.microsoft.com/windows/wsl/) distribuition. Open the file `/etc/wsl.conf` with the [nano text editor](https://www.nano-editor.org/), executing the below command on a [Ubuntu](https://ubuntu.com/) terminal.

    nano /etc/wsl.conf

To change the [default mount location](https://learn.microsoft.com/windows/wsl/wsl-config#automount-settings) of the Windows `C:\` drive from the default `/mnt/c` to `/c`, add the upcoming code snippet to the `/etc/wsl.conf` file.

    [automount]
    root=/

Then, to [enable systemd support](https://learn.microsoft.com/windows/wsl/wsl-config#systemd-support), add the upcoming code snippet to the same `/etc/wsl.conf` file.

    [boot]
    systemd=true

Save the changes with the command `CTRL + O` and then exit the [nano text editor](https://www.nano-editor.org/) with the command `CTRL + X`.

To enable the changes made on the `wsl.conf` file, youl will need to to restart your [**WSL**](https://learn.microsoft.com/windows/wsl/) instances. It can be done with the execution of the bellow command on a standard PowerShell console.

    wsl.exe --shutdown

 Once [Ubuntu](https://ubuntu.com/) restarts, *systemd* should be running. You can confirm executing the below command on a [Ubuntu](https://ubuntu.com/) terminal, which will show the status of your services.

    systemctl list-unit-files --type=service

The article [Set up a WSL development environment](https://learn.microsoft.com/windows/wsl/setup/environment) has some good optional advices to setup a development environment with  [**WSL**](https://learn.microsoft.com/windows/wsl/), but one that is almost mandatory is the installation of the [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701).

#### 1.2.3. Update, upgrade and install additional packages

It's recommended to regularly update and upgrade your packages using [Ubuntu](https://ubuntu.com/)'s package manager. This is done with the following command:

    sudo apt update && sudo apt full-upgrade

Aditional sofware can be installed using [Ubuntu](https://ubuntu.com/)'s package manager, exactly as in any other [Ubuntu](https://ubuntu.com/) installation.

To be able to install software from its source code, you need to make sure your system has a C++ compiler. The `build-essentials` packages are meta-packages that include all the necessary tools for compiling software. You can install it with the following command:

    sudo apt install build-essential

To verify if the `build-essentials` installation was properly made, check the output of the following command:

    gcc --version

### 1.3. Windows Terminal

The [**Windows Terminal**](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701) is a terminal application for users of command-line tools and shells like Command Prompt, PowerShell, and WSL. Its main features include multiple tabs, panes, Unicode and UTF-8 character support, a GPU accelerated text rendering engine, and custom themes, styles, and configurations.

#### 1.3.1. Installation

Open the [Microsoft Store](https://aka.ms/wslstore) and install the [**Windows Terminal**](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701).

### 1.4. Package Manager

A package manager is a software that easily automates the installation, upgradation, and configuration of third-party software or dependencies. [**Chocolatey**](https://chocolatey.org/) and [**winget**](https://github.com/microsoft/winget-cli) are both package managers for Windows software. Nowadays, I prefer [**winget**](https://github.com/microsoft/winget-cli) over [**Chocolatey**](https://chocolatey.org/) because [**winget**](https://github.com/microsoft/winget-cli) can be used to install software from the [Microsoft Store](https://apps.microsoft.com/home).

#### 1.4.1. Install winget

Windows Package Manager [**winget**](https://github.com/microsoft/winget-cli) command-line tool is available on Windows 11 and modern versions of Windows 10 as a part of the [App Installer](https://apps.microsoft.com/detail/9NBLGGH4NNS1). To check if [**winget**](https://github.com/microsoft/winget-cli) is available, open a PowerShell console and execute the following command:

    winget --version

If [**winget**](https://github.com/microsoft/winget-cli) is already available on your system, the current version of the software will be displayed and now you should make sure it is updated with the latest version.

If you need to install [**winget**](https://github.com/microsoft/winget-cli), open the [Microsoft Store](https://aka.ms/wslstore) and install the [App Installer](https://apps.microsoft.com/detail/9NBLGGH4NNS1) because that's how [**winget**](https://github.com/microsoft/winget-cli) is distribuited.

Upgrading applications with [**winget**](https://github.com/microsoft/winget-cli) is very easy. To identify which apps are in need of an update, open a PowerShell console and execute the following command:

    winget upgrade

The above command will output a list of which app (if any) have an available update. To upgrade all applications with an available update, open a PowerShell console and execute the following command:

    winget upgrade --all

When running [**winget**](https://github.com/microsoft/winget-cli) without administrator privileges, some applications may [require elevation](https://learn.microsoft.com/windows/security/application-security/application-control/user-account-control/how-it-works) to install. On those cases, Windows will prompt you to elevate. If you choose not to elevate, the application will fail to install/upgrade.

Check the [official documentation](https://learn.microsoft.com/windows/package-manager/winget/) to know the full potential of [**winget**](https://github.com/microsoft/winget-cli).

#### 1.4.2. Install Scoop

[**Scoop**](https://scoop.sh/) installs programs from the command line with a minimal amount of friction as it doesn't require Admin privileges.

To [**Scoop**](https://scoop.sh/), open a PowerShell console and execute the following commands:

    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression

To check if everything was properly installed and if further actions are necessary, execute the following command:

    scoop checkup

If the above command outputs a warning  stating that *Windows Developer Mode* is not enabled, you should consider enabling it because operations relevant to [symlinks](https://blogs.windows.com/windowsdeveloper/2016/12/02/symlinks-windows-10/) may fail without proper rights.

To enable *Windows Developer Mode*, follow the [official instructions](https://learn.microsoft.com/windows/apps/get-started/enable-your-device-for-development).

The output of the command `scoop checkup`, might show some recomendations to install some additional packages. If it does, install it using the recommended commands.

To check if all issues were solved with the previous actions, re-run the following command:

    scoop checkup

The output of the above command, should now be `No problems identified!`.

To list all apps installed with [**Scoop**](https://scoop.sh/), execute the following command:

    scoop list

#### 1.4.3. Install Chocolatey

If you are going to do your development work on the `Windows Native File System` (instead of doing it exclusively on the `WSL File System`) you should also install [**Chocolatey**](https://chocolatey.org/).

Before proceeding with the installation of [**Chocolatey**](https://chocolatey.org/), you must ensure **Get-ExecutionPolicy** is not ***Restricted***. The upcoming command, executed on a PowerShell console with *Administrator* privileges. will output the current [execution policy](https://go.microsoft.com/fwlink/?LinkID=135170).

    Get-ExecutionPolicy

If the output of the above command shows ***Restricted***, then run the following command on the same PowerShell console:

    Set-ExecutionPolicy Bypass -Scope Process

Or the preferable upcoming command, for quite a [bit more security](https://chocolatey.org/install).

    Set-ExecutionPolicy AllSigned

Then, on the same PowerShell console, execute the below command to install [**Chocolatey**](https://chocolatey.org/).

    Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

To list the installed chocolatey packages, execute the following command on a PowerShell console:

    choco list

### 1.5. Git & Git Bash

[**Git**](https://git-scm.com/) is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

#### 1.5.1. Installation

##### 1.5.1.1. Installation on the WSL File System

[**Git**](https://git-scm.com/) is included on the [Ubuntu](https://ubuntu.com/) submodule of [WSL](https://learn.microsoft.com/windows/wsl/), therefore, it's not necessary to install it on the `WSL File System`.

##### 1.5.1.2. Installation on the Windows Native File System

**Git Bash** comes included as part of the [Git's Windows package](https://git-scm.com/download/win) and is an application for Microsoft Windows environments which provides an emulation layer for a [**Git**](https://git-scm.com/) command line experience.

[**Git**](https://git-scm.com/), as stated on the [official downloads page](https://git-scm.com/download/win), can be installed on the `Windows Native File System` with [**winget**](https://github.com/microsoft/winget-cli). To [**Git**](https://git-scm.com/), open a PowerShell console and execute the following commands:

    winget install --id Git.Git -e --source winget

The above command will start the [**Git**](https://git-scm.com/) installation wizard that will prompt you with a few questions.

On the *Select Start Menu Folder* step of the installation program, insert the following text on the input box:

+ Development

On the *Select Components* step of the installation program, make sure that you will only check the following checkboxes:

+ Git LFS (Large File Support);
+ Associate .git* configuration files with the default text editor;
+ Associate .sh files to be run with Bash
+ Add a Git Bash Profile for Windows Terminal
+ Scalar (Git add-on to manage large-scale repositories)

On the *Choosing the default editor used by Git* step of the installation program, select the following text editor:

+ Nano editor

On the *Adjusting the name of the initial branch in new repositories* step of the installation program, select the following option:

+ Let Git decide

On the *Adjusting your PATH environment* step of the installation program, select the following option:

+ Git from the command line and also from 3rd-party software

On the *Choosing the SSH executable* step of the installation program, select the following option:

+ Use bundled OpenSSH

On the *Choosing HTTPS transport backend* step of the installation program, select the following option:

+ Use the OpenSSL library

On the *Configuring the line ending conversions* step of the installation program, select the following option:

+ Checkout Windows-style, commit Unix-style line endings

On the *Configuring the terminal emulator to use with Git Bash* step of the installation program, select the following option:

+ Use MinTTY (the default terminal of MSYS2)

On the *Choose the default behavior of 'git pull'* step of the installation program, select the following option:

+ Rebase

On the *Choose a credential helper* step of the installation program, select the following option:

+ Git Credential Manager

On the *Configuring extra options* step of the installation program, check the following checkboxes:

+ Enable file system caching
+ Enable symbolic links

On the *Configuring experimental options* step of the installation program, keep all the checkboxes unchecked.

When the installation is complete, configure the **Git Bash** profile on the [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701).

#### 1.5.2. Bash prompt customization

##### 1.5.2.1. Bash prompt customization on the WSL File System

The customization of the bash prompt is very personal and the files used to accomplish my personal customization on the `WSL File System` are stored at the folder `%OneDriveCommercial%\dotfiles\bash-wsl`. To make use of the mentioned files on the bash prompt customization, replace the **{LABEL}** in the upcoming command as appropriate and then execute it from an [Ubuntu](https://ubuntu.com/) terminal.

    mkdir -p ~/.bash_"$USER" && cp -r {ONEDRIVE_COMMERCIAL_PATH}/dotfiles/bash-wsl/* ~/.bash_"$USER"

> **Label Definition**
>
> + **{ONEDRIVE_COMMERCIAL_PATH}** : Path to the folder `%OneDriveCommercial%`

Replace the **{LABEL}** in the upcoming snippet as appropriate and the add it to the file `~/.bashrc`.

    # Source the file ~/.bash_{USER}/bash_{USER}.sh to customize the bash shell
    #
    if [ -f ~/.bash_{USER}/bash_{USER}.sh ]; then
        . ~/.bash_{USER}/bash_{USER}.sh
    fi

> **Label Definition**
>
> + **{USER}** : Output of the command `echo "$USER"`

After applying the above mentioned changes, save and close the file `~/.bashrc`. To make the changes effective, execute, from the [Ubuntu](https://ubuntu.com/) terminal, the following command:

    source ~/.bashrc

##### 1.5.2.2. Bash prompt customization on the Windows Native File System

The files used to accomplish my personal customization on the `Windows Native File System` are stored at the folder `%OneDriveCommercial%\dotfiles\bash-win`. If a [symlink](https://www.howtogeek.com/16226/complete-guide-to-symbolic-links-symlinks-on-windows-or-linux/) to the folder `%OneDriveCommercial%\dotfiles` isn't yet created the Windows `%USERPROFILE%`, create executing the below command from the Windows Command Prompt.

    mklink /J %USERPROFILE%\.dotfiles "%OneDriveCommercial%\dotfiles"

To edit the file `~/.bashrc`, open it (or create it) with the [Nano text editor](https://www.nano-editor.org/), executing the below command on a **Git Bash** terminal:

    nano ~/.bashrc

Then, within the file `~/.bashrc`, paste the upcoming snippet and replace the **{LABEL}** as appropriate.

    # Source the file ~/.dotfiles/bash-win/bashrc_{USER}.sh to customize the bash shell
    if [ -f ~/.dotfiles/bash-win/bashrc_{USER}.sh ]; then
        source ~/.dotfiles/bash-win/bashrc_{USER}.sh
    fi

> **Label Definition**
>
> + **{USER}** : Output of the command `echo "$USER"`

After applying the above mentioned changes, save and close the file `~/.bashrc`. To make the changes effective, execute from a **Git Bash** terminal, the following command:

    source ~/.bashrc

#### 1.5.3. Git configuration

To set [Git's global configuration](https://www.learnenough.com/git-tutorial#sec-installation_and_setup), replace the **{LABELS}** in the below commands as appropriate and then execute it in an [Git Bash](https://git-scm.com/) terminal window.

    git config --global user.name "{USER_NAME}"
    git config --global user.email {USER_EMAIL}
    git config --global core.editor nano
    git config --global pull.rebase true
    git config --list

> **Label Definition**
>
> + **{USER_NAME}** : The name of the user
> + **{USER_EMAIL}** : The e-mail of the user

Instructions for a more detailed Git global configuration can be found in the [Git's Official Documentation](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup).

#### 1.5.4. SSH Keys

The [SSH Protocol](https://en.wikipedia.org/wiki/Secure_Shell) is very useful to connect and authenticate to remote servers and services. The creation and setup of the SSH keys described here follows the instructions at [GitHub](https://help.github.com/en/articles/connecting-to-github-with-ssh).

##### 1.5.4.1. Checking for existing SSH keys

To check if the system already has an SSH key set, type the following command:

    ls -al ~/.ssh

If the output of the above command contains a list of files (by default, the filenames of the public keys are *id_dsa.pub*, *id_ecdsa.pub*, *id_ed25519.pub* or *id_rsa.pub*), the system already has a SSH key and it can be used.

##### 1.5.4.2. Generating a new SSH key

To create a new SSH key, replace the **{LABEL}** in the below command as appropriate and then execute it in an [Git Bash](https://git-scm.com/) terminal window.

    ssh-keygen -t rsa -b 4096 -C "{EMAIL_ADDRESS}"

> **Label Definition**
>
> + **{EMAIL_ADDRESS}** : The e-mail address to be used as label for the SSH key

The above command creates a new SSH key, using the provided email as a label.

    > Generating public/private rsa key pair.

When  prompted to "Enter a file in which to save the key," press Enter to accept the default file location.

    > Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]

Type a secure passphrase when prompted. GitHub has further instructions on [working with SSH key passphrases](https://help.github.com/en/articles/working-with-ssh-key-passphrases).

    > Enter passphrase (empty for no passphrase): [Type a passphrase]
    > Enter same passphrase again: [Type passphrase again]

##### 1.5.4.3. Adding the SSH key to the ssh-agent

To add the new SSH key to the `ssh-agent`, start it in the background with the command below.

    eval "$(ssh-agent -s)"

The command below will add the private key to the `ssh-agent`.

    ssh-add ~/.ssh/id_rsa

##### 1.5.4.4. Adding a new SSH key to the remote servers

To be able to copy the public SSH key to the clipboard, display it in a bash terminal window with the following command:

    cat ~/.ssh/id_rsa.pub

Copy the output of the above command and then add the public SSH key to the remote servers in use ([GitHub](https://github.com/settings/keys), [Bitbucket](https://bitbucket.org/account/user/ssh-keys), etc.).

### 1.6. KeePassXC

[**KeePassXC**](https://keepassxc.org/) is a cross-platform community-driven port of the Windows application [Keepass Password Safe](https://keepass.info/) that I choose to use precisely because it's cross-platform and it allows me to use it on every operating system that I work with.

#### 1.6.1. Installation

To install [**KeePassXC**](https://keepassxc.org/), execute the upcoming commands on a PowerShell console.

    scoop bucket add extras
    scoop install extras/keepassxc

Check if the output of the above last command shows a suggestion to install `vcredist2022`. If it does, install it executing the following command on a PowerShell console:

    scoop install extras/vcredist2022

Following the execution of the above command, there will be several prompts for elevated permissions which must all be be accepted to complete the installation. A restart of the machine will be necessary to complete the installation but before restarting the machine, check if the output of the installation command states that the `vcredist2022` installer can be removed. If it does, after the restart of the machine, execute the following command on a PowerShell console:

    scoop uninstall extras/vcredist2022

Move the `KeepassXC` shortcut from the folder `C:\Users\rferrcan\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Scoop Apps`to the folder `%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Utility`.

#### 1.6.2. Configuration

Set [**KeePassXC**](https://keepassxc.org/) preferences (`Tools->Settings`) as desired but make sure to enable the `Browser Integrations`. Then, setup [KeePassXC-Browser](https://chrome.google.com/webstore/detail/keepassxc-browser/oboonakemofpalcgghocfoadofidjkkk) extension to integrate it with the machine's installation of [**KeePassXC**](https://keepassxc.org/).
