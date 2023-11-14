# Root
chmod 666 /dev/mmcblk0 && umount /media/jack/boot && umount /media/jack/root

## Write image to disk 
bmaptool copy core-image-full-cmdline-beaglebone-yocto.wic /dev/mmcblk0

# User

## Build image
bitbake core-image-full-cmdline
bitbake core-image-minimal


