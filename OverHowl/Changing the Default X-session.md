**###CHANGING THE DEFAULT X-SESSION TO YOUR NEWLY INSTALLED DESKTOP ENVIRONMENT**

1.  Navigate to the `/usr/share/xsessions` directory where you can find .desktop files for each of the available sessions. Consult the contents of the .desktop files to determine the session you want to use.
    
2.  To specify a default session for a user, update the user’s account service in the `/var/lib/AccountsService/users/username`  file:
   
````
[User]
Language=
XSession=gnome-classic #Desktop Environment Name from /usr/share/xsessions/
 
 ````
    

After specifying a default session for the user, that session will be used the next time the user logs in, unless the user selects a different session from the login screen.

You also have to change the settings of the window manager if your using Light-dm Window manager then change the settings `/usr/share/xsessions/lightdm-xsession.desktop`

````
[Desktop Entry]
Version=1.0
Name=Default Xsession
Exec=startxfce4 ##change this to the desktop environment you are using
Icon=
Type=Application
````
