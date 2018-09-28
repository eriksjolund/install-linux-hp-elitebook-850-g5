# Running Linux (Ubuntu Desktop 18.04.1) on HP Elitebook 850 G5

Sharing some experiences about running Ubuntu on an HP Elitebook 850 G5 laptop.


Right now this document is only half-way finished. Hopefully I will find time to provide some more information.

## What works

Basic functionality is working

* WIFI
* HDMI to an external monitor (even with the lid closed). Tested with a Dell UZ2715Hb monitor that has 1080p max resolution.
* Trackpad
* Mouse button (to steer the mouse pointer)

I haven't tested much more than that.

## Customization of the laptop

The laptop was customized by me and then assembled by HP like this

    HP IDS UMA i5-8250U 850 G5 Base NB PC 
    FreeDOS 2.0 SE/FI 
    No Webcam 
    15.6 inch FHD (1920x1080) Anti-Glare LED UWVA 220 slim 
    32GB (2x16GB) DDR4 2400 
    1TB PCIe NVMe Three Layer Cell Solid State Drive 
    No Near Field Communication (No NFC) 
    Intel 8265 ac 2x2 nvP +Bluetooth 4.2 WW with 2 Antennas 
    No WWAN 
    No Fingerprint Sensor 
    Active SmartCard 
    3 Cell 56 WHr Long Life 
    45 Watt Smart nPFC Right Angle AC Adapter 
    C5 1.8m Sticker Conventional Power Cord SE/FI 
    3/3/0 Warranty EURO 
    No vPro AMT supported 
    DIB HP Basic Carrying Case 
    Country Localization SE/FI 
    Dual Point with numeric keypad spill-resistant Collaboration SE/FI 
    EU RED Pictogram Label 
    Core i5 G8 Label 
    HP 1 year Priority Management Service for PCs (1000+ seats) 
    HP 3 year Next Business Day Onsite Notebook Only Hardware Support 
    HP Operations Service

The laptop was delivered to me in the end of August 2018.

Short summary of hardware configuration

* RAM : 32 GB RAM
* Operating system : FreeDOS
* 1TB SSD
* 15.6" inch screen (resolution 1920x1080)

## Installation

The computer came with _FreeDOS_ already installed. 
Instead of using FreeDOS, I installed Ubuntu 18.04.1 (wiping the whole hard drive).
Unfortunately, it was a few weeks since I performed the installation so I don't remember the details.
I believe it was very straightforward (selecting default choices).

Here is the partition table

    root@laptop:~# fdisk -l /dev/nvme0n1
    Disk /dev/nvme0n1: 953,9 GiB, 1024209543168 bytes, 2000409264 sectors
    Units: sectors of 1 * 512 = 512 bytes
    Sector size (logical/physical): 512 bytes / 512 bytes
    I/O size (minimum/optimal): 512 bytes / 512 bytes
    Disklabel type: gpt
    Disk identifier: 06016D96-2E6A-4584-9897-E9C6E2DDD47B
    
    Device           Start      End  Sectors  Size Type
    /dev/nvme0n1p1    2048  7999487  7997440  3,8G EFI System
    /dev/nvme0n1p2 7999488 39999487 32000000 15,3G Linux filesystem
    root@laptop:~#
    
The EXT4 file system is used

    root@laptop:~# file -s /dev/nvme0n1p2 
    /dev/nvme0n1p2: Linux rev 1.0 ext4 filesystem data, UUID=9b426948-95ac-4325-8f42-f3ba5fd94f7a (needs journal recovery) (extents) (64bit) (large files) (huge files)
    root@laptop:~# 



### BIOS update

I rebooted the laptop and went into the BIOS. From there it was possible to download
and install a newer version of the BIOS.

An even newer version of the BIOS is available from the HP web page

    HP Firmware Pack (Q78)  01.03.00 Rev.A	 16.5 MB	22 aug 2018

https://support.hp.com/us-en/drivers/selfservice/hp-elitebook-850-g5-notebook-pc/18491276

but I wonder how to install it:

https://github.com/eriksjolund/install-linux-hp-elitebook-850-g5/issues/2

## Output from some commands

### sudo lshw -sanitize

    linux@laptop:~$ sudo lshw -santize > output/lshw.txt
    [sudo] password for linux:
    linux@laptop:~$

See the output in [output/lshw.txt](output/lshw.txt)

### lsmod

    linux@laptop:~$ lsmod > output/lsmod.txt
    linux@laptop:~$

See the output in [output/lsmod.txt](output/lsmod.txt)

### cat /proc/cpuinfo

    linux@laptop:~$ cat /proc/cpuinfo > output/cpuinfo.txt
    linux@laptop:~$

See the output in [output/cpuinfo.txt](output/cpuinfo.txt)

### cat /proc/meminfo

    linux@laptop:~$ cat /proc/meminfo > output/meminfo.txt
    linux@laptop:~$

See the output in [output/meminfo.txt](output/meminfo.txt)
