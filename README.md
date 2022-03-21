# random-wallpapers

## Introduction:
`random-walppapers` is a shell script to set a random X wallpaper and change it randomly after a given interval. The script uses [feh](https://feh.finalrewind.org/) to display the images and will always zoom it to cover the entire screen, preserving aspect ratio.

At the moment the script is very simple and the variables are hardcoded. Future versions should be more configurable, through command line options.

## Installation:
- Copy the `random-wallpapers` file into a directory in the PATH
- Edit the file to set the variables `wp_dir` and `wp_time` with the directory where the image files are and the interval in seconds between each wallpalper change, respectively.
- Turn it executable (ex.: `chmod +x random-wallpapers`)

## Usage:
Ideally it should be started with X, for example, adding `random-wallpapers &` to your `.xinitrc` or `.xsession`

## Caveats:
Some window managers and composite managers set the color or picture of the X root window when started, covering or substituting the wallpapper set by random-wallpapers. To surpass it, delay the starting of random-wallpapers:
```
(sleep 0.5; random-wallpapers) &
```

if the problem persists, the interval in the `sleep` command (in seconds) should be increased - usually 0.5-1s is enough.
