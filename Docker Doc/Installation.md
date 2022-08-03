<h1 align="center">Docker Installation</h1> <br>

## requirements :
1. OS must have virtualization enabled. (check task manger)
2. 64 os and processor and 8 GB ram

## installation 
download docker from following link:

[Docker for Windows](https://docs.docker.com/desktop/install/windows-install/) 
conform check mark on WSL  
install docker exe 
restart pc 

## Now setup WSL 2 

### Step 1 - Enable the Windows Subsystem for Linux
open powershell and pest the code
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart 
```

### Step 2 - Enable Virtual Machine feature
``` 
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart 
```
### Step 3 - Download the Linux kernel update package
[wsl updater hare ](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

### Step 4 - Set WSL 2 as your default version
run following code on powershell
```
wsl --set-default-version 2
```
