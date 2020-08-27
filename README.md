# CSSOpen - Session 1 - Lab 1 - WSL 2 Installation for Windows 10

- What is WSL? Please refer to [here](https://docs.microsoft.com/en-us/windows/wsl/about).<br> 
- WSL 2 is only available in **Windows 10, Version 2004, Build 19041 or higher**. You may need to update your Windows version.
- This is installation guide on Windows 10 for `Windows Subsystem for Linux (WSL)`, I recorded these installation steps for myself. Please feel free contact with me, if have any problems on this guide. 

## Enable the Windows Subsystem for Linux optionl feature on Windows 10

1. Open PowerShell as Administrator.<br> 
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/1_1.png "1_1")<br>

2. Run command.<br>
> Command:
> ```ps
> PS C:\windows\system32> dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart 
> ``` 
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/1_2.png "1_2")<br>

3. Restart your machine to complete the enable WSL.<br>

4. After restart the Windows 10, please open PowerShell as Administrator. Then run command to set WSL 2 as the default version when installing a new Linux distribution.<br> 
> Command:
> ```ps
> PS C:\windows\system32> wsl --set-default-version 2 
> ``` 
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/1_3.png "1_3")<br>

## Install Linux distribution on WSL 2

1. Open the Microsoft Store and select your favorite Linux distribution via **Windows logo key** + **s**. Then enter the store, and click **Open**.<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/2_1.png "2_1")<br>

2. Go to **Microsoft** > **Linux for Windows**. Then click **Ubuntu**.<br> 
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/2_2.png "2_2")<br>

3. From the distribution's page, click **Get**.<br> 
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/2_3.png "2_3")<br>

4. After finished to install Ubuntu Linux, click **Start**.<br> 
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/2_4.png "2_4")<br>

5. The first time you launch a newly installed Linux distribution, a console windows will open and you'll be asked to wait for a minute or two for files to de-compress and be store on your Windows 10. You will need to create a **username** and **password** for your new Linux distribution.<br> 
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/2_5.png "2_5")<br>

6. Now you already installed the Linux on your Windows 10 and can try to run Linux command.<br> 
> You can see the Linux command prompt 
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/2_6.png "2_6")<br>
> Command:
> ```sh
> neolin@tw-hslin-205:~$ lsb_release -a
> ```
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/2_7.png "2_7")<br>

7. Open PowerShell as Administrator, and run command to check the WSL version.<br>
> Command:
> ```ps
> PS C:\windows\system32> wsl -l -v 
> ```
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/2_8.png "2_8")<br>

## Install PowerShell/Azure PowerShell on Linux

1. PowerShell - Installation via Package Repository - Debian 10. For more details, please check [here](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7#debian-10).
> Command:
> Download the Microsoft repository GPG keys
> ```sh
> neolin@tw-hslin-205:~$ sudo wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb
> ```
> Register the Microsoft repository GPG keys
> ```sh
> neolin@tw-hslin-205:~$ sudo dpkg -i packages-microsoft-prod.deb
> ```
> Update the list of products
> ```sh
> neolin@tw-hslin-205:~$ sudo apt-get update
> ```
> Install PowerShell
> ```sh
> neolin@tw-hslin-205:~$ sudo apt-get install -y powershell
> ```

# Start PowerShell
pwsh
A
A
A
pwsh
