Virtualbox on Ubuntu

Installation via 'Ubuntu Software'



https://www.giga.de/downloads/windows-10/tipps/windows-10-in-virtualbox-installieren-so-geht-s/


https://www.giga.de/downloads/windows-10/tipps/virtuelle-maschine-mit-windows-10-download-von-microsoft-so-geht-s/
https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/
https://itsfoss.com/install-windows-10-virtualbox-linux/

https://stackoverflow.com/questions/1825599/testing-web-application-on-mac-safari-when-i-dont-own-a-mac



Fehler:
Kernel driver not installed (rc=-1908)

The VirtualBox Linux kernel driver is either not loaded or not set up correctly. Please reinstall virtualbox-dkms package and load the kernel module by executing

'modprobe vboxdrv'

as root.

If your system has EFI Secure Boot enabled you may also need to sign the kernel modules (vboxdrv, vboxnetflt, vboxnetadp, vboxpci) before you can load them. Please see your Linux system's documentation for more information.

where: suplibOsInit what: 3 VERR_VM_DRIVER_NOT_INSTALLED (-1908) - The support driver is not installed. On linux, open returned ENOENT. 

==> https://askubuntu.com/a/920713
	https://askubuntu.com/questions/760671/could-not-load-vboxdrv-after-upgrade-to-ubuntu-16-04-and-i-want-to-keep-secur
