
# MiSTer Attract Mode
**Enjoy the beautiful pixel art and sounds of games in your MiSTer library - like being at the arcade!**

Attract Mode is a script which starts a random game on the MiSTer FPGA. The script is highly customizable through the included ini file (details below). Games can be played in Attract Mode, but the next game loads automatically after 2 minutes. This is meant as a show! When you're done just ***cold reboot*** your MiSTer from the OSD (F12) menu - or use the power button.

## Usage
To cycle through the supported MiSTer cores, copy `Attract_Mode.sh` and `Attract_Mode.ini` to `/media/fat/Scripts` Directory. The INI is optional, but strongly recommended if you want to customize behavior.

## Supported Systems
Currently supported MiSTer cores:
* Arcade
* Genesis
* Mega CD
* Neo Geo
* SNES
* TurboGrafx-16 CD AKA PC Engine CD

## MiSTer Configuration
The [Update-all](https://github.com/theypsilon/Update_All_MiSTer) script works great for putting system files in the right places.

### USB Storage
/media/usb may cause issues due to NTFS being case-sensitive on MiSTer.

### Console Cores
Make sure you are using the recommended folder structure, such as /media/fat/Games/SNES/. The script supports zipped Everdrive packs or unzipped folders. For MegaCD and Turbografx16 CD games must to be in CHD format.

## Attract Mode Configuration
### Optional features
Included in `/Optional/` are several additional scripts. These require `Attract_Mode.sh` to run.

Each Attract_Mode_*system*.sh script cycles games from just that one system - not all of them.

Also included is `Lucky_Mode.sh` and corresponding system-specific Lucky_Mode_*system*.sh scripts. Lucky mode picks a random game and loads it - no timer to worry about! This is a great way to explore and play your collection.

To use these options just copy the optional script(s) you want into the same location as Attract_mode.sh - by default `/media/fat/Scripts/`.

### Arcade Horizontal or Vertical Only
Change the "orientation" setting in the `Attract_Mode.ini` file to choose from only horizontal or vertical arcade games.

### Exclude
Want to exclude certain arcade games? Just add them to `mraexclude` in the `Attract_Mode.ini` file.

## How it works
MiSTer arcade cores are launched via a MiSTer command. For console games there is no official way to load individual games programmatically. Attract Mode automates the process by sending simulated button presses to the MiSTer. This is done with a modified version of [pocomane's MiSTer Batch Control](https://github.com/pocomane/MiSTer_Batch_Control). 

## Mister Bug
Currently the Menu Core causes issues where games stop changing and new input is not accepted after a certain time (If 20s timer it takes around an hour to fail). Unfortunately, only physically turning the Mister off fixes this. The issue is under investigation.
