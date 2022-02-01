# Install AppImage Apps

Prinzipiell werden diese Apps eher im Verzeichnis ~/Applications abgelegt

Bei Cura wurde beim ersten Aufruf dafür gesorgt, dass das Appimage in 
das Verzeichnis verschoben wird. Ggfs. muss man das manuell machen:


## 1) Download `YOURAPP.appimage`


## 2) Make it executable

```bash
chmod u+x YOURAPP.appimage
```

## 3) copy to usr/bin

- place global
- in current path, so it is everywhere executable

```shell
sudo mkdir /usr/bin/YOURAPP
sudo mv YOURAPP.appimage /usr/bin/nvim
```

