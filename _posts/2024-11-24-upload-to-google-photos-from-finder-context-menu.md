---
layout: post
title: Upload To Google Photos From Finder Context Menu [Mac]
author: "MaverickMac"
comments: true
categories: [Mac, Tutorial]
tags: mac bash finder shortcuts automator context-menu photos
excerpt_separator: <!--more-->
---


[Dropover](https://dropoverapp.com) is a popular Mac app that simplifies dragging and dropping files. But it also integrates with cloud services like iCloud, Dropbox, Imgur, and making it easy to upload with just right click. One can even add custom scripts which means we can upload custom services like [Google Photos](photos.google.com).
That script can also be used as *Quick Action* in Finder context menu.
<!--more--> 

![Upload To Google Photos From Finder Context Menu](https://cdn.edc0.com/logbook/images/finder-Context-menu-upload-to-gphotos.jpeg)

However here we will create a simple
Finder context menu using *Shortcuts app*, *bash script*, and *rclone*.


### Setup Rclone

Install `rclone` using Homebrew:

```bash
brew install rclone

# Then setup rclone
rclone config

# Choose n for a new remote.
# Name the remote (e.g., GPhotos).
# Select 15 for Google Photos.
# Follow the prompts to authenticate with your Google account.
# Once authorized, rclone will save your configuration.
```

> Rclone can only upload photos to album it creates. If you want existing album (created by some other API method) then replace access_token & refresh_token with previously generated tokens in ~/.rclone/rclone.conf
{: .prompt-tip }

### Create context menu using Ahortcuts App and a Simple Bash script

```md
- Click the "+" button in the top-right corner to create a new shortcut.

- Click on the `{i}` button. Select "Use as Quick Action". Select Finder.

- It will add a receive section (as shown in the picture below)

- In it, only select "images". Type = "images". Select Multiple = ✔️

- Add List. List contains albums names. Modify it accordingly.

- Add "Choose from List". It will ask user to select an album.
```

![Shortcuts-Upload-To-Gphotos-Steps](https://cdn.edc0.com/logbook/images/Shortcuts-Upload-To-Gphotos-Steps.png)

### Add "Run Shell Script" Action

```md
- In the search bar on the right, search for "Run Shell Script" and drag it into the shortcut editor.

- Shell: Choose /bin/zsh (or another shell you prefer).

- Pass Input: Select As arguments.

- Enter the script you want to execute.

- In the album_name=, right click-> Select variable->Choosen item
```

<iframe frameborder="0" scrolling="no" style="width:100%; height:373px;" allow="clipboard-write" src="https://gist.edc0.com/iframe.html?target=https%3A%2F%2Fgithub.com%2Fedczero%2Fsnippets.edc0.com%2Fblob%2Fmaster%2Fdata%2Flogbook%2F2024-11-24-upload-to-google-photos-from-finder-context-menu%2FUpload-To-Gphotos.sh&style=base16%2Fhopscotch&type=code&showBorder=on&showLineNumbers=on&showFileMeta=on&showFullPath=on&showCopy=on"></iframe>








