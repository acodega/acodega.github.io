---
title: 'Quick tip: easy Windows local administrator login'
author: Adam Codega
layout: post
permalink: /2012/06/quick-tip-easy-windows-local-administrator-login/
dsq_thread_id:
  - 724354980
categories:
  - quick tip
tags:
  - active directory
  - microsoft
  - quick tip
  - windows 7
---
Here&#8217;s a quick tip for those of you who work in a Windows domain environment.

Like most people when I troubleshoot Windows workstations on a domain I often have to log in as local administrator. This means I have to type in the administrator username as **[name of computer]\administrator**.

Now it&#8217;s easy to get the hang of computer names in your office but often times I forget. (Sometimes that&#8217;s a good thing because it means I haven&#8217;t worked on that particular computer in awhile.) I will then have to click on &#8220;How do I log on to another domain?&#8221; where I&#8217;ll be shown the computer&#8217;s name.

Even if you know the name of the computer, there&#8217;s a convenient trick in Windows 7 and Windows Server 2008. (Technically Vista too but who cares?) At the login screen, type **.\** followed by the local username (for example, **.\administrator**) and the name of that particular computer will be filled in for you.

Quick tips like these are endless in supply.. if you know of a good one leave it in the comments!