---
title: 'Quick tip: Compare folders in Mac OS X'
author: Adam Codega
layout: post
permalink: /2014/02/quick-tip-compare-folders-mac-os-x/
dsq_thread_id:
  - 2247144098
categories:
  - on the job
  - quick tip
---
Recently I&#8217;ve decided to move from [Dropbox][1] to [Box][2]. The free storage that Dropbox comes with isn&#8217;t enough for me and I don&#8217;t use a lot of their special features to make it worth keeping them. I simply keep all my files in one folder on my laptop and have it synced to Dropbox, where I have it installed on my basement file server. (I also backup the file server with [Crashplan][3])

Also, as it turns out [Box is running a promo right now][4]. If you install their iOS app after creating an account your free storage space will be expanded from 10 GB to 50 GB.

So anyway.. the main point of this blog post. Switching was easy. I installed Box on my laptop and simply copy and pasted my Dropbox contents into the new Box folder. But then I got busy that afternoon and continued working on a few things in my Dropbox folder. Now I had to compare the two folders since I had worked on projects across a few different folders. I always used [WinMerge][5] and liked it on Windows computers. It has a nice GUI where it shows the two folder contents side by side and any files that don&#8217;t exist in both places, or who&#8217;s contents are different, are highlighted in red. I could use [DiffMerge for OS X][6] but only a few changes had been made so all I needed was the **diff** command from the terminal.

<pre><strong>adam:~ adam$ diff -rq Dropbox "Box Sync"</strong>
Files Dropbox/.DS_Store and Box Sync/.DS_Store differ
Only in Dropbox: .dropbox.cache
Only in Box Sync: Engagement Disc
Only in Box Sync: Honeymoon Disc
Files Dropbox/Loop By Loop/mailing.txt and Box Sync/Loop By Loop/mailing.txt differ
Only in Dropbox/Loop By Loop/2x2_stamp: 2x2_stamp rounded.pxm
Only in Dropbox/Loop By Loop/2x2_stamp: 2x2_stamp_postal-seperate.idraw
Only in Dropbox/Loop By Loop/2x2_stamp: 2x2_stamp_postal-seperate.png
Only in Dropbox/Loop By Loop/2x2_stamp: 2x2_stamp_postal.idraw
Only in Dropbox/Loop By Loop/business cards: sheep.png
Only in Box Sync: Pixelmator brushes
Only in Box Sync: The-Secret-Weapon-Manifesto.pdf
Only in Box Sync: Wedding Disc
Only in Dropbox: codega-email.jpg
Only in Dropbox: codega.png
Only in Dropbox: holidays off.rtf
Only in Box Sync: passwords-suck.png
adam:~ adam$</pre>

&nbsp;

With a small list of files that were different/only existed in Dropbox I went ahead and made my changes.  You can also see that since the folder &#8220;Box Sync&#8221; had a space in it&#8217;s name I enclosed it in quotes. I used two options, r makes diff also go into subfolders as well and q will provide me a brief summary of differences, helpful when comparing a lot of folders and files. Check out the other diff options [over at Commands.com][7].

 [1]: http://www.dropbox.com
 [2]: http://www.box.net
 [3]: http://www.code42.com/crashplan/
 [4]: https://blog.box.com/2014/01/get-the-all-new-box-for-iphone-and-ipad-50gb-free/
 [5]: http://winmerge.org/about/screenshots/
 [6]: http://www.sourcegear.com/diffmerge/
 [7]: http://mac.commands.com/diff/