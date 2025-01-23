---
layout: post
published: true
title: 'Apple Shortcut to DFU restore a Mac'
---

Hi there. Long time, no blog.

I've got a lot to share about what I've been up to, but I wanted to share something simple for now. In my current role I am using Erase All Content & Settings or DFU'ing a Mac a lot. Like, **A LOT**. I can spend my morning testing a deployment going to 1:1 Macs, where I'll reset a Mac three or four times. Then in my afternoon I find myself testing app behavior on a shared Mac persona, and comparing the behavior on different macOS versions. There's lots of bongs and a few ["macOS contains.."](https://www.bonfire.com/store/macadmfound/)

All this is to say, I'm always running [DFU Blaster Pro](https://twocanoes.com/products/mac/dfu-blaster/) and Apple Configurator 2. The thing is, what I'm doing is pretty simple and repetitive. DFU Blaster Pro is great and I can DFU a Mac in a few seconds.. but if I can do it faster, why not? (Honestly, it's Apple Configurator 2 that is a little tedious)

I discovered the command line utility macvdmtool kind of randomly on [Kyle Ericson's GitHub](https://github.com/kylejericson/DFU_Tool). He's made an installer for it but you can also download and build macvdmtool from the [AsahiLinux GitHub](https://github.com/AsahiLinux/macvdmtool). Using it and [Apple Configurator 2's cfgutil](https://it-training.apple.com/tutorials/deployment/dm095/), I have an Apple Shortcut to DFU a Mac and restore an IPSW I've already downloaded.

![]({{site.baseurl}}/img/dfu-shortcut.png)

The rest of the shortcuts listed are a topic for another post.

Here's the Apple Shortcut configuration. From my testing I've found that macvdmtool's step has to be run with `sudo` and also with Run as Administrator enabled.

![]({{site.baseurl}}/img/dfu-shortcut-howto.png)

You can modify this shortcut to download and restore the latest macOS by omitting `-I` and the file path. I have to admit I'm ridiculously late to the Apple Shortcuts game, so I'm open for any ideas. I can picture an Apple Shortcut with a file picker so you can choose the IPSW to restore.

If you have any feedback you can find me [on Mastodon](https://irrelephant.co/@adamcodega) and [MacAdmins Slack](https://www.macadmins.org/). Happy DFU'ing.

Next blog post, we'll be taking a look at [Jamf's Self Service+](https://learn.jamf.com/en-US/bundle/self-service-plus-documentation/page/About_Self_Service_Plus.html) which is available to customers as of this week.
