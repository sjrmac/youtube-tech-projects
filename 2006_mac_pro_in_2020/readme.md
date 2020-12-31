
## "2006 Mac Pro in 2020" Resources

This document contains all the resource info and links for the "2006 Mac Pro in 2020" video along with some extra info and notes that I thought I should include. This info ONLY APPLIES for Mac Pro 1,1 and 2,1 models.

## Overview

**Firmware upgrade + OS Install info**
 - Mac Pro 1,1 to 2,1 Firmware upgrade
 - Windows 10 install method
 - macOS El Capitan install method
 - rEFInd install info (I find this one handy!)
 - Tuning Windows 10

 **Parts purchased**
 (This section will have links and names of the items I bought for my upgrades)

**Extra resources and links**
(Worth taking time to look at if you really want to educate yourself on these machines and their quirks)

## Firmware upgrade + OS Install info Prep
Before you start following this portion of the guide, I will mention that I got pretty frustrated doing this, so it's okay if you do haha! Hopefully this will be a much smoother process for you :D

Here are the following things I recommend having before proceeding:

 - [ ] Flashdrive (larger than 8GB is good)
 - [ ] SATA to USB connector or caddy (trust me on this one, win10 install is much easier using this if doing on a external machine.)
 - [ ] A place to backup important files if you need to.
 - [ ] Internet connection (unless you know what you need to have prepared to do this offline)
 - [ ] Some patience LOL

**BACK UP ANYTHING IMPORTANT BEFORE PROCEEDING!!!**

## Firmware Upgrade

Let's start by upgrading the firmware from 1,1 to 2,1. If you are worried about doing this upgrade, you shouldn't be. It was a straight forward process for me and everything worked as it should. The 2,1 firmware supports all the CPUs that the 1,1 firmware did, and there's even a option to downgrade if you need to for some reason. This utility apparently also works on macOS 10.11, but I rather run it on Lion 10.7.5 (the last officially supported OS for the 1,1/2,1) for stability reasons.

Start by downloading the "**Mac Pro 2006-2007 Firmware Tool**" from this project's folder, or using the link below. 
(The copy here in the repo is the same as the one on Netkas, but I figured it's a good idea to have a copy in case the link goes down.)

> http://forum.netkas.org/index.php/topic,1094.0.html

Once you've got the zip downloaded, go ahead and extract it to get **"Mac Pro 2006-2007 Firmware Tool.app"**.
Next, let's download the **"Mac Pro EFI Firmware Update 1.2"** package here: 
> https://support.apple.com/kb/DL206?locale=en_US
If you can't use the download button for this package on Safari using the Mac Pro, use this direct link, or transfer the package using a flashdrive:
https://download.info.apple.com/Mac_OS_X/061-3943.20070927.pO93v/MacProFirmwareUpdate1.2.dmg

Once you have the dmg file downloaded, go ahead and mount it by opening it. Now open **"Mac Pro 2006-2007 Firmware Tool.app"** and click the "**Upgrade to 2007 Firmware**" button. The application will give you some instructions to follow. I recommend taking a picture of these just in case you might need to reference them later for any reason during the FW upgrade process. IF YOU HAVE ERRORS, refer to the bottom of this section for some handy links that should have a solution.

Alrighty! If you followed the instructions, you should now be able to see that your Mac Pro is now a 2,1 in the **System Information** application in macOS or OS X. Feel free to move on to the next section.

**IF YOU HAD ERRORS WITH THE FIRMWARE UTILITY APP, use the following links to find a solution:**

 - https://forums.macrumors.com/threads/mac-pro-1-1-firmware-upgrade-issues.2174741/
 - https://forums.macrumors.com/threads/mac-pro-1-1-firmware-to-2-1.1392341/

## OS Install:
**Important Background Info:**
I'll start with telling you that **Windows 10 Pro** is the best option for this machine in my opinion. Before you question why I said Windows 10 Pro, here's why you need the Pro version: it has support for more than one CPU, which is important if you'd like to take full advantage of having two physical CPUs. Home edition will only see one physical CPU. Windows is by far, the most pain in the ass OS to install due to Apple's 32 bit EFI and BIOS emulation CSM shit. I'll talk more about that later (bottom of the **rEFInd** section), but since I've seemingly found a fairly simple way to do the Windows install, it's not too bad to do.

If you are more of a macOS user, well, you really only have one option. Installing **macOS El Capitan** (10.11) is the absolute maximum version you can run on this Mac Pro. Installing El Capitan is really easy and plenty of apps still work on that OS, but it is old.

As for Linux at the time of me writing this, you are on your own. If I end up having to install Linux on this machine, I will update this guide with info on that. Heck, I might even do it if there is enough interest.

## Windows 10 Install:
Like I said in the YouTube video, this machine's full potential in today's world is utilized in Windows 10. Let's install it.

**DO NOT TRY the following ways to install Windows 10. I already did and it did not work.**

 - Via a USB installer created by the official Microsoft tool, or a program like Rufus (even with old BIOS fixes, MBR, etc...)
 - Via a SSD that was turned into installer media and inserted in a SATA slot (this is really dumb, I know... didn't boot...)
 - Via OS X, restoring as a DMG or something ¯\_(ツ)_/¯ 
 - Via a USB Installer and attempting to boot it through **rEFInd** (See the bottom of the **rEFInd** section for more info)

Please don't do any of those. Trust me, I wasted WAY TOO MUCH time seeing what Apple's EFI would accept or not.
I guess you could try Bootcamp, but I don't ever bother using that personally. **Hrutkay Mods** on YouTube has an excellent series on these Mac Pro 1,1/2,1 and I highly recommend watching a few of his videos for different install info if you want to try something else like DVD. Here's a link to the series: 
> https://www.youtube.com/watch?v=gVnJKGKtMbk&list=PLLcYxRX9ndMEl6ZPPnhrMJl6RQydGFvR2

Unfortunately, I don't have a method of doing this Win10 install on the Mac Pro itself using macOS or OS X. I personally would love to figure it out as it would make doing a Windows install more appealing, but I don't have one. Here's what you'll need though:

 - a Windows 10 machine to run **Rufus** to create a WinToGo drive and to run **brigadier** to download Bootcamp drivers)
 - Spare hard drive or SSD (I strongly recommend this so you can keep your Lion install in the event you might need it)
 - SATA to USB caddy or dock (I personally got one like this): https://www.ebay.com/itm/ORICO-2-5-SATA-USB-3-0-Hard-Drive-Disk-HDD-SSD-Enclosure-External-Laptop-Case/114500760179 (get something that suits the drive type you will use.)
 - a flash drive 8GB or larger just in case
 - Windows 10 64bit ISO, which can be obtained here: https://www.microsoft.com/en-us/software-download/windows10ISO or using the Media Creation tool and using the save the ISO option

On the Windows 10 machine, download the Win10 64Bit ISO, Rufus, then brigadier:
> https://rufus.ie/
> https://github.com/timsutton/brigadier/releases/download/0.2.4/brigadier.exe

Now's the time to hook up your HDD or SSD to the SATA caddy or SATA to USB adaptor that you want to use for the install. Make sure to identify which drive letter your external drive is mounted as. This is important because you don't want to accidentally wipe another drive out during the next few steps. Don't blame me if you select the wrong one!

Here's an image of how you need to configure and run Rufus:
(if your SATA to USB device doesn't appear in Rufus, make sure "**List USB Hard Drives"** is checked and select the right drive.0
![Rufus config for WinToGo 2006 Mac Pro](https://raw.githubusercontent.com/sjrmac/youtube-tech-projects/main/2006_mac_pro_in_2020/2006_mac_pro_windows_rufus1.png)
![Rufus config for WinToGo 2006 Mac Pro 2](https://raw.githubusercontent.com/sjrmac/youtube-tech-projects/main/2006_mac_pro_in_2020/2006_mac_pro_windows_rufus2.png)

While the WinToGo installation is being done through Rufus, we can use **brigadier** to grab the necessary Bootcamp drivers that we'll need on Windows to make the hardware talk to the software. You must run **brigadier** as Administrator in Windows (I've had issues without Admin privileges), then tell it what Mac model we need, which is "**MacPro2,1**". **Brigadier** will download the appropriate latest package for our Mac Pro and place it in the **Downloads** folder on Windows. When **brigadier** is finished, you can put its downloaded folder on the finished WinToGo disk created by **Rufus**, or on a flash drive so we can install the drivers from it later when we get Win10 booting.

Once Rufus is finished creating the WinToGo disk, eject the drive safely, then go ahead and install the drive into one of the Mac Pro's SATA slots. The easiest way to boot to the new Windows install, is by holding the **Option** key while your Mac Pro starts up until you see the Boot Device selection. Choose the Windows disk and not the EFI Boot drive. You may or may not experience a few reboots before reaching the Windows setup environment. ***If you experience reboots here, just hold the Option key and select the Windows drive again manually.***

Once you boot into Windows Setup, feel free to setup as you wish. Once you get to the desktop, you've successfully finished the initial install. If you open File Explorer and select "This PC", you'll notice that there is a drive called "**UEFI_NTFS**" and you can ignore it. This drive is a partition that Rufus made so that the WinToGo installation could be bootable on a system with UEFI. 
![Rufus Mac Pro 2006 UEFI_NTFS partition in File Explorer](https://raw.githubusercontent.com/sjrmac/youtube-tech-projects/main/2006_mac_pro_in_2020/IMG_20201129_102629.jpg)

**NOTE**: If you understand rEFInd and what it does, you'll notice there are .efi files in this **UEFI_NTFS** partition. You should be fine if you remove all the non ia32.efi files if you want to clean up a bit. I don't remember if everything was fine when I removed them. Let me know :D 

It's time to install the Bootcamp drivers, but we'll need to do it a specific way. You'll need the Bootcamp folder that **brigader** downloaded earlier. The folder should be named: **BootCamp-041-84868** (I don't think Apple released any package for 1,1/2,1 Mac Pros newer than this one)

Now, navigate to this path: BootCamp-041-84868\Drivers\Apple
![mac pro 2006 bootcamp drivers windows10 64 bit](https://raw.githubusercontent.com/sjrmac/youtube-tech-projects/main/2006_mac_pro_in_2020/Screenshot%202020-12-30%20215809.png)

We need to run **BootCamp64**, but before we run it, we need to set the application compatibility mode to "**Previous versions of Windows**". Right click on **BootCamp64**, Click Properties, then go to the Compatibility tab:
(Compatibility was set to Windows 7)
![mac pro 2006 bootcamp drivers windows10 64 bit 2](https://raw.githubusercontent.com/sjrmac/youtube-tech-projects/main/2006_mac_pro_in_2020/Screenshot%202020-12-30%20221222.png)

After clicking Apply, you may now run **BootCamp64** and let it install. It will install the Bootcamp Control Panel as well, which works. I have an Apple wired keyboard with numpad and my Function keys work the same as macOS or OS X.

When the drivers finish installing, it's a good time to reboot. Select the Windows drive manually during boot using the **Option** key, and then see if you need to download and install any Windows updates (chances are you will be doing so and that's fine.)

And there you have it, Windows 10 is installed! You now have the essential Bootcamp drivers you need. If you want to tweak Windows further, or read my notes on what I did to improve my experience, read "**Tuning Windows 10**" section.

## macOS El Capitan 10.11 Install Method One
Installing El Capitan is much easier than Windows 10. In fact, **Hrutkay Mods** on YouTube made this so simple, it's hard to screw up.

I'm gonna write a guide on how I did the install as well as it turned out to be an adventure because I had to work around a few limitations to get what I wanted haha :D

Here's what you need:
 - Spare wiped HDD or SSD installed in the machine
 - Internet connection
 - Flash drive 8GB or larger (format as MacOS Extended Journaled)
 - Optionally: copy of El Cap for Pikify (my method)

Let's start with **Hrutkay Mods** method. You can follow his video tutorial here: https://www.youtube.com/watch?v=6ziDKG-ESDo&ab_channel=HrutkayMods but I'll sum up his steps here.

**Steps:**
 - Dowload the El Capitan image from the links in his video description
 - Open **Disk Utility**, drag the El Capitan image in so it appears on the sidebar, then select it. Once the El Capitan image is selected, go to the Restore tab and make sure the Source option is set to the El Capitan image. Set the Destination option to the spare HDD or SSD you installed earlier and proceed to restore the image to the drive.
 - Once the image restore has completed, you can reboot while holding the **Option** key and then proceed to select the drive with El Capitan installed. It will boot, and then you can go through macOS setup as normal. 
 - **NOTE**: Disable and hide and incoming security updates in the Mac App Store as they can prevent the machine from booting. Someone online did write a script that should prevent the security updates from replacing the modified files that the Mac Pro needs to boot 10.11, but I am unsure if that script comes with this special disk image from **Hrutkay Mods**. More info about updates here: https://forums.macrumors.com/threads/2006-2007-mac-pro-1-1-2-1-and-os-x-el-capitan.1890435/ (I'll reference this link later on with my install method).

Thanks **Hrutkay Mods** for this easy install method!

## macOS El Capitan 10.11 Install Method Two
Essentially, we have to use install method one. Why? Well, unless you have a copy of the full macOS El Capitan installer application laying around anywhere, it won't be so easy. So why make things more complicated? Install method one is easy, so why should I bother with anything else? Let me explain. (You could try doing this method in Lion maybe).

I prefer a total clean install... While the disk image that was created for **Hrutkay Mods** and his tutorial seems safe, I wanted to go a step further. I wanted to run a freshly sourced El Capitan installer application through the **Pikify** app, which essentially creates a USB installer that will boot on our Mac Pros with EFI32 support. Install method one has this support baked in (the disk image you restore is basically a fresh install of El Cap and the necessary EFI mods).

So here's what I did along with some extra notes. I'm sure there's another way to do this, but whatever haha :D
You need the following:

 - Flash drive 8GB or larger formatted as MacOS Extended Journaled
 - El Capitan **InstallMacOSX.dmg** from Apple: https://support.apple.com/en-us/HT211683
 - Pikify App: https://forums.macrumors.com/threads/2006-2007-mac-pro-1-1-2-1-and-os-x-el-capitan.1890435/page-56#post-22335903 (I host a copy here on GitHub in this project folder as well.)

**Steps**
 - Installed El Capitan via method one
 - Grabbed the El Capitan **InstallMacOSX.dmg** from Apple 
 - Installed the package from the disk image to get the macOS El Capitan installer application into the Applications folder, then opening it to see if it would run.
 - Ran the **Pikify** app and created a USB installer. (Make sure your USB drive is formatted as MacOS Extended Journaled. I figured that out after a few tries and it just worked after I formatted as Extended Journaled.)
 - USB Installer creation finished, then rebooting while holding the **Option** key to select the installer disk and proceeded to install El Cap to the drive of my choice. (If El Cap won't install, read the the top of the post where you can download Pikify from. This is likely the expired certificate issue people run into doing older macOS installs)

After completing the steps above, I had a nice clean copy of El Capitan installed with Piker-alpha's EFI mods. Everything works as expected. On the plus side, you now have a USB drive you could use for reinstalls as well, or recovery (if you did some wack stuff).

## rEFInd Installation
If you are reading this portion of the guide, I'll make the assumption that you are more technically inclined and watched the YouTube video and the portion of it where I explained why I use rEFInd.

You can read about the macOS/OS X install procedure here: http://www.rodsbooks.com/refind/installing.html#osx or I'll put commands and setup info below. The reason I install rEFInd on a macOS or OS X drive is because Apple's boot system will default to Apple operating systems. In my case, my 10.11 El Capitan drive is in slot 1 and the Windows Drive in slot 2. I believe that the boot system looks for an Apple OS before considering any other options, regardless of what slot the drive is in. Since my El Cap drive is in slot 1 and has an Apple OS on it, the boot system will look at that drive's EFI setup first, so to me, it makes sense to put rEFInd on that drive and "bless" it so that the boot system starts rEFInd every time by default.

To get rEFInd installed and working properly, you need to do the following:

 - Start with disabling **System Integrity Protection**(if on 10.11 only as anything older doesn't have this feature): Boot to macOS Recovery, open Terminal, and type "**csrutil disable**", then reboot back to macOS.
 - Download rEFInd from Sourceforge: https://sourceforge.net/projects/refind/
 - Unzip the downloaded zip (Downloads folder is totally fine)
 - Open **Terminal**, change directory to the downloaded and extracted rEFInd folder (version of rEFInd may change FYI, so keep that in mind when copy pasting the following command): 

> cd /Users/your username/Downloads/refind-bin-0.12.0/
 - Mount the ESP partition by running a script included in the **refind** folder: 
> sudo ./mountesp
 - Make a rEFInd folder on the ESP partition:
> sudo mkdir -p /Volumes/ESP/efi/refind
 - Move **refind** folder to ESP partition: 
> sudo cp -r refind/* /Volumes/ESP/efi/refind/
 - Now we'll remove any non **ia32** components since we cannot use them and rEFInd won't boot unless they are gone: 
> sudo rm /Volumes/ESP/efi/refind/refind_x64.efi Volumes/esp/efi/refind/refind_aa64.efi /Volumes/ESP/efi/refind/drivers_x64 /Volumes/ESP/efi/refind/drivers_aa64 /Volumes/ESP/efi/refind/tools_aa64 /Volumes/ESP/efi/refind/drivers_x64
 - Now, with cleanup complete, we'll finish up with making sure the config file is right:
> sudo mv /Volumes/ESP/efi/refind/refind.conf-sample /Volumes/ESP/efi/refind/refind.conf
 - Last step is to bless the efi file so that the firmware will start it every time:
> sudo bless --mount /Volumes/ESP --setBoot --file /Volumes/ESP/efi/refind/refind_ia32.efi --shortform 

And thats it! I recommend rebooting now, then using rEFInd to boot to the macOS recovery partition and enabling **System Integrity Protection** again in Terminal (again, only if on macOS 10.11, older OSes don't apply to this feature):
> csrutil enable

Congratulations, rEFInd is installed. It's up to you how you use it now :) Just remember that rEFInd is installed on a disk and is not part of the firmware, so if you remove the drive that rEFInd is on, the Mac will not start it without that drive.
My install boots up and works great:
![rEFInd on 2006 Mac Pro 1,1 2,1](https://raw.githubusercontent.com/sjrmac/youtube-tech-projects/main/2006_mac_pro_in_2020/IMG_20201129_100100.jpg)

I use it to auto-select and boot to Windows 10, since that's the only OS I have use for on my Mac Pro. Windows 10 also seems to start quicker through rEFInd. If you try booting a Windows installer USB through rEFInd, you'll end up seeing this message on your display:
![rEFInd USB boot error Windows 10 Mac Pro](https://raw.githubusercontent.com/sjrmac/youtube-tech-projects/main/2006_mac_pro_in_2020/IMG_20201128_230405.jpg)

**If you'd like to follow rEFInd's official tutorial, it is available here: http://www.rodsbooks.com/refind/installing.html#osx**

## Tuning Windows 10
I'm sure you can tune things further, but this is what I did:
* Enable AHCI support (speed boost over using IDE, trust me, 100% worth the extra work)
* Make the new Broadcom BCM94360CD wireless card work using Bootcamp drivers
* **Hrutkay Mods** Bootcamp 6 package + benefits (worth considering and doing)

**AHCI Guide:**
I just followed **Hrutkay Mods** video on this. No need for me to put the instructions here as the video is perfect.
https://www.youtube.com/watch?v=MAv4v5LhTWk

**Broadcom BCM94360CD** support:
I went and grabbed this Bootcamp driver package from Apple's website downloads as it was the latest one available*: 
> https://support.apple.com/kb/DL1837?viewlocale=en_US&locale=en_US

(*without using a Mac to grab the driver folder through the Bootcamp utility, or **brigader** to download a newer package)

I then installed these drivers (Win8 one rather than Win7):
![2006 mac pro windows 10 Broadcom BCM94360CD ](https://raw.githubusercontent.com/sjrmac/youtube-tech-projects/main/2006_mac_pro_in_2020/Screenshot%202020-12-30%20215958.png)

Once you install those individually, they may or may not auto detect the hardware. You may need to go into **Device Manager** and manually set up the device with the proper driver. (Unchecking "Show compatible hardware" will let you find the right driver in the list)
![enter image description here](https://raw.githubusercontent.com/sjrmac/youtube-tech-projects/main/2006_mac_pro_in_2020/Screenshot%202020-12-30%20221124.png)

**Hrutkay Mods** has a video on newer Bootcamp drivers and there's a section in the video where he shows how to manually install drivers if you get stuck: 
> https://www.youtube.com/watch?v=i0x96t8DSp4

**Hrutkay Mods Bootcamp 6 Package installation**
Just watch the videos :D (great content and reasoning behind doing this)
> https://www.youtube.com/watch?v=i0x96t8DSp4
> https://www.youtube.com/watch?v=PtnMPNlnj28

## Parts I Purchased
Here's a list of the things I bought that I think are worthy upgrades and good for value. This should be self explanatory.

 - Mini 6pin to 6pin PCIe cable for Mac Pro: https://www.ebay.com/itm/Mini-6pin-to-6pin-PCIe-Pci-express-Video-Card-Power-Cable-for-Apple-Mac-Pro/274332705429 $5.95
- Dual Mini 16 AWG 6pin to 8pin cable: https://www.ebay.com/itm/Dual-Mini-16-AWG-6-Pin-To-8-Pin-For-Mac-Pro-Graphics-Card-Power-Cable-GTX1080-US/363079402279 $6.88
- ORICO Superspeed 7 Ports PCI-E to USB 3.0 Card: https://www.ebay.com/itm/ORICO-Superspeed-7-Ports-PCI-E-to-USB-3-0-Expansion-Card-for-Windows-XP-Linux/202859069118 $19.94
- iMac 27” A1419 Late 2015 Airport/Bluetooth Card Broadcom BCM94360CD: https://www.ebay.com/itm/iMac-27-A1419-Late-2015-WiFi-Bluetooth-Airport-Card-Broadcom-BCM94360CD/254383475416 $31.33
- Apple Wireless Card to Mini PCI-E Adapter for BCM94360CD https://www.ebay.com/itm/For-Apple-Wireless-Card-to-Mini-PCI-E-Adapter-Converter-for-BCM94360CD-BCM94331/193263453948 $7.99
- Intel Xeon X5355 2.66GHz LGA 771: https://www.ebay.com/itm/Matching-pair-Intel-Xeon-X5355-2-66-GHz-SL9YM-SLAC4-SLAEG-LGA-771-CPU-Processor/272964776764 $11.99

Total before tax: $84.08
Total after tax: $92.85

**NOTE**: The reason I got the PCIe power cables was due to the fact that I had planned to put a different GPU in the Mac Pro (like the Radeon 5870 I had in the YouTube video). Unfortunately, I didn't get the 5870 to work, but those cables could serve useful depending on what kind of GPU I could get in the future. **Get the type that suites your needs :D**

**Compatibility Notes:**
 - The ORICO USB 3.0 card I list here isn't compatible with macOS or OS X. Works great in Windows 10 with the driver!
 - The Broadcom BCM94360CD wireless card upgrade is great if you are fine without having wireless in Mac OS X 10.7 Lion. Works in macOS 10.11 El Capitan perfectly, and in Windows 10, with the proper Bootcamp driver as well (Check extra notes to read up on how I got it working).

## Extra Resources and Links:
There is no way I could have written this guide and simplified things had I not seen the following main pages I used for info. Worth reading through some of these if you want to learn more about Mac Pros, the 32 bit EFI mods, etc.

 - Greg Gant's **"The Definitive Classic Mac Pro (2006-2012) Upgrade Guide"** http://blog.greggant.com/posts/2018/05/07/definitive-mac-pro-upgrade-guide.html
This guide by far, is the best technical resource thing I have found on Mac Pros. It is absolutely phenomenal to have a resource like this. Extremely valuable for any classic Mac Pro (2006-2012) users!!!

 - Apple Mac Pro Diagnostic / Repair Guide: https://tim.id.au/laptops/apple/macpro/macpro.pdf
 Good for hardware debugging and learning how to read the diagnostic lights.

 - **Hrutkay Mods** Mac Pro YouTube series: https://www.youtube.com/watch?v=gVnJKGKtMbk&list=PLLcYxRX9ndMEl6ZPPnhrMJl6RQydGFvR2
Greg produced some great videos on the 1,1/2,1 and I recommend watching them as well as there is valuable information to take note of. He's also got more Mac related content that you may enjoy as well!

 - Netkas Forum for the Mac Pro Firmware Upgrade utility: http://forum.netkas.org/index.php/topic,1094.0.html

 - MacRumors **2006/2007 Mac Pro (1,1/2,1) and OS X El Capitan**: https://forums.macrumors.com/threads/2006-2007-mac-pro-1-1-2-1-and-os-x-el-capitan.1890435/
Even though this thread is mainly about the El Cap install and Piker-alpha EFI info, it's still very handy and a good read.

 - For Windows 64 bit install info, I came across this site, which gave me some ideas, resulting in the WinToGo install solution: https://www.hackintosh-forum.de/forum/thread/44482-macpro-1-1-flash-to-macpro-2-1-with-win10-x64-install-at-32bit-efi-incl-bootcamp/
 - Another Windows 10 thread for ideas: https://forums.macrumors.com/threads/windows-10-install-mac-32bit-efi-working-fix-select-cdrom-boot-type.2217681/

- rEFInd: http://www.rodsbooks.com/refind/
This tool is worth reading about as well. Solid boot manager!

**That is all the extra information I used, plus lots of Google searching to find those sites. Don't be afraid to Google stuff!**

I hope you appreciate this guide as it took me quite some time to make sure I got everything right.

***sjrmac (Samuel Ridosko)***
