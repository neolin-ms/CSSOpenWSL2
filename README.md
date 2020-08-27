# CSSOpen - Session 1 - Lab 1 - WSL 2 Installation for Windows 10

- What is WSL? Please refer to https://docs.microsoft.com/en-us/windows/wsl/about <br> 
- WSL 2 is only available in **Windows 10, Version 2004, Build 19041 or higher**. You may need to update your Windows version.
- This is Windows Subsystem for Linux Installation Guide for Windows 10, please feel free contact with me, if have any problems on this guide. 
- I recorded these installation steps for myself. If you have any unclear parts, please feel free to let me know. 

## Enable the Windows Subsystem for Linux optionl feature on Windows 10

1. Open PowerShell as Administrator.<br> 
![GITHUB](https://github.com/neolin-ms/CSSOpenWSL2/WSL2Image/01.PNG "01")<br>

2. Run command.<br>
```sh
PS C:\windows\system32> dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart 
``` 
![GITHUB](https://github.com/neolin-ms/CSSOpenWSL2/WSL2Image/02.PNG "02")<br>

3. Restart your machine to complete the enable WSL.

4. After restart the Windows 10, please open PowerShell as Administrator. Then run command to set WSL 2 as the default version when installing a new Linux distribution. 
```sh
PS C:\windows\system32> wsl --set-default-version 2 
![GITHUB](https://github.com/neolin-ms/CSSOpenWSL2/WSL2Image/03.PNG "03")<br>
``` 
## Install Linux distribution on WSL 2

1. Open the Microsoft Store and select your favorite Linux distribution via **Windows logo key** + **s**. Then enter the store, and click **Open**.
