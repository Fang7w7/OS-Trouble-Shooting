>>
`$ sudo useradd -s /path/to/shell -d /home/{dirname} -m -G {secondary-group} {username}  
$ sudo passwd {username}`  
Let us create a new user named vivek using the useradd command on Ubuntu:  
`$ sudo useradd -s /bin/bash -d /home/vivek/ -m -G sudo vivek  
$ sudo passwd vivek`  
Where,

-   **-s /bin/bash** – Set /bin/bash as login shell of the new account
-   **-d /home/vivek/** – Set /home/vivek/ as home directory of the new Ubuntu account
-   **-m** – Create the user’s home directory
-   **-G sudo** – Make sure vivek user can sudo i.e. give admin access to the new account

##giving an existing user a shell 

`usermod --shell /bin/bash <username>`