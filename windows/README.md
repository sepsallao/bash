# WINDOWS

##  VS CODE
###### Setup VS Code on windwos for development
https://dev.to/kouts/setup-vs-code-on-windows-for-development-in-a-linux-vm-or-a-remote-server-4c6n

###### VS CODE REMOTE SSH CONNECTION NOT WORKING 
https://stackoverflow.com/questions/64034813/vs-code-remote-ssh-connection-not-working

###### bad owner or pemissions
This started popping up immediately after I created another user with Administrator privileges, and that account began inheriting access to my .ssh folder.

You do not need to change your permissions whatsoever.

Just go to .ssh, right-click Properties, Security Tab, Advanced. DISABLE INHERITANCE, then click on the Administrator user (the one that is not you) and Remove them. Apply. Done.

- Jason Hughes (Stack Over Flow)

##

## WSL
###### Reboot 
You cannot reboot a distro with a single command. You must shut down and boot up the distro with two commands.

View the list of distros and their current state:

wsl -l -v

Shutdown everything: Build 18917+

wsl --shutdown

Terminate a specific distro: Windows 1903+

wsl -t <DistroName>

Boot up the default distro (marked with *):

wsl

Boot up a specific distro:

`wsl -d <DistroName>`

`> wsl -l -o`

###### Install Docker without Docker Desktop from windows
https://dev.to/bowmanjd/install-docker-on-windows-wsl-without-docker-desktop-34m9

###### Advance configuration
https://docs.microsoft.com/en-us/windows/wsl/wsl-config#configure-global-options-with-wslconfig

##