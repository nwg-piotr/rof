# rof
rof is  a launcher script to avoid launching multiple instances of the same window. The name stands for [r]un [o]r set [f]ocus).

While playing with [my collection of Tint2 executors](https://github.com/nwg-piotr/tint2-executors) one of things I hated most 
was that commands assigned to mouse events would execute again and again after each click, even if previous instances were 
already running. The behavior I expected was: launch the command if not yet running, else just bring focus to the command 
window. Having no better idea on how to achieve this, I wrote this short script. It searches the process ID of the name given, then tries to find a window by the process ID. If found, it'll be given focus, instead of running the command again.

## Dependencies:

`xorg-xprop`, `wmctrl` (valid for Arch Linux; package names may vary in other distributions)

## Usage:

```
rof [-P process_name] command
```

Use `rof command` to simply run if the command and the process name are the same.

Provide the optional process name, for instance if the command is a script which runs another command:

```
rof -P zenity zenity-set-volume.sh
```

launches the script which opens a zenity box, with arguments: `zenity --scale --value ${lvl} --title "Volume" --text "Set master volume level"`

## Sample:

The script may be useful in a Tint2 executor left/right click commands:

```
#-------------------------------------
# Executor 4
execp = new
execp_command = ~/tint2-executors/volume-icon.sh
execp_interval = 3
execp_has_icon = 1
execp_cache_icon = 1
execp_continuous = 0
execp_markup = 1
execp_tooltip = Scroll ↓↑, middle click to mute
execp_lclick_command = rof -P zenity ~/tint2-executors/zenity-set-volume.sh
execp_rclick_command = rof pavucontrol
execp_mclick_command = amixer set Master toggle -q
execp_uwheel_command = amixer set Master 5%+ unmute -q && ~/tint2-executors/notify-vol.sh
execp_dwheel_command = amixer set Master 5%- -q && ~/tint2-executors/notify-vol.sh
execp_font_color = #000000 100
execp_padding = 0 0
execp_background_id = 0
execp_centered = 0
execp_icon_w = 26
execp_icon_h = 26
```
