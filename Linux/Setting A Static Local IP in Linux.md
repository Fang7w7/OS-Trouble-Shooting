check the default gateway in Windows Host

1. Then Open terminal and type -

`$ ifconfig eth0/wlan0 192.168.1.123 netmask 255.255.255.0`

2. check the default gatway in in terminal

`$ route -n`

3. now set the default gateway that you have found in windows host

`$ route add default gw 192.168.1.129 eth0/wlan0`

now do the manual setting in network settings in linux and set the automatic ip assignment as manual.

Another Method is -

1. Go to `/etc/network`
2. now add the following lines in the `interfaces`  files

````
auto eth0/wlan0
iface eth0/wlan0 inet static
address 192.168.1.123
netmask 255.255.255.0
gateway 192.168.1.129

````

now save the file and reboot your system.