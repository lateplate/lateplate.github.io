---
layout: post
title: 5 steps to creating frustration-free Android test devices
subtitle: How to setup devices so that manual testing doesn’t crush your soul
type: default
---

A few days ago, I picked up one of my test devices to try out some new code. I couldn’t believe how frustrating it was.

I wasn’t logged into the right accounts. I didn’t have the right apps installed. By the time I finished testing, I couldn’t even remember how to reproduce the bug.

And like any Android programmer, my testing frustration was magnified because we support numerous OS versions/devices.

To save my sanity, I built a system for a unified, predictable setup on every device. Here’s how to do it.

## 1. Install the OS versions you support

Depending on what API levels you support, ideally you have a 1–1 device to API ratio. This isn’t always possible of course, but it’s helpful.

So first things first — take an inventory of your devices and which ones support which OS versions. Then examine what your customers use the most and optimize for those scenarios.

With that in mind, my lineup looks like this right now:

* **Nexus 5 (5.1.1) —** The Nexus 5 the most valuable device in my lineup. It’s supremely flexible and can run all the OS versions that most users have (4.4–6.x).
* **Nexus 5 (6.0.1) —** More than 50% of our customers are on 6.x. This is currently my baseline test device.
* **Samsung Galaxy S6 (6.0.1)**— Samsung devices make up a good chunk of our users, so it’s important to have at least one representative device. Their implementation of certain features (particularly WebView) can be different, so it’s important to test non-stock Android devices.
* **Nexus 5x (7.0)**— A newer device where I can test the very latest Android builds and features.
* **Nexus 6P (7.0) —** Not totally necessary, but it can be helpful to have one big screen device to see how things look in the real world, as compared to something closer to the 5" size. Also gives me some flexibility to move down to 6.x as needed.

(I admittedly don’t have a 4.4 device, and rely on a Genymotion VM to test for that. I’ve debated knocking down my Nexus 6P down to 6.x, and flashing a Nexus 5 to 4.4).

## 2. Install and configure a common set of testing apps

You’ve probably got a common set of apps you rely on to test your app. This is the time to make sure they’re all installed, logged in, and preferences tweaked to your liking.

App choices will vary person to person, but here are a few that I rely on and recommend:

* 1Password — Keep all your passwords secure, and makes logging in to apps so much easier. Always the first app I install.
* AZ Screen Recorder — Great for screencasts or to create gifs to share with teammates.
* Chrome Beta — We do a lot of WebView work, so we want a heads up on how future versions of Chrome/WebView will behave.
* Dropbox — Automatically uploads screenshots so I can grab them from my computer quickly. I also use it to do some file-based testing.
* Flesky / Swiftkey / Google Keyboard — Writing on our homegrown rich text editor, Trix, is a big part of our app. So we test various keyboards frequently.
* Keep — Super handy to save quick notes, URLs and whatever else synced up across devices.
* Solid Explorer — The best file manager I’ve found. Moving things around in the file system can be very handy.

## 3. Login everywhere

It sounds painfully obvious, but with so many devices floating around, you might not actually be logged in everywhere you need to be. Inventory your standard places to login and do it.

Typically for me this means logging in to just a handful of places:

* 1Password for Teams
* Google — Personal
* Google — Work
* Dropbox

It’s basic but there’s nothing more annoying than getting into your testing and realizing halfway through you’re not logged in to the right accounts.

## 4. Use Nova Launcher for a consistent experience

This was the real game changer for me. Using Nova Launcher, you can make every device look and work the same.

For me the biggest irritation was the launcher/app organization being different on every device. Everything was hard to find and it slowed me down.

Nova solves all of this.

You can setup your home screen, dock, and app drawer once, then share that across devices. When you pick up another device, your apps are in the exact same place as you expect. It’s predictable and fast— no hunting, no mental overhead.

Here’s how to do it.

* Pick your favorite device and install Nova Launcher. Buy and install Nova Launcher Prime (this unlocks a set of handy features).
* Set Nova as your home screen launcher, replacing whatever you’re currently using.
* Open Nova settings and play with all the settings. There’s too much to cover here, but take the time to make it work exactly how you want. Nova’s customizations can do anything your heart desires.
* When you’re happy with the setup, in settings go to “Backup & import settings”. Backup your current settings to Dropbox (or wherever).
* Pick up one of your other devices. Install Nova again.
* Go to “Backup & import settings” again, but this time do a restore. Pick the file from Dropbox (or wherever) that you saved in the previous step. Repeat for all devices.
* Voila — your devices now all look and work the same!

The long-term beauty of using Nova is that as your apps or preferences change, just upload a new backup and restore it on all your other devices. You’re all set again!

## 5. Tweak all your system settings

The last thing to do is go through all your system preferences and get them working the same on each device. For me that means:

* Making sure all my wifi networks are setup (home, office, favorite coffee shops)
* DND/total silence is activated. Test devices don’t need to notify me about anything.
* Developer options and USB debugging is enabled
* Screen stays awake when plugged in (developer options)
* Screen brightness is set to a level I like (with adaptive brightness off)

## Optional: live with it

One thing I like to do is swap devices from time to time and “live” with our app for a day or two on that device.

Using the app on a real device under real scenarios gives valuable perspective. You can tell if everything looks, feels, and performs as you’d expect.

To make this process easier, a couple tips:

* Use a nano SIM from your cellular provider, and keep a SIM card adapter set handy. Even though all newer devices use nano SIM, you still might run into micro SIM slots (or if you’re really lucky, a standard SIM slot!)
* Install apps that you use outside of work. This helps ensure you don’t jump ship back to your daily driver, and you give the test device a real shot. But keep your personal apps in a separate tab in Nova’s app launcher. That way your testing apps are still front and center, but you can still get to the fun stuff and live with the device for a bit.

That’s it, I’m glad you made it this far! Following these steps should help reduce your manual testing frustrations, and hopefully keep you in the zone doing the more fun stuff (like programming everything that needs to be tested!)
