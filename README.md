# What is Obsidian?

[Obsidian](https://obsidian.md/) is really cool and free note-taking app that wants to be your second brain. To learn more about it, check out my [Obsidian overview](https://medium.com/swlh/take-better-notes-with-this-free-note-taking-app-that-wants-to-be-your-second-brain-1a97909a677b) and [how I use it to take notes](https://medium.com/swlh/how-to-take-notes-insights-from-ai-neuroscience-a-sociologist-and-a-free-app-34b4be63080a) (and [why we take notes](https://medium.com/swlh/why-take-notes-3-common-misconceptions-and-3-better-mindsets-447ef6853aa9)).

# Alfred workflow for Obsidian

This simple [Alfred](https://www.alfredapp.com/) workflow uses [Obsidian](https://obsidian.md/)'s [URI scheme](https://publish.obsidian.md/help/Advanced+use/Using+obsidian+URI) (available in version 0.8.15 and above) and JXA actions/scripts (thanks to [@hjklapp](https://github.com/hjklapp)) to open notes in their vaults. This workflow has been tested in Obsidian 0.9.7.

Available Alfred features/keywords: `ov`, `od`, `oo`, `os`, `or`, `ot`

## Features that work out-of-the-box

### Open a vault: `ov`

To open one of your many Obsidian vaults, type `ov your_vault_name`. You can change the keyword input subtext to remind yourself of the names of your vaults. Double-click **ov Keyword** to change the Subtext field.

## Features that require some (simple) setting up

### Open a vault with autocomplete: `oo`

To autofill and autocomplete Obsidian vaults: Type `oo your_vault_name`. 
- Double-click **oo List Filter** to add all your vaults. See screenshots below.
- This feature is suggested by [@hjklapp](https://github.com/hjklapp).

![](img/oo.gif)
![](img/oo.png)

### Open daily note: `od`

- The Daily notes Obsidian plugin must be enabled.
- Type `od`  or use a hotkey (double-click the empty Hotkey to set it up). Your daily note must already exist, otherwise you'll get "File not found message." (see [issue](https://github.com/hauselin/obsidian-alfred/issues/6)).
- Notes and comments are provided in the workflow/script to help you set things up. Double-click the **/usr/bin/osascript Run Script** associated with **od Keyword** to set it up. You need to specify your daily note date format (step 1 in script) and the vault name (step 2 in script). Click Save when you're done.
    - New in v0.1.3: Easily specify your date format in the /usr/bin/osacript by using yyyy, mm, dd. See screenshot below.

![](img/odaily.png)

### Search Obsidian vaults with Alfred File Filters; `os`, `or`, `ot`

You'll have to edit the Scope of each File Filter to tell Alfred where to search for files on your computer. Double-click **os File Filter**, **or File Filter**, and **ot File Filter**. You can also change other settings via Basic Setup, Scope, Fields, Limit and Sort tabs.

- Search for all files with the term `xyz`, type `os xyz`.
- Search for recent files (last 3 days) with the term `xyz`, type `or xyz`.
- Search for files modified today, `xyz`, type `ot xyz`.

![](img/or.gif)

**Other features**

If you want to copy the path to a file instead of opening it in Obsidian, check out @ldebritto's [fork](https://github.com/ldebritto/obsidian-alfred). 

## Known bugs

If the Obsidian app isn't already opened, this workflow will always open the last recently opened vault. This bug is a known issue with Electron apps on MacOS. See [discussion on Obsidian's Discord](https://discordapp.com/channels/686053708261228577/716028884885307432/755203478413902036).