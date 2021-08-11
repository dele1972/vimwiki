# ubuntu - webdav als Laufwerk einbinden

## Notwendige Software/Treiber installieren

### ca-certificates

Zuerst nachsehen ob bereits installiert:

```bash
apt-cache policy ca-certificates
```

Wenn nicht installieren:

```bash
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install ca-certificates
```

### davfs2 (universe)

Zuerst nachsehen ob bereits installiert:

```bash
apt-cache policy davfs2
```

Wenn nicht installieren:

```bash
sudo apt-get install davfs2
```

## webdav einmalig als Laufwerk einbinden

### als root (Benutzer dann nur read only)

```bash
sudo mount -t davfs https://dele72.od.alfahosting.de/dav/dennis /home/lederich/alfadrive
```

### mit Benutzerrechten

#### fstab editieren

Damit erlaubt root das einbinden von Laufwerken

```bash
sudo -s
nvim /etc/fstab
```

Dort muss folgende Zeile hinzugefügt werden:

```text
https://dele72.od.alfahosting.de/dav/dennis /home/lederich/alfadrive davfs noauto,user,rw 0 0
```

Anschließend kann man aus dem sudo Modus wieder raus

```bash
exit
```

#### Jedem User das Einbinden von WebDAV erlauben (SUID-Bit für den Befehl mount.davfs setzen)

```bash
sudo dpkg-reconfigure davfs2
```

#### Den Benutzer zur Gruppe davfs2 hinzufügen

```bash
sudo usermod -aG davfs2 lederich
```

## Wenn man das Laufwerk öfter einbinden will

### Credentials hinterlegen

```bash
sudo -s
nvim /etc/davfs2/secrets
```

Dort die Zeile anhängen:

```text
/home/lederich/alfadrive/dennis BENUTZERNAME  PASSWORT
```

### Mount jetzt möglich per

```bash
mount /home/lederich/alfadrive
```

### 'automatisiert' beim Login einbinden

#### 1. Script erstellen

```bash
nvim /home/lederich/.alfa.sh
```

```text
#!/bin/bash
echo -e "BENUTZER\nPASSWORT\nj" | mount /home/lederich/alfadrive
```

**FRAGE**: reicht hier evtl. die Verkürzte Version `mount /home/lederich/alfadrive`?

#### 2. Script in Startprogamme einfügen

- `WIN + startprogramme`
  - oder im Terminal: `gnome-session-properties`
- dort einen neuen Eintrag einfügen und als Befehl den Scriptpfad hinterlegen

## umount

```bash
fusermount -u /home/lederich/alfadrive
```

## Links

- [ubuntuusers - WebDAV](https://wiki.ubuntuusers.de/WebDAV/)
- 
