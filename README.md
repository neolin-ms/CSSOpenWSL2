# CSSOpen - Session 1 - Lab 1&2&3 

- What is WSL? Please refer to [here](https://docs.microsoft.com/en-us/windows/wsl/about).<br> 
- WSL 2 is only available in **Windows 10, Version 2004, Build 19041 or higher**. You may need to update your Windows version.
- This is installation guide on Windows 10 for `Windows Subsystem for Linux (WSL)`, I recorded these installation steps for myself. Please feel free contact with me or file a [issue](https://github.com/neolin-ms/CSSOpenWSL2/issues) on this repo, if have any problems on this guide. 

## Lab 1: Enable the WSL optionl feature on Windows 10

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

## Lab 1: Install Linux distribution on WSL 2

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

## Lab 2: Install PowerShell/Azure PowerShell on Debian Linux

1. PowerShell - Installation via Package Repository - Debian 10. For more details, please check [here](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7#debian-10).
> Command:<br>
> - Download the Microsoft repository GPG keys
> ```sh
> neolin@tw-hslin-205:~$ sudo wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb
> ```
> - Register the Microsoft repository GPG keys
> ```sh
> neolin@tw-hslin-205:~$ sudo dpkg -i packages-microsoft-prod.deb
> ```
> - Update the list of products
> ```sh
> neolin@tw-hslin-205:~$ sudo apt-get update
> ```
> - Install PowerShell
> ```sh
> neolin@tw-hslin-205:~$ sudo apt-get install -y powershell
> ```
> - Start PowerShell
> ```sh
> neolin@tw-hslin-205:~$ pwsh
> ```
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/3_1.png "3_1")<br>

2. Install Azure PowerShell. For more details, please check [here](https://docs.microsoft.com/en-us/powershell/azure/install-az-ps?view=azps-4.6.0#code-try-0). 
> Command:<br>
> - Requirements: Azure PowerShell works with PowerShell 6.2.4 and later on all platforms. To check your PowerShell version, run the command.
> ```ps
> PS /home/neolin> $PSVersionTable.PSVersion
> ``` 
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/3_2.png "3_2")<br>
> - Install the Azure PowerShell module. Copy below codes and put on PS prompt, then **Enter**. 
> ```ps
> if ($PSVersionTable.PSEdition -eq 'Desktop' -and (Get-Module -Name AzureRM -ListAvailable)) {
>    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
>      'Az modules installed at the same time is not supported.')
>} else {
>    Install-Module -Name Az -AllowClobber -Scope CurrentUser
>}
> ```
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/3_3.png "3_3")<br>
> Output:<br>
> ```ps
> Untrusted repository
>
> You are installing the modules from an untrusted repository. If you trust this repository, change
> its InstallationPolicy value by running the `Set-PSRepository` cmdlet.
> 
> Are you sure you want to install the modules from 'PSGallery'?
> [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
> ```
> Answer **Yes** or **Yes to All** to continue with the installation.

## Lab 3: Sign in with your Azure credentials.
> - Try to sin in your Azure. Connect to Azure with a browser sign in token.<br> 
> Command:
> ```ps
> Connct-AzAccount
> ``` 
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/4_1.png "4_1")<br>
> - Open your borwse, then go to https://microsoft.com/devicelogin. On the webpage enter the code, e.g. HX*****. Then click **Next**.<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/4_2.png "4_2")<br>
> - Please enter your alias name for Sign in, e.g. xxxx@microsoft.com. Then click **Next**.<br> 
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/4_3.png "4_3")<br>
> - You have signed in to the Azure PowerShell application on your device. And also see your Azure subscription on the Azure PowerShell prompt.<br> 
>> * Webpage<br>
>>![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/4_4.png "4_4")<br>
>> * Azure PowerShell prompt<br>
>> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/4_5.png "4_5")<br>

## Lab 3: Use Azure PowerShell to Deploy a Linux VM on Azure 

1. On the Linux command prompt, run command to create an SSH key pair. And you will see the two files, e.g. id_rsa, and id_rsa.pub.<br>
> Command:<br>
> ```sh
> neolin@tw-hslin-205:~$ ssh-keygen -m PEM -t rsa -b 4096 
> neolin@tw-hslin-205:~$ ls .ssh
> ```
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_1.png "5_1")<br>
2. Create a PowerShell script to deploy a Linux VM on Azure. For the script example, please refer to [here](://github.com/neolin-ms/AzurePowerShell/blob/master/2Create_VM_Linux.ps1). Copy script example and save it to your Linux. 
> Command:<br>
> ```ps
> neolin@tw-hslin-205:~$ vi script_example.ps1 
> ```
3. Click key **i** to enter edit mode, then copy the script example cods and paste. Click key **Esc** to view mode, then click key **: + wq! + Enter** for save and exit the file.<br> 
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_2.png "5_2")<br>

4. Now enter Azure PowerShell, and run the script_example.ps1 to deploy a Linux VM on Azure.<br>
> Command:<br>
> ```ps
> neolin@tw-hslin-205:~$ pwsh
> PS /home/neolin> ./script_example.ps1
> ```
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_3.png "5_3")<br>
5. After complted to deploy the Linux VM, you can see a public ip. Then you able to access to Linux VM via SSH<br> 
> Command:<br>
> ```sh
> PS /home/neolin> exit
> neolin@tw-hslin-207a:~$ ssh -i ~/.ssh/id_rsa azureuser@13.94.61.247
> ``` 
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_4.png "5_4")<br>
6. After accessed to Linux VM, run command to check the Linux distribution version and Linux Kernel.<br>
> - Check Linux distribution version<br>
> Command:<br>
> ```sh
> [azureuser@myVM ~]$ cat /etc/*release
> ```
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_5.png "5_5")<br>
> - Check the Linux Kernel version<br> 
> Command:<br>
> ```sh
> [azureuser@myVM ~]$ uname -ra
> ```
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_6.png "5_6")<br>
7. Return to Azure PowerShell, and then clean up the resource of test on Azure. 
> - Confirm the rsource name<br>  
> Command:<br>
> ```ps
> PS /home/neolin> Get-AzResourceGroup | Format-Table
> ``` 
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_7.png "5_7")<br>
> - Delete the resource<br>
> Command:<br>
> ```ps
> PS /home/neolin> $job = Remove-AzResourceGroup -Name "myResourceGroup" -Force -AsJob //Delete
> PS /home/neolin> $job //Show clean state 
> PS /home/neolin> Wait-Job -Id $job.Id //Wait unit the deletion is complete
> ```
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_8.png "5_8")<br>
8. Waiting for a while, you will see deletion state is **Completed**.<br> 
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_9.png "5_9")<br>
9. Confirm the resource again. Then resource name - **myResourceGroup** already deleted. You complete all Labs. 
> ```ps
> PS /home/neolin> Get-AzResourceGroup | Format-Table 
> ```
> Output:<br>
> ![GITGUB](https://github.com/neolin-ms/CSSOpenWSL2/blob/master/WSL2Image/5_10.png "5_10")<br>

## References
- Presentation file, P.10 
  - [stallman.org](http://www.stallman.org), Richard Stallman's Personal Site.
  - [GNU (GNU's Not Unix)](http://www.gnu.org), The GNU Operating System and the Free Software Movement. 
  - [Wikipedia, Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds), Linux Torvalds.
  - [GPL](http://www.gnu.org/licenses/licenses.html#GPL), The GNU General Public License.
  - [Active Kernel release](https://www.kernel.org/releases.html), The Linux Kernel Archives.
  - [DistroWatch.com](https://distrowatch.com/), Put the fun back into computing. Use Linux, BSD. 
  - [The History of Tux the Linux Penguin](https://www.sjbaker.org/wiki/index.php?title=The_History_of_Tux_the_Linux_Penguin), The Linux logo, why penguins? Linus said: I was bitten by a Killer Penguin in Australia.
- Presentation file, P.13
  - The Linux Foundation, check the training [edX - Introduction to Linx](https://www.edx.org/course/introduction-to-linux)(It's a free online training) get more details about System Structure. 
- Presentation file, P.14
  - The Linux Foundation, [Filesystem Hierarchy Standard (FHS) Version 3.0](https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html). 
