---
layout: post
title: How I do photo backups in 2021
star: false
---

If you're anything like me, you prefer to have complete control over your photo library files. But backing up those files on a rolling, ongoing basis has long been a pretty disjointed and painful process. How do you get photos and videos off your phone on a regular basis, keep local copies, and upload them to the cloud without using a proprietary app or service?

Every combination of software I've tried in the past hasn't quite worked as smoothly as I’d hoped. But — famous last words — I may have landed on a decent solution!

For those of you who firmly believe that iCloud Photos, Google Photos, Google Drive, or Dropbox meets your backup needs, then this post is not for you (and that's OK).

But for some folks there are many good reasons that those services might not be a good fit — you don't want to pay the tech giants even more money, you don't trust them with your most treasured data, you have privacy concerns, they don't offer enough storage, you don't want to be at the whim of their pricing changes, you have concerns about the longevity of the company or service, you don't want to lock into a specific app/platform, there's no good way to restore your data, or any number of other reasons. For me it's all of the above.

So after much experimentation and research I rolled this simple solution.

It's cross platform (Android, iOS, Mac, Windows), doesn't require a ton of additional expensive hardware or software (though you do need enough local storage capacity to hold your files), its monthly service fees are as cheap or cheaper than the major services (and doesn't feed the tech giants), and doesn't require me to do anything with the command line (I get enough of that during work hours).

## Required hardware
A "server" — any computer running MacOS or Windows. Very little horsepower required.

## Required software

* [The PhotoSync server](https://www.photosync-app.com) (free)
* The PhotoSync [Android](https://play.google.com/store/apps/details?id=com.touchbyte.photosync) or [iOS](https://apps.apple.com/us/app/photosync-transfer-photos/id415850124?mt=8&ign-mpt=uo%3D4) client ($6.50 a year)
* Cloud backup software of your choice for your server — I use [Arq](https://www.arqbackup.com) and can recommend it, but there are many choices out there.

## Optional hardware
A boatload of storage connected to your server since you will be keeping a local copy of all your files.

## Setup
I'm not going to run through the whole process step by step and rob you of that fun. But the basic gist is:

* Install everything.
* Pick a disk location on your server (or external drive) and point the PhotoSync server app to that directory
* Setup your PhotoSync Android or iOS client with a connection to your server. It should auto detect the server or you can directly hook to an IP.
* Setup an automatic job on your PhotoSync Android or iOS client to sync on whatever schedule you want. I have mine setup to transfer each night while I'm asleep, then delete those files from my phone.
    Setup a schedule on your cloud backup software to back up those local photo/video files.

That's it! Those are just the broad strokes, but there's really not much more to it, and it's all point and click.

In the end your phone will automatically unload/sync your photos and videos on a predefined schedule, you'll have a complete local copy of every photo and video file, they will be completely free from lock in to Apple or Google etc., and everything will be automatically backed up to the cloud.
