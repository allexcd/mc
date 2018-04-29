# Midnigt Commander Custom Configs

## MC Installation
1. `brew update`
2. `brew install mc`

## User Menu Installation

Copy the `menu` file from the project into `~/.config/mc/`

### Custom actions added to User Menu

7. Copy Filename
- Copies the selected filename to clipboard

8. Update Filename
- Renames the selected file using the filename copied in the clipboard
- Preserves the selected file extension

### Using the custom actions

1. Select a file with mc then press `F2` to open the menu options
2. Press `7` to copy the filename
3. Select the file to be renamed within mc
4. Press `F2` to open the menu options
5. Press `8` to rename the file

## Open video files with VLC

1. Create a vlc alias in your `~/.bash_profile`: `alias vlc='/Applications/VLC.app/Contents/MacOS/VLC'`
2. Make a symlink to get access to env vars and aliases in mc subshell: `ln -s ~/.bash_profile ~/.local/share/mc/bashrc`
3. Make a symlink with the `mc.ext`: `ln -s /usr/local/Cellar/midnight-commander/4.x/etc/mc/mc.ext ~/.config/mc/mc.ext`
4. Edit `mc.ext` file: `nano ~/.config/mc/mc.ext` and add under `include/video` section:
`Open=(vlc %f >/dev/null 2>&1 &) # this is going to use the vlc alias set in the .bash_profile`
You'll have to scroll down until you find the video section
5. If the `vlc` alias does not work, until finding a fix, replace `vlc` with `/Applications/VLC.app/Contents/MacOS/VLC`
under `include/video` section

## Specify special keyboard maps:
1. `ln -s ~/.inputrc ~/.local/share/mc/inputrc`

## Other commands
CTRL + O to switch between mc ui and subshell
