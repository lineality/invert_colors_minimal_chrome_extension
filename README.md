### invert_colors_minimal_chrome_extension
## Dark Mode: eye-saving invert colors minimal chrome browser extension

# About Invert-Colors-Minimal

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

I recommend putting the few simple lines of code into your browser manually (making your own extension)
rather than trusting, running, or even downloading anything that might be harmful. 
Maybe what you load from the extension store is not what it says. Maybe
it will be replaced with updated different code at any time.
This is a few lines of code you can easily install yourself manually for an extension you can 100% 
understand and trust. (As far as I undersand...that is the goal.)


# Steps to Deploy Extension Yourself from Code
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


# Design, Plan, and Goal

So far as I understand, as a non-veterin at javascript (which I consider a plague on web-simplicity and security)
and browser-extensions (which I consider I plague on web security),
there are three ways in chrome to effect a dark-mode change of colour
(where light-mode pages destroy people's eyes yet are often still
after so many years a tyranical default. One way of thinking about this may be
that the extension needs to have some way of turning on and knowing what
page or tab or site to apply to. There is also a 4th way, but this is 
effectively impossible for a simpe chrome-extension-store add so far
as I know.
### 1. All Urls
1. <all urls> This is not a "permission" in most uses of the term, but
google considers this a very permissive or potentially insecure way to write
an extension because it can apply to any website. I did try to avoid using this, but the more
I look at different ways an extension can work, and trying them out,
this really seem the best to me for several reasons with only one draw-back for the user.

A. This is the simplest extension I know of, asside from the manifest-file that names and describes the extension
the entire extenion is this one short line, nothing more: "document.body.style.filter = "invert(100%)";"
Asside from no extension at all, I can't think of a simpler, cleaner, not hiding anything,
not doing anything everyone can't understand, not-dangerous, line of code. This inverts the colors 100%, and that is all.

B. Because of how chrome is set up, there are three broswer catagories on top of the extensions all-url vs. active-tab design,
so the user chooses 1. use this all the time (not so useful), 2. use this just right now (very useful), 3. use it for this url (very useful)
So now I do not get white-light flashed every time I go to the same website and need to turn that off: every new doc, every new etc.
(yes, google-office-suite being light mode is a major issue for people with eyeballs)
The only downside, which so far has not been an issue for me in real life, is that it does not toggle on and off at the touch of a button,
you need to turn it off and open a new tab to turn the color-flip off.
But literally the only time I ever wanted to rapidly taggle back and forth was when I was require by google to upload a
demo photo of the app working, which I chose to show a before and after image. In daily use, I don't flash my eyes with strobe toggle.

C. The simplicity of this code makes it very feasible for any user to get the 2, 7, or 12 lines of code (depending on what you consider a 'line')
and make sure it is exactly what they think it is, trust it to be, want it to be, and that they understand running it, 
and upload it directly without needing to download anything from anywhere. To me this is a rare ideal case where
any user can run an extension in a practical way without anything they do not understand, no hidden risk,
no 'permissions' (in most definitions of the term), and no possibly secret changes in downloaded code.
It's less than 10 lines, just type it in or copy past yourself. It doesn't get any better than that.
The extension-store is completely bypassed along with all the risks and downsides. Loading potentially unknown code is completely bypassed.
It is so simple you can write it yourself to do just one single thing: flip the colors on any site you select. Maybe there
is a hidden snag somewhere, but I am confused by any description of this extension as dangerous or permissive compared
to literally any other extension which is doing who-knows-what with expected-to-be-terrible side effects. 

### 2. Active Tab
2. [active tab] Active-tab IS technicaally a permission, which allows the browser to know to act on the tab you are on.
Perhaps in other uses this allows the extension to track active tabs and that is why it is considered a 'dangerous permission.'
Maybe this is useful but I loath 'requesting' any permission that is not absolutely needed, and the code is not
as clean as the super-simple version, and (if ironically) it can NOT be set to always convert the same websites
(so it lets advertisers track you but you can't track your own needs? Great technology.)

### 3. Pop-Up Nightmare 1996 Garbage Yardsale
3. A theoretical 'pop-up' bloat-fest nightmare that I have never seen actually work in chrome is option 3. (
(I say 'in chrome' because a firefox invert app that actaully links to github code, a mad laberyth of code and directories,
may use this...but good luck understanding that spawling birds-nest of code that is supposed to do only one simple thing.
To my mind this is a case study in what a problem looks like, where you have endless dodgy technologies and tests and features and tricks and popups and permissions and on and on and on in ever-expanding code, to simply replace this one very simple very short single line, single command: "document.body.style.filter = "invert(100%)";" And "popups"...really?
This is like offering to give someone a horrible disease. Just no. No popups. NO. Bad idea. Bad dog.

### 4. Hard Coded Site List
4. instead of all-urs, make a list which urls, which sites, you want to apply this extension to. This migth be good for some users who don't mind and have the time to manually hard code script into archiving versioning and re-installing their new dev-code into their active browers on the fly as they go to different websites...but even that is 'insecure' in some ways of thinking,
and it surely is cumbersome. But for some institutions or use-cases, maybe it makes sense. It is a possible option (I think).
Maybe you could create a giant office-suite of software living in the extension that allows users to write in their site list...but that is not simplicty with security either.


### Many catagories of "permissions" (with a goal of zero-permissions)

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

#### A minimal toggling firefox extension/add-on (to color invert for dark mode) that I wrote, which uses the active-tab approach.
```
https://github.com/lineality/invert_colors_minimal_firefox_addon
```


This is a firefox extension (not by me) that at least shows
code...if that is really what is running, who knows.
```
https://github.com/Max-Github/FireFoxInvertColors
```
