# Mods

## Ultimate

_[Black & White: Ultimate](https://www.bwgame.net/downloads/black-white-ultimate.1460/) is a fan overhaul and modpack for Black & White 1 that includes gameplay tweaks, bug fixes, and an all-in-one experience._

> Ultimate is a large modification based on Black & White: Creature Isle. It includes the original Black & White story, the original Creature Isle story and a bunch of extra features, all in one game. 

**Important:** Start from a clean installation of Black & White + Creature Isle.
_Do **not** install unofficial fan patches or the infinite draw-distance mod with Ultimate, as these fixes are already included on their own._

_Best practice: Create a completely new bottle for Black & White: Ultimate with a fresh B&W installation._

1. Install Black & White + Black & White: Creature Isle (updated to v1.23)
2. Download [Black & White: Ultimate v1.40](https://www.bwgame.net/downloads/black-white-ultimate.1460/)
3. Drag and drop the "Ultimate" folder into your Black & White directory (`C:\Program Files (x86)\Lionhead Studios Ltd\Black & White`)
4. Add "BWUltimate.exe" as a Bottles Program -> `.../bottles/Black-&-White/drive_c/Program Files (x86)/Lionhead Studios Ltd/Black & White/Ultimate/BWUltimate.exe`
5. Download [dxwrapper](https://github.com/elishacloud/dxwrapper).
6. Extract "dxwrapper" into `Black & White/Ultimate/DDraw`
7. Go to the `DDraw/` folder and rename the original `ddraw_compat.dll` to `ddraw_compat.dll.bak`
8. Copy `ddraw.dll` out of the `Stub/` folder and paste it into `Black & White/Ultimate/DDraw`, then rename this new `ddraw.dll` to `ddraw_compat.dll`
9. Set up your "DLL Overrides" and configure `dxwrapper.ini` (see below)

_You can delete the `Stub/` folder now (optional)._

![DDraw Folder](../assets/screenshot10.png)

### DLL Overrides

Add these DLL overrides and set them to:

`Native, then Builtin`

- `d3dim`
- `d3dim700`
- `ddraw`

_These overrides force Wine to prefer native DirectX wrapper DLLs over Wine’s built-in implementations._

### Configure dxwrapper.ini

_The `dxwrapper.ini` file is included with dxwrapper._

Open `dxwrapper.ini` (`Black & White/Ultimate/DDraw/dxwrapper.ini`) and change the following values:

- `D3d9to9Ex=1`
- `Dd7to9=1`
- `DdrawUseDirect3D9Caps=1`

You can configure many more options, such as running the game in borderless fullscreen:
```ini
[Compatibility]
Dd7to9                     = 1
D3d9to9Ex                  = 1
EnableDdrawWrapper         = 1

[FullScreen]
FullScreen                 = 1
ForceWindowResize          = 1
WaitForWindowChanges       = 0


[d3d9]
EnableVSync                = 1
LimitPerFrameFPS           = 60
FullscreenWindowMode       = 1
```

### Notes

- `gamescope` didn't work for me with `dxwrapper`, but try to setup as much as possible with `dxwrapper` (like VSync and FrameCap)
- try reenabling "DXVK" (in bottles)
- try newer wine runners (`kron4ek-wine-proton-10...`, `ge-proton10`)
- Set "Windows Version" to "Windows 10"
- `dxwrapper` improves DirectDraw compatibility on modern Wine/Proton setups

### Troubleshooting

#### No Menu

- Verify that `ddraw_compat.dll` was replaced correctly and that Wine is successfully using `ddraw` as Native.

#### Crashes on launch

- Disable DXVK temporarily
- Try another Wine runner

#### Cursor issues

- Try running the game in windowed mode.
- Uncheck "Windowed Mode" in the Black & White Setup.exe (to use fullscreen mode), and then configure `dxwrapper.ini` to handle the fullscreen layout.

#### Special Thanks

Thanks to the community on the Black & White Discord and to Shane for creating this mod!

## Vanilla 

_Using standard fan patches_

- [B&W: Mods Apps Tools](https://www.bwgame.net/downloads/categories/b-w-mods-apps-tools.46/)
- [Maps](https://www.bwgame.net/downloads/categories/maps.45/)

- [HD Project - V1.56 Final.7z](https://www.bwgame.net/downloads/hd-project.1474/)
- [Infinite Drawing Distance - runblack.zip](https://www.bwgame.net/downloads/black-white-v1-42-infinite-drawing-distance.1464/)