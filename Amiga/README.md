# Amiga Reconfigurator

Inspired by posts like these:
* http://blog.petrockblock.com/forums/topic/launch-amiga-games-from-retropie-menu/
* https://retropie.org.uk/forum/topic/400/launching-amiga-games-form-emulation-station

These are scripts to configure EmulationStation and create configuration files to allow running of Amiga games directly from EmulationStation without having to launch uae4arm.

Features:
* Automatically updates uae4arm emulator configuration files to accept .uae file formats
* Assembles .uae configuration files for games with arbitrary numbers of disks
* Simultaneously supports multiple varying disk numbering formats and configurable custom ones too
  * GameName_Disk1.adf
  * GameName_Disk2.adf
  * OtherGame_disk_0.adf
  * OtherGame_disk_1.adf
  * SingleDiskGame.adf
  * GameFour (Disk 1 of 3).adf
  * GameFour (Disk 2 of 3).adf
  * GameFour (Disk 3 of 3).adf
  * Fifth-DskA.adf
  * Fifth-DskB.adf
  * Other examples too
  * Almost literally anything you can think of
  * Because regex is great
* Can be instructed to unzip .zip files, as long as and .adf or .adz file of the same name as the .zip file is in the .zip top level directory
* Is "quick": using this ROM set http://www.emuparadise.me/Complete_ROM_Sets_(Full_Sets_in_One_File)_ROMs/Amiga_Fullset/96280 on a Raspberry Pi 3 without overclock:
  * Unzip 4278 .adf floppy disk files and generate .uae files representing 2517 unique games in less than 17 minutes
  * Generate same .uae files from pre-unzipped .adf files in 3.5 minutes
* "Useful" output, verbose and quiet options available
* Won't overwrite .uae files unless you really want it to
* Some of the code is commented

Bad stuff:
* Default configuration values (pulled from uae4arm) aren't great, and I don't know enough yet to make intelligent revisions
* Probably more

Usage:
* SSH into your Raspberry Pi
* `git clone https://github.com/Douggernaut/RetroPieAssistant.git`
* edit RetroPieAssistant/Amiga/multidisk.cfg to add your custom regex for disk format strings as wanted/needed (feel free to ask for help on this)
* edit RetroPieAssistant/Amiga/template.uae as needed (and please tell me how also!)
* `./RetroPieAssistant/Amiga/run_all.sh`

Thanks for having a look!