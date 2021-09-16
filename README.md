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
