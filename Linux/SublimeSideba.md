You will need to edit the `.sublime-theme` file to do this. Unfortunately, in Sublime Text 3 this file is contained in a zipped `.sublime-package` file, so you'll need to extract that first. Install the [`PackageResourceViewer`](https://sublime.wbond.net/packages/PackageResourceViewer) plugin via Package Control, then hit ⌘ShiftP and type **_`prv`_** to bring up the PackageResourceViewer options. Select `Open Resource`, scroll down to `Theme - Default`, hit Enter, scroll down to `Default.sublime-theme`, and hit Enter again to open it.

Next, search for **`sidebar_label`** and modify the first one (on line 362) to look like this (it needs to be valid JSON):

```javascript
{
    "class": "sidebar_label",
    "color": [0, 0, 0],
    "font.bold": false,
    "font.italic": false, // <-- add comma
    "font.size": 14 // <-- new line
    // , "shadow_color": [250, 250, 250], "shadow_offset": [0, 0]
},
```

Save the file, and you should see the sidebar font size change. You can change `14` to whatever size you want, depending on your personal preferences.


## Installation

Note with either method, you may need to restart Sublime Text for the plugin to load properly.

### Package Control

Installation through [package control](http://wbond.net/sublime_packages/package_control) is recommended. It will handle updating your packages as they become available. To install, do the following.

-   In the Command Palette, enter `Package Control: Install Package`
-   Search for `PackageResourceViewer`