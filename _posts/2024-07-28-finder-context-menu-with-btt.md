---
layout: post
title:  "New-File & Open-in-Terminal context menu with BetterTouchTool"
author: "MaverickMac"
comments: true
tags: brightness command-line
excerpt_separator: <!--more-->
---


Previously many small applications tried to provide essential *Finder* context menus such **New File** & **Open-in-Terminal**. These are,
<!--more-->

[Custom-Finder-Right-Click-Menu](https://github.com/samiyuru/custom-finder-right-click-menu)

[FinderPlus-macOS](https://github.com/kotleni/FinderPlus-macOS)

[Context-menu](https://langui.net/context-menu/) (may not work now)

[SzContext](https://github.com/RoadToDream/SzContext)




<img src="/assets/images/Finder-Context-menu-with-BTT.png" style="float: left;width:30%;margin-right: 10px">

Most of them either do not work with latest mac, or requires compiling for apple silicon. 

However now, starting with **BetterTouchTool v4.560** you can extend the [Finder context menu](https://docs.folivora.ai/docs/6b_finder_context_menu.html) with custom menu items very easily. You can even add monochrome system icons.

{:style="clear: left"}

---

**New-File:**

The setup is done in the "Automations & Named & Other Triggers" section in BTT by adding a "Custom Finder Context Menu Items" trigger and assigning the Configure Custom Conntext Menu Items" action.



![finder_context_1](https://docs.folivora.ai/docs/media/finder_context_1.png)

When context menu item is triggered, BTT will make these variables available that can be used e.g. in terminal commands or scripts:
* **BTTFinderContextMenuTargetPath** (the path of the current folder)
* **BTTFinderContextMenuSelectedItemPaths** (the paths of the selected items, separated by ;; )

We will take advantage of that with simple one line bash script to create multiple new file like in Gnome Nautilus.


{% highlight bash linenos %}
filePath="{BTTFinderContextMenuTargetPath}/untitled";fileNo=1;while [ -f "${filePath}" ];do filePath="{BTTFinderContextMenuTargetPath}/untitled${fileNo}";fileNo=$((fileNo+1));done;touch "${filePath}"
{% endhighlight %}

<img src="/assets/images/BTT-Finder-context-menu-new-file.png">

---

**Open-in-Terminal:**

<img src="/assets/images/BTT-Finder-context-menu-open-in-terminal.png" style="background-image: none;">


Open in Terminal is as simple as selecting "Open selected/Active folder with specific app" and then choosing default terminal app.




