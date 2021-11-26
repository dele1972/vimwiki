## check if package is in repo

```bash
apt-cache search <package-name>
```


## check if package is installed

(https://askubuntu.com/q/423355)

```bash
apt-cache policy <package-name>
```

```bash
sudo apt list --installed
```

## update apt repo

```bash
sudo apt-get update && sudo apt-get upgrade
sudo apt update && sudo apt -y upgrade && sudo apt -y dist-upgrade && sudo apt -y autoremove
sudo apt --fix-broken install
```

## INSTALL

```bash
sudo apt-get [Option(en)] install PAKET1 [PAKET2]  
```

```bash
sudo apt-get -y install <package-name>
```


## remove libs wothout any dependencies

```bash
sudo apt-get autoremove
```

## remove package

```bash
sudo apt remove package_name
```

https://www.tecmint.com/useful-basic-commands-of-apt-get-and-apt-cache-for-package-management/


## FEHLER BEI UPDATE (2020-09-17)

(https://forum.ubuntuusers.de/topic/gpg-fehler-oeffentlicher-schluessel-fehlt/)

```bash
  Die folgenden Signaturen konnten nicht überprüft werden, weil ihr öffentlicher Schlüssel nicht verfügbar ist: NO_PUBKEY 59BC194978779ADF
Paketlisten werden gelesen... Fertig
W: Ziel Packages (main/binary-amd64/Packages) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel Packages (main/binary-all/Packages) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel Translations (main/i18n/Translation-de_DE) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel Translations (main/i18n/Translation-de) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel Translations (main/i18n/Translation-en) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel DEP-11 (main/dep11/Components-amd64.yml) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel DEP-11 (main/dep11/Components-all.yml) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel DEP-11-icons-small (main/dep11/icons-48x48.tar) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel DEP-11-icons (main/dep11/icons-64x64.tar) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel CNF (main/cnf/Commands-amd64) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel CNF (main/cnf/Commands-all) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
E: Das Depot »http://ppa.launchpad.net/leolik/leolik/ubuntu bionic Release« enthält keine Release-Datei.
N: Eine Aktualisierung von solch einem Depot kann nicht auf eine sichere Art durchgeführt werden, daher ist es standardmäßig deaktiviert.
N: Weitere Details zur Erzeugung von Paketdepots sowie zu deren Benutzerkonfiguration finden Sie in der Handbuchseite apt-secure(8).
W: Während der Überprüfung der Signatur trat ein Fehler auf. Das Depot wurde nicht aktualisiert und die vorherigen Indexdateien werden verwendet. GPG-Fehler: https://tel.red/repos/ubuntu bionic InRelease: Die folgenden Signaturen konnten nicht überprüft werden, weil ihr öffentlicher Schlüssel nicht verfügbar ist: NO_PUBKEY 59BC194978779ADF
W: Ziel Packages (main/binary-amd64/Packages) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel Packages (main/binary-all/Packages) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel Translations (main/i18n/Translation-de_DE) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel Translations (main/i18n/Translation-de) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel Translations (main/i18n/Translation-en) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel DEP-11 (main/dep11/Components-amd64.yml) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel DEP-11 (main/dep11/Components-all.yml) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel DEP-11-icons-small (main/dep11/icons-48x48.tar) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel DEP-11-icons (main/dep11/icons-64x64.tar) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel CNF (main/cnf/Commands-amd64) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
W: Ziel CNF (main/cnf/Commands-all) ist mehrfach konfiguriert in /etc/apt/sources.list.d/google-chrome.list:3 und /etc/apt/sources.list.d/google-chrome.list:4
```

- https://wiki.ubuntuusers.de/apt/apt-get
- https://linuxize.com/post/how-to-uninstall-software-packages-on-ubuntu/
