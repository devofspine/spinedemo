**NOTE** This repository contains sources of a *Flatpak package* for spinedemo. Spinedemo is a demo version of spine which is a Wine-like PS4 emulator for Linux that is being developed in private.

*See releases for binary downloads.*

```
spine - PS4 emulator for Linux
spinedemo version 20190609

================================================================================

1. Requirements
2. Installation
3. Running
4. Controls
5. Changes

================================================================================

1. Requirements

Linux installation with working OpenGL acceleration (3.3+). Preferably native
for better performance but at least one VM is known to work.

Supported:
- native installation
- VMware Fusion

Unsupported:
- VirtualBox

2. Installation

Default version is packaged using Flatpak (https://flatpak.org).

> flatpak --user install flatpak/spinedemo.flatpak

Alternative version was built on Fedora 29 and statically linked. It requires
only OpenGL and SDL2. It is provided in the static directory.

This was done because version built with flatpak runtime doesn't seem to work
with Nvidia drivers.

Supported games (md5 of executable, other dumps may also work):
- Mega Man Legacy Collection
	- 6911087c37fde29034c1d9ef2950684a eboot.bin (ELF)
	- 38c82774d44373cf24f84401eec97623 eboot.bin (SELF)
- We Are Doomed
	- 01fc7a91797a2debda8d0f14b4b0fa55 eboot.bin (ELF)
	- 6cf309f131434bcff7d8737664b45c8e eboot.bin (SELF)

Releases are currently tested on:
- desktop computer with Nvidia GTX970, Fedora 29
	binary version works, flatpak doesn't
- laptop running Fedora 29 under VMware Fusion
	both versions work

3. Running

Dump the game on your PS4 and copy the resulting files to your PC.

To run flatpak version:

flatpak run --filesystem={dump directory}:ro org.devofspine.SpineDemo {path to eboot.bin}

To run binary version:

> spinedemo {path to eboot.bin}

4. Controls

ESC - exit

arrow up - dpad up
arrow down - dpad down
arrow left - dpad left
arrow right - dpad right

w - triangle
s - cross
a - square
d - circle

i - leftstick up
k - leftstick down
j - leftstick left
l - leftstick right

keypad 5 or t - rightstick up
keypad 2 or g - rightstick down
keypad 1 or f - rightstick left
keypad 3 or h - rightstick right

1 - L1
2 - R1
3 - L2
4 - R2
5 - L3
6 - R3

9 - touchpad press
0 - options

5. Changes

20190609
	One more down, 9998 to go. Additional rightstick keys for laptop keyboards.
20190607
	Statically linked binary with no dependencies expcept GL and SDL2
20190605
	Initial release
```
