# CloverHDA High Sierra 10.14
![HDA Icon](https://github.com/insanelydeepak/cloverHDA-for-Mac-OS-Sierra-10.12/blob/master/res/cloverHDA.jpg?raw=true) 

___

Native audio for unsupported codecs in Mac OS Mojave 10.14 with Clover
This cloverHDA.kext enables audio/sound on Mac OS Sierra 10.14
___


if you like this project, please star it.

### Requirements : 
      1 - Vanilla/Native AppleHDA 
      2 - a good Kext Installer or [EastKextPro](http://www.insanelymac.com/forum/files/file/397-easykext-pro-a-minimal-and-super-fast-kext-installer/)
  
      3 - Property List Editors - Xcode or Property List Editor, PlistEdit Pro, TextEdit, etc.
      4 -  must have CLOVER/config.plist
           i. RtVariables/BooterConfig/0x28
            ii. RtVariables/CsrActiveConfig/0x3 


### Installation :

      1 - Download cloverHDA.kext as per your Audio ID's 
      2 - Install using EastKextPro or any Kext Installer to /S/L/E
      3 - Now apply patches from cloverHDA.plist to your Clover config.plist
      4 - Add Layout_ID = 14 as described in ReadME.txt (You don't have to do this if using method HDAEnabler or HDEF Patch)
      5 - Restart 

### How to apply patches :

      1 - Use a good plistEditor e.g PlistEdit Pro,Xcode,CloverConfigurator,CloverConfigurator Pro
      2 - open cloverHDA.plist , goto KernelAndKextPatches -> KextsToPatch like in below screenshot
      3 - copy all patches to your config.plist (one by one or all once ,its depend on your plist editor)
        
![Screenshot](https://github.com/insanelydeepak/cloverHDA-for-Mac-OS-Sierra-10.12/blob/master/res/cloverHDAPlist.png?raw=true)

#### Note : for Layout_ID you can use DSDT (HDEF Patch) or Clover (Clover/Config.plist/Devices/Audio/Inject=Audio_ID) or [HDAEnabler's kexts](https://bitbucket.org/insanelydeepak/hdaenablers-applehda-for-hackintosh/downloads)

### Layout_ID/Audio ID description :
   Use Layout_ID 14 for all desktop and laptop codec's

### Supported Codec/DEVICE_ID :
 please find your codec in repo respective desktop/laptop folder, if not exist feel free to open a issue. 


###  [Troubleshooting :](https://github.com/insanelydeepak/cloverHDA-for-Mac-OS-Sierra-10.12/blob/master/TroubleShoot/Troubleshoot%20Reporting.md)
     
     1.No Audio after installation : basically this happens due to CloverHDA is not loaded or LayoutID is not used either via DSDT(HDEF Patch) or Clover (config.plist) , also make sure that VoodooHDA or AppleALC is not installed.
     2.Headphone/Microphone is not working : you have to use Codec_commander , if still issue exist you need to make custom profil for Codec_commander so it can work with your codec.
     3.No Audio after Sleep : use EAPDFix or Codec_Commander , customize its info.plist as per your requirements.
     4.Device show but no Audio : Some laptops requires to use FakePCIID , use always latest version of FakePCIID from rehabman.
     5.if still not geting sound devices then : please report with Requested files ,
     
#### Note : for KabyLake System , use FakePCIID + HDMI kext from below link
(https://bitbucket.org/RehabMan/os-x-fake-pci-id/downloads/)

#### Note : Recommended to Use EasyKexPro for installation , Repair Permission and Rebuild Caches.
   

### Issue/Bug Reporting :
 if you need to fix your codec just [open a ticket on](https://github.com/insanelydeepak/cloverHDA-for-Mac-OS-Sierra-10.14/issues/new)

 You must have attached debug zip files requested in [Troubleshooting](https://github.com/black-dragon74/OSX-Debug) 


### How to get Codec Dump :
     1. Use Ubuntu or Any Version of Linux Distro (Note : Use the latest version of Linux and Alsa drivers )
     2. Open Terminal and copy paste below Code :
      cd ~/Desktop && mkdir CodecDump && for c in /proc/asound/card*/codec#*; do f="${c/\/*card/card}"; cat "$c" > CodecDump/${f//\//-}.txt; done && zip -r CodecDump.zip CodecDump
      
     3. On Desktop there’s a folder/file name Codec_dump
     4. Save this to safe place  



### Credits :
This kext is based on  [PikeRAlpha's DummyHDA method](https://pikeralpha.wordpress.com/2013/12/17/new-style-of-applehda-kext-patching/) and Clover Patches on fly  method's

PikeRAlpha, Mirone, EmlyDinesh, The king, Master Chief, RevoGirl, toleda, bcc9, TimeWalker and many others who contributed to AppleHDA patching.

## Donation
If this project help you reduce time to develop, you can give me a cup of coffee :) 

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](http://paypal.me/insanelydeepak)
