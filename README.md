# CSSOpen - Session 1 - Lab 1 - WSL 2 Installation for Windows 10

- What is WSL? Please refer to https://docs.microsoft.com/en-us/windows/wsl/about <br> 
- WSL 2 is only available in **Windows 10, Version 2004, Build 19041 or higher**. You may need to update your Windows version.
- This is Windows Subsystem for Linux Installation Guide for Windows 10, please feel free contact with me, if have any problems on this guide. 
- I recorded these installation steps for myself. If you have any unclear parts, please feel free to let me know. 

## Enable the Windows Subsystem for Linux optionl feature on Windows 10

1. Open PowerShell as Administrator. 
![GITHUB](https://github.com/neolin-ms/CSSOpenWSL2/WSL2Image/01.PNG "01")<br>

2. Run command.
```sh
PS C:\windows\system32> dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart 
``` 




