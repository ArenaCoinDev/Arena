
Debian
====================
This directory contains files used to package arenad/arena-qt
for Debian-based Linux systems. If you compile arenad/arena-qt yourself, there are some useful files here.

## arena: URI support ##


arena-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install arena-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your arena-qt binary to `/usr/bin`
and the `../../share/pixmaps/arena128.png` to `/usr/share/pixmaps`

arena-qt.protocol (KDE)

