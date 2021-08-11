Download from Mozilla Firefox Developer Edition webpage
Extract it with file-roller
move the folder to its final location "/opt/"   (/opt/firefox_dev/)
create the "~/.local/share/applications/firefox_dev.desktop" to get a launcher with an icon distinct from normal Firefox

---8<-----------------------------[firefox_dev.desktop]--
[Desktop Entry]
Name=Firefox Developer 
GenericName=Firefox Developer Edition
Exec=/opt/firefox_dev/firefox %u
Terminal=false
Icon=/opt/firefox_dev/browser/chrome/icons/default/default128.png
Type=Application
Categories=Application;Network;X-Developer;
Comment=Firefox Developer Edition Web Browser.
--------------------------------------------------->8---

To mark the launcher as trusted, make it executable: chmod +x ~/.local/share/applications/firefox_dev.desktop

