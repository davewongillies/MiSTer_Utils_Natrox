A plea
=============
**Please** support me on https://ko-fi.com/natrox!
As of writing (7th of June 2025), I am going through a very hard time financially.

Many people use the SD migration tool. It is available for free to help the community.
However, if you think the utility has helped you well, 

I would appreciate your support!

Last updated on: 2025-06-07

Have an idea for a utility or need a specific one?
===================================================
Please open a PR with "[Utility request]". `migrate_sd.sh` was also made by request after all.

Extra utilities for your MiSTer FPGA
====================================
This repository is an ongoing effort to create extra scripts, programs, documents and more for the MiSTer FPGA.
Please feel free to use them as you see fit - if you wish to integrate these resources into your own repository and/or pack, please comply with the LICENSE.

Directories
-----------
These are subject to change, but right now this is how I have things set up:

| Directory   | Description                                                |
| ----------- | ----------------------------------------------------------:|
| `Scripts`   | Scripts and binaries for use ON the MiSTer FPGA.           |
| `docs`      | Documentation and tutorials generally related to MiSTer.   |
| `host`      | Scripts and binaries for use on Linux I think are useful.  |

Each entry in each folder will have some description in this README.

How to use
----------
For `Scripts`, if your MiSTer isn't connected to the Internet you can clone this repository or directly download the raw files. Put them in `/media/fat/Scripts`.

If your MiSTer is connected to the Internet you can add the following to `/media/fat/downloader.ini`:

```ini
[MiSTer_Utils_Natrox]
db_url = https://raw.githubusercontent.com/Natrox/MiSTer_Utils_Natrox/db/db.json.zip
```

Then run `update_all` to install the scripts.

If you cherry-pick your downloads, some of the programs in `Scripts` may have dependencies - these will be checked for at run-time, so you can figure out which other files you should download. These dependencies are strictly limited to this repository.
I also recommend to try and read the scripts. Although I will do my best to explain them in this README, it is always good to know what you are installing.

The `docs` folder will have tutorials and documentation in either markdown or PDF format. Some of these documents are related to the programs found in this repository - while others are not. All documents do relate to either MiSTer FPGA, or relate to procedures that help you accomplish certain goals useful for your MiSTer. `docs` does not follow the GPLv3 license - everything within is _Public Domain_.

Utilities for use on your computer can be found in `host`. Although some of these may work on MiSTer's embedded operating system, they are principally designed for use on computers running some flavor of Linux. As with the programs in `Scripts`, the programs in `host` may have dependencies (including external ones). It is recommended to download/clone the entire folder. For external dependencies, I aim to include dependency checking within each program, but I can not guarantee it. As usual, please read the source code to get a better idea of how these programs function.

Descriptions
============
This is a complete list of everything found in this repository. It will be updated as more data is added.

`Scripts`
---------
* `migrate_sd.sh` 
This utility can be used on a running MiSTer system to migrate to a new SD card. A USB SD card adapter is required to be connected to your MiSTer. The target SD card can be of any size - as long as it can fit all of the data on the source SD card. It performs a number of checks to make sure that the migration will be successful. 
A key feature of this utility is that it looks at the source SD card's disk geometry and reproduces the required geometry on the new SD card. This means that the U-Boot partition located at the tail-end of the disk is copied over, while the rest of the card is formatted to exFAT for data use. All of the original data is copied over by default - version 0.2.0 introduces folder filtering, giving you the option to skip folders if you so desire. 
This utility is designed to be run from the MiSTer main menu, it will guide you through disk selection and it performs the necessary checks. During the process, it will freeze the main MiSTer binary to ensure file integrity. 
It can also be used to make a backup SD - although it is not suitable for incremental backups.
* `psx_chd_organize.sh` 
An extremely simple utility that will organize loose `.chd` images in `/media/fat/games/PSX` into folders. 
Includes support for multi-disk games. To be expanded some day. 
* `auto_downclock.sh` 
This utility automatically downclocks the MiSTer to 400MHz if a wireless controller loses connection. The idea behind it is that whenever the controller disconnects, it is likely that I am not using the MiSTer. 
When the controller reconnects, the MiSTer is clocked back up to what is normally runs at. 
It is compatible with the overclocking scripts. However, it is ultimately a fairly useless utility since running at a lower clock speed does not seem to impact thermals at all. 
Use at your own risk, I have only tested this with the wireless Xbox 360 dongle. 

Where is the rest?
==================
More is coming soon! I will continuously update this repository as I create more stuff for MiSTer.
Please feel free to watch this repository.
