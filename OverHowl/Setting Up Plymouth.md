`$ sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /lib/plymouth/themes/Anonymous/Anonymous.plymouth 500`

`$ sudo update-alternatives --config default.plymouth` 

`$ sudo update-initramfs -u`


> install plymouth
> install plymouth-themes
> install firmware-linux

Plymouth-preview

````
#!/bin/bash

check\_root () {

  if \[ ! $(id -u) \-eq 0 \]; then

    echo "Please run as root"

    exit

  fi

}

check\_root

DURATION\=$1

if \[ $# \-ne 1 \];

then

  DURATION\=5

fi

plymouthd; plymouth \--show-splash

for ((i\=0; i<$DURATION; i++)); do

  plymouth \--update\=duration$i;

  sleep 1;

done;

plymouth \--quit
````

> sudo cp -r <theme-name> /usr/share/plymouth/themes/
> plymouth-set-default-theme --help
> plymouth-set-default-theme -R <theme name>