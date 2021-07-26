**###Custom Launcher**

1. To add the program to your main menu, we need to create a .desktop file in 

```~/usr/local/share/applications```

2. Using terminal run

```sudo gedit /usr/local/share/applications/Teamspeak.desktop```

3. and paste in the following into gedit. (Substitute with your program values accordingly)

````
[Desktop Entry]
Encoding=UTF-8
Exec=~/Software/teamspeak/ts3client_runscript.sh
Name=Teamspeak3
GenericName=Teamspeak
Type=Application
Terminal=false
StartupNotify=false
Type=Application
Icon=~/Software/teamspeak/icon.png
Categories=Game
````

Common category values include: AudioVideo, Development, Education, Game, Graphics, Network, Office, Settings, System, Utility

Heads up, I downloaded my own icon for the desktop entry and placed it in the installed folder.

Mark the teamspeak.desktop file as executable using the terminal command (Might not be necessary)

```$ chmod +x /usr/local/share/applications/Teamspeak.desktop```

Restart your system and you should find a your program added to your main menu in the category you defined.