# yocto-Beaglebone-Black

Build Steps  

git clone https://github.com/arjuncr/yocto-Beaglebone-Black.git   

. oe-init-build-env  


```
bitbake core-image-minimal
Loading cache: 100% |                                                                                  | ETA:  --:--:--
Loaded 0 entries from dependency cache.
Parsing recipes: 100% |#################################################################################| Time: 0:00:21
Parsing of 828 .bb files complete (0 cached, 828 parsed). 1469 targets, 62 skipped, 0 masked, 0 errors.
NOTE: Resolving any missing task queue dependencies

Build Configuration:
BB_VERSION           = "1.51.1"
BUILD_SYS            = "x86_64-linux"
NATIVELSBSTRING      = "ubuntu-20.04"
TARGET_SYS           = "arm-poky-linux-gnueabi"
MACHINE              = "beaglebone-yocto"
DISTRO               = "poky"
DISTRO_VERSION       = "3.3+snapshot-71dfb3b237391ccc840ca5e0c0fa9e38ed79be5c"
TUNE_FEATURES        = "arm vfp cortexa8 neon callconvention-hard"
TARGET_FPU           = "hard"
meta
meta-poky
meta-yocto-bsp       = "master:71dfb3b237391ccc840ca5e0c0fa9e38ed79be5c"

```


## Create SD card Partition to boot the board       
Create the partition in the SD card and copy the generated file in those partitions.     

You can use GParted to create the partition.      

Create the first partition with the following details.      
Name of the partition - BOOT      
Size - 150 MB.      
Flag - Set the boot flag     
Type - FAT32       
Create 2nd partition with the below details.      
Name of the partition - ROOT.      
Size - greater than 1024 MB or remaining space of SD card.     
Type- ext4     

## Copy generated image in SD card partition    
Make sure your SD card is mounted on the host pc and you can access both SD card partitions.      

# copy files from build/tmp/deploy/images/beaglebone-yocto/ to SD card boot and root partition.      
cp MLO-beaglebone-yocto /media/tutorialadda/BOOT/     
cp u-boot.img /media/tutorialadda/BOOT/      
sudo tar -xvf core-image-minimal-beaglebone-yocto.tar.bz2 /media/tutorialadda/ROOT/     

## Booting     
Follow the below steps and boot the board with your Custom Linux image.     
  
Insert SD card into beaglebone black card slot.     
Connect the serial cable to monitor bootup logs and login to beaglebone black.    
Press the S2 button while connecting power to beagle bone.    
You will get the bootup log on the serial console.    
