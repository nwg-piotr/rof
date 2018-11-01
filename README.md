# rof
rof is  a launcher script to avoid launching multiple instance of the same window. The name stands for [r]un [o]r set [f]ocus).

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

Provide the optional process name e.g. if the command is a script which runs another command:

```
`rof -P zenity zenity-set-volume.sh`
```

launches the script which opens a zenity box, with arguments: `zenity --scale --value ${lvl} --title "Volume" --text "Set master volume level"`
