Running Windows 10 18.03+ or Newer?
===================================

Create and modify the new WSL configuration file:
-------------------------------------------------
sudo nano /etc/wsl.conf
---8<-----
[automount]

# We need to set root = / because this will make your drives mounted at /c or /e instead of /mnt/c or /mnt/e
root = /

# 'metadata' is not necessary but it will fix folder and file permissions on WSL mounts
# so everything isn’t 777 all the time within the WSL mounts. I highly recommend you do this!
options = "metadata"
----->8---


Install ZSH (Kali)
==================
sudo apt install zsh

oh my zsh basic installation (https://github.com/robbyrussell/oh-my-zsh)
------------------------------------------------------------------------
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

Install Powerlevel9k omz theme
------------------------------
Quelle: https://github.com/bhilburn/powerlevel9k/wiki/Install-Instructions#option-2-install-for-oh-my-zsh

git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k

---8<-----|~/.zshrc|---
ZSH_THEME="powerlevel9k/powerlevel9k"
----->8----------------



install tmux
============
sudo apt-get install tmux

---8<-----|~/.zshrc|---
export TERM="xterm-256color"
----->8----------------



Fehler beim erneuten Starten Bash nach einem Windows-Neustart
=============================================================
WslRegisterDistribution failed with error: 0x800703fa
-----------------------------------------------------
services.msc --> restart the LxssManager service as Administrator
or
1. run CMD as administrator
2. stop service by : sc stop LxssManager
3. restart it by: sc start LxssManager
or
1. run Regedit.exe as Admin
2. open this Path to registry key: Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LxssManager\Start
3. Set value to 2 (Automatic)
or
1. run CMD as administrator
2. configure service by: sc config LxssManager start=auto


workaround fix
--------------
Encountered the same issue, newest update but the bug prevented me from running some WSL scripts on login.
In case you don't want to manually restart the LxssManager once you log in, you can do the following:

In C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup you create a new .bat file (e.g. wsl_fix.bat) and write the command C:\WINDOWS\system32\svchost.exe -k netsvcs -p into it, which basically triggers the start of the LxssManager upon login.



CMD Befehle für WSL
===================
# list installed distros
wslconfig /list

# unregister Debian
wslconfig /u Debian
