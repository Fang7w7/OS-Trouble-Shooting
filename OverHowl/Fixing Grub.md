1. create a live usb
2. boot using it
3. find the actual root partition

now command 

````
sudo mount /dev/sdx /media //x is your root partition no
sudo mount --bind /dev /media/dev
sudo mount --bind /proc /media/proc
sudo mount --bind /run /media/run
sudo mount --bind /sys /media/sys

sudo chroot /media
ls /home/
grub-install /dev/sda

````