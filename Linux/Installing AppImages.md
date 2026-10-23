AppImages are self-contained portable apps — no package manager needed. To make them show up in launchers (Rofi `drun`, dmenu), they need a `.desktop` entry.

## Steps

1. **Create a storage dir**
   `mkdir -p ~/.local/share/AppImage`

2. **Download the AppImage**
   `wget -O ~/.local/share/AppImage/Obsidian.AppImage "<release-url>"`

3. **Make it executable**
   `chmod +x ~/.local/share/AppImage/Obsidian.AppImage`
   Run it directly to test: `~/.local/share/AppImage/Obsidian.AppImage`

4. **Create a desktop entry**
   `nano ~/.local/share/applications/Obsidian.desktop`

   ```ini
   [Desktop Entry]
   Name=Obsidian
   Exec=/home/$USER/.local/share/AppImage/Obsidian.AppImage %u
   Icon=/home/$USER/.local/share/icons/Obsidian.png
   Type=Application
   Categories=Office;Utility;
   StartupNotify=true
   Terminal=false
   Keywords=Notes;Markdown;Editor;Knowledge;
   ```

   Icon: `wget -O ~/.local/share/icons/Obsidian.png "<icon-url>"`

5. **Register it**
   `update-desktop-database ~/.local/share/applications/`

6. **Launch** — Rofi (`Mod1+D`) or `dmenu_run`

## Repeat for other apps
Same five steps; just swap filenames, URLs, and the `Name`/`Exec`/`Icon` fields.
