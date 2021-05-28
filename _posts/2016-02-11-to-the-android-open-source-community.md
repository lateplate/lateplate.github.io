---
layout: post
title: To the Android open source community—Thank you!
type: default
---

While developing the Basecamp 3 Android app over the past year, we’ve leaned quite a bit on some really useful open source libraries.

These libraries did a bunch of heavy lifting for us. They helped shorten our development time, increase programmer happiness (since we didn’t have to write them from scratch!) and ultimately ship a better product.

Open source is such a deep-rooted part of Basecamp’s culture that I think it’s important to give credit where credit is due. I want to, in some small way, show our gratitude to a group of people who probably aren’t thanked all that often.

So, to all of you — the women and men who author and maintain Android open source projects everywhere — thank you very, very much for all your hard work!

## The All-Stars

There are lots and lots of libraries out there, so I’d be remiss if I didn’t call out some all-stars that really helped us out.

Big thanks to the teams that build and maintain these libraries — you’ve made our work and lives better! (If you’re an Android programmer, it’d be a good idea to bookmark these if you’re not already using them.)

* [Facebook’s Stetho](https://github.com/facebook/stetho/): A debug bridge that lets you use Chrome Developer Tools to inspect native UI, resources, and data. We use this quite a bit to debug layout issues and stored preference data.
* [Flipboard’s BottomSheet](https://github.com/Flipboard/bottomsheet): An easy way to mimic Android’s bottom sheet interaction without writing it from scratch. We use this to power our share sheet, and have some ideas about future uses too.
* [Google’s GSON](https://github.com/google/gson): Easily serializes JSON into Java objects. We use GSON a lot to serialize JSON data, which makes it a breeze to work with in Java.
* [greenrobot’s EventBus](https://github.com/greenrobot/EventBus): An event bus that makes it super easy to implement a pub-sub model. We use events for all sorts of stuff, like updating the UI when a background data call finishes.
* [Path’s Android Priority Job Queue](https://github.com/yigit/android-priority-jobqueue): A job manager that has simple defaults, but offers a lot of power too. It’s fantastic for running asynchronous jobs and a wonderful replacement for the dreaded Asynctask.
* Square’s [Retrofit](https://github.com/square/retrofit) and [OkHttp](https://github.com/square/okhttp): If you’re doing any kind of API or HTTP work, you need to use these, period. We use Retrofit exclusively for all of our API interfaces.
Giving Back — Turbolinks Android

Like any good citizen of an active developer community, we’re not just going to leech — we’re ready to give back!

In short order we’ll be releasing our first open source Android library — Turbolinks Android. It’s the same adapter framework that’s powered our Basecamp 3 Android app since November 2015, and it’s a crucial component in our native-web hybrid approach. It’s made specifically for Android, and will get your hybrid app hooked up to a Turbolinks 5 web app in a jiffy.

We’ve done our very best to make sure Turbolinks Android possesses all the qualities that we love about the all-stars libraries above: easy to get started, easy to use, fast, and reliable.

We’re thankful that we’ve been able to stand on the shoulders of awesome libraries ourselves, and can’t wait to get Turbolinks Android out to the open source community!
