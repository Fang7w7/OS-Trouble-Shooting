Desktop environments can interfere with each other or change system-wide settings. Issues with a desktop environment’s appearance can generally be fixed by changing the theme in the Appearance control panel.

#### Customize Notification Dialog

Xfce will change the notification dialog to its own. It can be configured with this command:

```
xfce4-notifyd-config
```


#### Remove Duplicate Options From Login Screen

Some desktop environments provide more than one session. For example, Cinnamon provides both a 2D and a 3D session. The options available at login are located in the `/usr/share/xessions` directory, and unneeded options can be removed by deleting the corresponding files. For example, to remove Cinnamon’s extra option:

```
sudo rm /usr/share/xsessions/cinnamon2d.desktop
```


#### Double Lock Screen Passwords

GNOME does not use a screensaver (only a lock screen), but other desktop environments may install the classic GNOME screensaver package as a dependency. If you’re being prompted for a password twice after suspending or locking the screen, disable the second prompt with this command:

```
gsettings set org.gnome.desktop.screensaver lock-enabled false
```

Or, if that doesn’t stop the second prompt, uninstall the redundant screensaver with this command:

```
sudo apt purge gnome-screensaver
```

#### Enable Cinnamon Lock Screen

If Cinnamon’s desktop lock screen isn’t functioning, this command will re-enable it:

```
gsettings set org.cinnamon.desktop.lockdown disable-lock-screen false
```

#### Removing Desktop Environments

If you no longer want to use a desktop environment, it can be removed by using:

```
sudo apt autoremove --purge ...
```

For example, to remove KDE:

```
sudo apt autoremove --purge kde-standard
```