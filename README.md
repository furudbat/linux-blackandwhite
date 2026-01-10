# Black & White on Linux

Install Black & White (2001) on Linux (wine)

## Requirements

### System

You need [bottles](https://usebottles.com/), simples way to install bottles is through [flatpak](https://flathub.org/en/apps/com.usebottles.bottles).

### Game

So this game is **abandonware**, you probably can find it on the Internet or just mount the CD/backup you own.

- Black & White (2001)
- Black & White: Creature Idle (2002)


#### Patches

- [Villager Banter](https://www.bwgame.net/downloads/villager-banter.139/)
- [Football Addon](https://www.bwgame.net/downloads/football-addon.138/)
- [Patch v1.1](https://forum.bwgame.net/downloads/v1-1-patch.129/)
- [Patch v1.2](https://www.bwgame.net/downloads/v1-2-patch.130/)
- [Patch v1.42 (Fanpatch)](https://www.bwgame.net/downloads/black-white-unofficial-patch-v1-42.1418/)


## Installation (through bottles and wine)

### prepare

1. you need to download the patches and store them, for example in `patches` folder.
2. mount CDs/iso
    - Black & White -> `/mnt/cdrom`
    - Creature Isle -> `/mnt/cdrom2`

### Setup bottle

1. Start bottles and create a new bottle by clicking on "+"

![create bottle](assets/screenshot1.png)

- Name: `Black & White`
- Gaming
- Runner: `wine-ge-proton8-26`

_You can install more Runner in the bottles app, go to (open main menu) "Preferences" -> "Runners" -> "Wine GE" and download `wine-ge-proton8-26`_

2. Setup bottle by clicking in the "Settings"

- disable `VKD3D`
- **set "Windows Version" to `Windows XP`**

![settings](assets/screenshot2.png)

3. go to "Manage Drives" and add your `cdrom` drives

![manage drives](assets/screenshot3.png)

_You can add folder containing patches_  
_after setup you can remove the cd drives_

### Install Game

Click on "Black & White" bottle, scroll down and go to "Tools" -> "Legacy Wine Tools", click on "Explorer".

Now install game from mounted CD, in "Explorer", double-click on `Setup.exe`.
_NOTE: you need a Serial Key, probably somewhere **abandond** on the Internet_
Just need everything default, you don't need to read the ReadMe nor start the game, skip online registration.

![install setup](assets/screenshot4.png)

#### Copy audio files

Copy "Audio" directory from CD into installed game directory `C:\Program Files (x86)\Lionhead Studios Ltd\Black & White`

### Install patches

(Still) In the Explorer, go to your mounted patches (`Z:\...\Downloads\...\patches`) directory and install every patch in the following order:

1. Black_White_Patch_v1.100.exe
2. BW_Football_Addon.exe
3. BW_Villager_Banter.exe
4. black_white_patch_v1_20.exe
5. BWFanPatchInstaller.exe

### Setup Game

In the Explorer, go to `C:\Program Files (x86)\Lionhead Studios Ltd\Black & White`.

1. double-click (start) `Setup.exe`
    - setup your resolution and graphic settings
    - you may check "window mode" (for testing, later you can switch to fullscreen)


### Install Add-On (optional)

In Explorer, install the Creature Isle Add-on (`cdrom2`), run `Setup.exe`, install (fan) patches (`BWCIFanPatchInstaller.exe`), don't start game.

### Setup bottle (again)

Close the Explorer and go to the "Black & White" bottle, "Settings" -> "DLL Overrides", Add "New Override"s

- `blinkw32`
- `d3dim`
- `ddraw`
- `d3dim700`

![dll overrides](assets/screenshot5.png)

## Start/Test the Game

Start the Explorer, go to the game directory and start "runblack.exe"

if everything start and works your are golden 🎉

_Note: With the Fan Patch you should not need the no-cd exe ;), otherwise the game wouldn't start_

### Add Shortcuts

Go to the "Black & White" bottle and add "Programs"

- CreatureIdle - CreatureIdle -> `.../bottles/Black-&-White/drive_c/Program Files (x86)/Lionhead Studios Ltd/Black & White/CreatureIdle/CreatureIdle.exe`
- Setup -> `.../bottles/Black-&-White/drive_c/Program Files (x86)/Lionhead Studios Ltd/Black & White/Setup.exe`
- runblack -> `.../bottles/Black-&-White/drive_c/Program Files (x86)/Lionhead Studios Ltd/Black & White/runblack.exe`
- Setup - CreatureIdle -> `.../bottles/Black-&-White/drive_c/Program Files (x86)/Lionhead Studios Ltd/Black & White/CreatureIdle/Setup.exe`

![programs](assets/screenshot6.png)

_Tip: You can rename the "Setup" shortcut_

Try to start the game (`runblack`) via "Programs"...

If it wouldn't start, try disabling `VKD3D` (in "..." -> "Change Launch Options") and `DXVK`, set "Virtual Desktop" to "off".  
Try out (older) runners: `lutris-ge-...`, `ge-proton8`.
You can still start the game with the "Explorer" (`Legacy Wine Tools` -> `Explorer`).

#### Add to Steam (optional)

Click on "..." (runblack) -> "Add to Steam" (you may restart steam).


##### gamescope

In Steam go to "Black & White" -> "Manage" -> "Properties...", edit the current shortcut options _"START IN" may vary_

Add gamescope and extend launch options

![steam gamescope](assets/screenshot7.png)

#### Customize Header

Customize Logo and Header with [SGDBoop](https://www.steamgriddb.com/boop): https://www.steamgriddb.com/game/37411

![custom header](assets/screenshot8.png)


## Install Mods

- Replace `runblack.exe` with [Infinite Drawing Distance](https://www.bwgame.net/downloads/black-white-v1-42-infinite-drawing-distance.1464/)
- Replace game assets with [HD assets](https://www.bwgame.net/downloads/hd-project.1474/)
- Download more [Maps](https://www.bwgame.net/downloads/categories/maps.45/)

---

## Additional Infos

### Dependencies

![wine dependencies](assets/screenshot9.png)

_see [Exported bottle config](Black-&-White.yml) for more details_

### Limitations

- Game (window) only renders on the primary monitor, if you are playing in window mode.
- use fan patch or no-cd (exe)

### My Setup

- CachyOS (64 Bit)
- CPU: AMD (x86)
- GPU: Nvidia
- Hyprland (wayland)
- bottles installed via flatpak
- gamescope and steam installed via CachyOS Gaming package

---

## License

 CC-BY-SA 4.0

---

## Links

- https://www.bwgame.net/downloads/
- https://www.bwgame.net/threads/running-black-white-on-windows-10.7916/
- https://lutris.net/games/black-white/
- https://discord.com/channels/306953102848950273/1237853952066715708