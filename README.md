### invert_colors_minimal_chrome_extension
## Dark Mode: eye-saving invert colors minimal chrome browser extension

# About Invert Colors Minimal

## Description
With security, transparency, and data-hygiene in mind: 
This is a minimal chrome extension to invert colors in a browser tab
(e.g. to reduce eye-strain by turning inscrutably white pages black)
that you can manually deploy in your browser, so that you know
exactly what code you are running. Black-Box extensions in the 
extension-store may be safe to use, but it is very difficult for an average
user to test this.
This requires no permissions. If the version you have tries to get any
permissions, please stop and figure out what is going on, check the code,
check default settings (which may be outside of the extension itself).

A trade-off of the extreme minimalism, is that the extension does not toggle
or reset if you refresh the tab. You will need to open a new tab to turn 
the extension (color reversal) off. 
 
# Steps to Deploy Extension
1. Create a new directory(folder) and put these two files in it:
- manifest.json
- invert_color_minimal_chrome_content.js  

Note: The "invert_color_minimal_chrome_content.js" file should be just one line of code:
```
document.body.style.filter = "invert(100%)";
```

2. Open/Go to chrome://extensions/ in your Chrome browser.
3. Turn on "Developer mode" at the top right.
4. Click "Load unpacked" and select your directory.
- A puzzle-piece icon should appear to the right of your URL-address bar. 
5. Click the puzzle-piece icon that should be to the right of your URL-address bar to see a drop-down menu of extensions.
6. "Invert Colors Minimal" should appear in that list. Click "Invert Colors Minimal" to invert to dark-mode.

# Permissions:
This extension does not need ANY permissions.

Go to: extensions puzzle-piece icon -> minimal_color_invert extension ->  
-> three vertical dots ->  "View web permissions" -> 

The url will look something like this:
```
chrome://settings/content/siteDetails?site=chrome-extension%blahblahblah
```

### This page should show permissions for this extension for all sites:

For reasons beyond my imagination, google pre-sets permissions
very openly. So you need to MANUALLY set everything to block or mute.
So far as I know there is no way for an extension developer to
turn off these permissions, which is terrible. 

Set everything to block or mute. Again, this minimal invert-colors 
extension does not need any permissions.

# Settings: 
Go to: extensions puzzle-piece icon -> minimal_color_invert extension ->  
-> three vertical dots ->  "This can read and change site data" -> 

Seemingly randomly on each browser instance, the default here may be different.
Sometimes this is default set to: 
- When you click the extension
- On _____ (this site)
- On all sites

So you will likely need to adjust this.

If you know you will always use this for a given white-background site,
you may opt to select the 2nd: On (this site) choice, which will not 
affect colors on other sites.


# For Firefox:
This is a firefox extension (not by me) that at least shows
code...if that is really what is running, who knows.
```
https://github.com/Max-Github/FireFoxInvertColors
```
