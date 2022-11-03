---
layout: post
published: true
title: 'Not How, but Why: Microsoft Office 365 for Mac'
---
On January 24th, after a few delays leaving us on the edge of our seats, Microsoft delivered on its WWDC 2018 promise and [Microsoft Office 365 arrived in the Mac App Store](https://itunes.apple.com/us/app-bundle/microsoft-office-365/id1450038993?mt=12). [Daz Wallace](https://dazwallace.wordpress.com/2019/01/30/migrating-microsoft-office-suite-to-mas-deployment/) and [Ben Toms](https://macmule.com/2019/01/26/deploying-microsoft-office-from-the-mac-app-store/) have great blog posts already online. Also, Microsoft has already updated their [Deployment guide for Office for Mac](https://docs.microsoft.com/en-us/deployoffice/mac/deployment-guide-for-office-for-mac), a great resource by itself.

Microsoft calls the traditionally deployed Office apps their "Microsoft CDN" version, versus the new App Store version. 

Based on some of the conversations in #microsoft-office on [MacAdmins.org](http://macadmins.org), it's important to ask "Not how, but why?" in evaluating whether this will change how you deploy Office for Mac in your environment. Of course this is by no means an argument for or against App Store deployment. There's pros and cons to both options.

## Do I need it?
Firstly, if you're using a volume license of Office 2019, it is not compatible with the App Store version. Traditionally, I would not call Office for Mac hard to deploy or manage. Especially since 2016 was released, the pkgs are easy to automate the deployment of and Microsoft AutoUpdate can be used from the command line/scripts. That being said, of course this could be one less App to have in your repo. Microsoft Teams and Skype for Business will be lonely in your repo though, as they aren't available in the App Store. (Yet?) As for management, the App Store apps are virtually as configurable with configuration profiles as the CDN versions. (And is it ever configurable.. 124 preferences last I looked.)

I say almost because the CDN version of the OneDrive app can be pre-configured while the App Store app must be manually configured.

## How do I roll it out?
App Store apps are traditionally distributed with an MDM (like [SimpleMDM](https://simplemdm.com/), [Mosyle](https://mosyle.com/), or others) connected with your [Apple Business Program account](https://help.apple.com/deployment/macos/#/iorb94d350b2). Distribution this way is a little ambiguous, knowing how soon an app will install or update and troubleshooting issues when they arise is not like scheduling an install and reading the logs. We'll also have to wait and see how soon the App Store updates are available compared to their CDN siblings. Microsoft does not plan to have any delay but it's been common in other apps with App Store twins that they release their CDN version while waiting for Apple to approve their App Store version. In order to migrate from CDN to App Store, you will also need to remove the CDN version first. This includes removing the apps, Office entries in the keychain, preference files, and pkg installation receipts. Lastly, sit and wait until the App Store apps gets installed. It will probably be quick. It's sort of.. ambiguous.

While you can set up a [caching service using Microsoft AutoUpdate](https://macadmins.software/docs/MAU_CachingServer.pdf), you can also cache App Store apps using [macOS's built in caching features](https://support.apple.com/guide/mac-help/about-content-caching-on-mac-mchl9388ba1b/mac).

## What's the inside scoop?
Deploying Office is more than just access to email and some files. Microsoft is consistently adding features to connect the desktop apps to Office 365 services and improve your work and collaboration. Since updates in apps can change and improve how people work, you might benefit from allowing early access to new features. This could be a limited scope of people or as an opt-in choice for your [Office 365 Champions](https://www.microsoft.com/en-us/microsoft-365/success/champions). Microsoft makes their [Insider Program](https://insider.office.com/en-us/) available in two ways, Insider Fast and Insider Slow. Insider Slow is the second group to get the latest update before a production release and implies less risk. Users can either opt-in through the Microsoft AutoUpdate app, or IT can set Microsoft AutoUpdate to use a certain Insider track.

With that in mind, Office for Mac from the App Store doesn't allow a choice, and is the same as the non Insider CDN release of Office.

Whether you choose CDN or App Store distribution, your organization should have a story around how you stay informed and knowledgeable on Office 365 improvements. Along with the Champions program and the Insider tracks, IT can also follow feature rollouts and planned changes with the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap). (Speaking of which, Microsoft just added [Files On-Demand to Mac](https://support.office.com/en-us/article/learn-about-onedrive-files-on-demand-0e6860d3-d9f3-4971-b321-7092438fb38e) this month!)

Make sure to bookmark [macadmins.software](https://macadmins.software/) where you can easily get the latest Office apps, deployment and config profile information, and other helpful resources. Of course, don't forget to join #microsoft-office on the [MacAdmins.org Slack Team](http://macadmins.org).
