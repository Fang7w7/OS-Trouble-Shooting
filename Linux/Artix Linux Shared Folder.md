1. sudo pacman -S linux-lts-headers
2. sudo pacman -S virtualbox-guest-utils
3. sudo mount -t vboxsf  -o gid=1000,uid=1000 artix_share /media/
###mounting the shared folder in /media directory

4. sudo chown -R saeed:saeed /media/ 


The mount point in arch is in /run/media/saeed/



1.  Open VirtualBox
    
2.  Right-click your VM, then click **Settings**
    
3.  Go to **Shared Folders** section
    
4.  Add a new shared folder
    
5.  On **Add Share** prompt, select the **Folder Path** in your host that you want to be accessible inside your VM.
    
6.  In the **Folder Name** field, type `shared`
    
7.  Uncheck **Read-only** and **Auto-mount**, and check **Make Permanent**
    
8.  Start your VM
    
9.  Once your VM is up and running, go to **Devices** menu -> **Insert Guest Additions CD image menu**
    
10.  Use the following command to mount the CD:
    

```
sudo mount /dev/cdrom /media/cdrom
```

11.  Install dependencies for VirtualBox guest additions:

```
sudo apt-get update
sudo apt-get install build-essential linux-headers-`uname -r`
```

12.  Run installation script for the guest additions:

```
sudo /media/cdrom/./VBoxLinuxAdditions.run
```

13.  Reboot VM

```
sudo shutdown -r now
```

14.  Create "shared" directory in your home

```
mkdir ~/shared
```

15.  Mount the shared folder from the host to your ~/shared directory

```
sudo mount -t vboxsf shared ~/shared
```

16.  The host folder should now be accessible inside the VM.

```
cd ~/shared
```

## [](https://gist.github.com/estorgio/1d679f962e8209f8a9232f7593683265#make-the-mount-folder-persistent)

## Make the mount folder persistent

This directory mount we just made is temporary and it will disappear on next reboot. To make this permanent, we'll set it so that it will mount our `~/shared` directory on system startup

1.  Edit fstab file in /etc directory

```
sudo nano /etc/fstab
```

2.  Add the following line to fstab (separated by tabs) and press Ctrl+O to Save.

```
shared	/home/<username>/shared	vboxsf	defaults	0	0
```

3.  Edit modules

```
sudo nano /etc/modules
```

4.  Add the following line to `/etc/modules` and save

```
vboxsf
```

5.  Reboot the vm and log-in again

```
shutdown -r now
```

6.  Go to your home directory and check to see if the file is highlighted in green.

```
cd ~
ls
```

If it is then congratulations! You successfully linked the directory within your vm with your host folder.

## [](https://gist.github.com/estorgio/1d679f962e8209f8a9232f7593683265#bonus)

## Bonus:

How to point apache's web directory to our folder in the host.

1.  Remove apache's old `html` directory (WARNING! Backup your data if necessary)

```
sudo rm -rf /var/www/html	
```

2.  Add a symbolic link in its place

```
sudo ln -s ~/shared /var/www/html
```

