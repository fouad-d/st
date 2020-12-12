 ST - the simple (suckless) terminal
The suckless terminal (st) with some additional features that make it literally the best terminal emulator ever.

Unique features (using dmenu)
follow urls by pressing alt-l
copy urls in the same way with alt-y
copy the output of commands with alt-o
Bindings for
scrollback with alt-↑/↓ or alt-pageup/down or shift while scrolling the mouse
OR vim-bindings: scroll up/down in history with alt-k and alt-j. Faster with alt-u/alt-d.
zoom/change font size: same bindings as above, but holding down shift as well. alt-home returns to default
copy text with alt-c, paste is alt-v or shift-insert
Pretty stuff
Compatibility with Xresources and pywal for dynamic colors.
Default gruvbox colors otherwise.
Transparency/alpha, which is also adjustable from your Xresources.
Other st patches
Vertcenter
Scrollback
font2
updated to latest version 0.8.2

Installing st
Download the source code from this repository or use a git clone:

  git clone https://gitlab.com/dwt1/st-distrotube.git
  cd st-distrotube
  sudo make clean install

Users of Arch-based distros can also install it from the AUR as st-luke-git.


On OpenBSD, be sure to edit config.mk first and remove -lrt from the $LIBS before compiling.

Be sure to have a composite manager (xcompmgr, picom, etc.) running if you want transparency.

How to configure dynamically with Xresources
For many key variables, this build of st will look for X settings set in either ~/.Xdefaults or ~/.Xresources. You must run xrdb on one of these files to load the settings.
The alpha value (for transparency) goes from 0 (transparent) to 1 (opaque).

Colors
To be clear about the color settings:

This build will use gruvbox colors by default and as a fallback.
If there are Xresources colors defined, those will take priority.
But if wal has run in your session, its colors will take priority.
Note that when you run wal, it will negate the transparency of existing windows, but new windows will continue with the previously defined transparency.

Notes on Emojis and Special Characters
If st crashes when viewing emojis, install libxft-bgra-git from the AUR.

Note that some special characters may appear truncated if too wide. You might want to manually set your prefered emoji/special character font to a lower size in the config.h file to avoid this. By default, JoyPixels is used at a smaller size than the usual text.



