---
layout: post
title:  "Found Meld Native Build (M1/M2)"
author: "MaverickMac"
comments: true
tags: native-build meld
excerpt_separator: <!--more-->
---





I was looking for a simple but native diff tool for comparing files, codes and folders. While there are many alternatives like *Beyond Compare* or *Kaleidoscope*, there are either not native, ugly or very expensive.

<!--more-->

On linux there is Meld for comparing files, which is available only through MacPorts, until now. 

I found **[Meld for OSX](https://yousseb.github.io/meld/)** which is offering a dmg for intel mac. 

It has recently received a native Apple Silicon build, as detailed in this ~[GitHub pull request](https://github.com/yousseb/meld/pull/148)~. This update brings significant improvements for users on M1 and M2 Macs.

📦 Downloads: [Meld-Native-Apple-Silicon](https://files.catbox.moe/t4eqer.dmg) [Alternate-Link](https://uofi.box.com/s/o2ci9nk9qit9jatv3pzjv3dybbp94dqr)

After downloading it, quarantine with,

```sh
xattr -c /Applications/Meld.app
```

<img src="/assets/images/Meld-UI-Full.png" width="50%" align="left" class="inline"/>

![Meld-UI](/assets/images/Meld-Comp-Full.png){: width="50%"}

💡 If your hombrew is not in standard path, you may need to reinstall pango and  brotli. Check for more info on that [github page](https://github.com/yousseb/meld/pull/148).



```sh
brew install pango brotli
```


This native build brings improvements such as,
* **Performance Boost**: The native build for Apple Silicon ensures optimal performance and efficiency on M1 and M2 Macs, leveraging the full potential of the hardware.
* **Improved Stability**: Users can expect a more stable and responsive experience, with reduced compatibility issues compared to running the Intel version via Rosetta 2.

Hopefully this native build soon available on their website. 
