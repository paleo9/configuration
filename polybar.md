# Adding polybar to bspwm in fedora 35

## Steps

1. install unifonts from fedora repo
1. install siji font from https://github.com/stark/siji
1. create ~/.config/polybar/config
1. create ~/.config/polybar/launch.sh
1. make launch.sh executable
1. add a line to ~/.bspwmrc to launch polybar

## Create polybar config file

copy the default file from /usr/share/doc/polybar/config
The bar created is called 'example', given by [bar/example]

Under [module/bspwm], add 'pin-workspaces = false'
( see https://github.com/polybar/polybar/wiki/Module:-bspwm )

comment out the section [module/mpd]

comment out [modules/center] i3

remove 'i3' from modules-center


in modules-right: 
  * remove wlan, battery, backlight powermenu from modules-right
  * move filesystem so that it is with memory, cpu etc
  * change eth0 interface from virbr0 to enp3s0

## Create launch.sh

see https://github.com/polybar/polybar/wiki
rename bar1 to 'example'

## Make launch.sh executable

chmod +x $HOME/.config/polybar/launch.sh

## Add a line to ~/.bspwmrc

$HOME/.config/polybar/launch.sh

