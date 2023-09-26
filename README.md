### invert_colors_minimal_chrome_extension
## Dark Mode: eye-saving invert colors minimal chrome browser extension

# About Invert Colors Minimal

## Description
With security, transparency, and data-hygiene in mind. 
This is a minimal chrome extension to invert colors in a browser tab,
e.g. to reduce eye-strain by turning inscrutably white pages black.
This requires no permissions. If the version you have tries to get any
permissions, please stop and figure out what is going on, check the code,
check default settings (which may be outside of the extension itself).

A trade-off of the extreme minimalism, is that the extension does not toggle
or reset if you refresh the tab. You will need to open a new tab to turn 
the extension off. 
 
# Steps to Deploy Extension
1. Create a new directory(folder) and put these files in it:
- manifest.json
- invert_color_minimal_chrome_content.js  

2. Open chrome://extensions/ in your Chrome browser.
3. Turn on "Developer mode" at the top right.
4. Click "Load unpacked" and select your directory.
- An icon should appear near your address bar. 
5. Click the icon that appeared and it should invert the colors on the current page.

# Permissions:
extensions -> this minima_color_invert extension ->  
-> three vertical dots ->  "View web permissions" -> 

These will be permissions for this extension for all sites.
For reasons beyond my imagination, google presets permissions
very openly. So you need to MANUALLY set everything to block or mute.
So far as I know there is no way for an extension developer to
turn off these permissions, which is terrible. 
