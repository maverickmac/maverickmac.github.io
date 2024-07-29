---
layout: post
title:  "Set Exact Brightness Level Across Mac"
author: "MaverickMac"
comments: true
tags: brightness command-line
excerpt_separator: <!--more-->
---


Even though Mac has granular brightness control with **⌥ + ⇧ + F1/F2** (Brightness control in Air M1), it still difficult to set exact brightness across dual boot or even across different mac.
<!--more-->


The solution is to get brightness level in numerical format. And [Brightness](https://github.com/nriley/brightness) exactly does that. While app like [Lunar ](https://lunar.fyi/)has a command line utility, Brightness is free & open source. 


<img src="/assets/images/Brightness-Working-on-M1.png" style="float: left;width:60%;margin-right: 10px">



Install it with homebrew: `brew install brightness`

💡 However development has stopped for a while, and you have to compile it for apple silicon. 

📦 Download a precompiled version from [here](https://files.catbox.moe/wzwsdq.zip). And copy the binary over `sudo cp ~/Downloads/brightness /opt/homebrew/bin/`


{:style="clear: left"}



To get the current brightness level, 

```sh
brightness -l
```

Set it with (Change the value accordingly)

```sh
brightness 0.459100
```

