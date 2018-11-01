# rof
rof is  a launcher script to avoid launching multiple instance of the same window. The name stands for [r]un [o]r set [f]ocus).

While playing with my [collection of Tint2 executors](https://github.com/nwg-piotr/tint2-executors) one of things I hated most 
was that commands assigned to mouse events would execute again and again after each click, even if previous instances were 
already running. The behavior I expected was: launch the command if not yet running, else just bring focus to the command 
window. Having no better idea on how to achieve this, I wrote this short script.
