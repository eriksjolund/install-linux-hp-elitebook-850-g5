Experiences running Ubuntu Linux on a HP Elitebook 850 G5

# Running Linux (Ubuntu Desktop 18.04.1) on HP Elitebook 850 G5

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

### BIOS update

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
