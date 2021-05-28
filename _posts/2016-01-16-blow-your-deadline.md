---
layout: post
title: Blow your deadline, blow your budget, and chalk it up as a success
type: default
---

Blow your deadline, blow your budget, and chalk it up as a success!

At the end of 2015, we launched an account switching feature in the Basecamp 3 Android app. On the surface it’s a pretty basic feature — if you’re part of more than one account, you can just tap a menu and flip over to another account.

This feature met all the criteria our team looks for when picking new work to start: it was something customers wanted, it was something we wanted, and it seemed shippable within a two week budget.

**The result**: We shipped a great version of the account switcher. Success!

**The fine print**: It took us six weeks to ship. We completely blew the budget and deadline. 😭

What happened? How did we balloon from two weeks to six weeks? And how can we call this a success?!

## The Problem: We Didn’t Have All The Information

As many programmers have (rather painfully) experienced, we didn’t have all the information up front. When we originally budgeted two weeks worth of time, we assumed that our foundational code was solid enough to keep building on.

That assumption was wrong.

Over time and in the natural rush leading into launch, some things slipped. Our code wasn’t quite as organized as it used to be. AsyncTasks were making our code hard to read, and even harder to maintain. Our local data storage scheme was hard to use. Somehow four different authentication paths got bolted on. Our unit test coverage wasn’t as robust as it should have been.

But none of that was obvious during week one of building this feature. Or even week two. Or even week three. You get the picture.

The Real Measure Of Success: Laying The Groundwork

Sam Stephenson, a programmer at Basecamp and one of the smartest people I’ve ever met, said it best:

> Then, instead of solving the problem with an ad-hoc, one-off change, lay the groundwork for a general system that facilitates the specific change you want to make.

That, in a nutshell, explains how our two week feature turned into a six week mini-project. And it’s why we absolutely classify this venture as a success.

We ripped out AsyncTasks and replaced them with Android Priority Job Queue. We rewrote our entire data storage system. We cleaned up our authentication code. We wrote new tests and improved others. We did a bunch of things that would take too long to list here. We did everything we could to improve our general systems for future work. (And oh yeah, we wrote all the new code to make switching accounts work too!)

In short, our team recognized the incredible value in doing things the right way, not the fast way. We knew that rewriting, refactoring, and reorganizing large chunks of our codebase was a worthwhile effort to give us a more solid foundation going into 2016.

Yeah, we could have shipped this feature in two weeks. But it was far more important to lay a solid groundwork in six weeks. We respect our deadlines, but we respect the quality of our work much more.

## What Did We Learn?

Even though we were happy with the end result, there were certainly things we could have done better. So what did we learn?

📅 After one or two weeks, we could have paused for a couple of days and taken a step back. This would have given us time to analyze more deeply, reset expectations, and set a new soft deadline. Even if we came to the same conclusion / deadline, resetting still would have been beneficial for getting us all on the same page and reassessing our current priorities.

🎥 As soon we had a feeling this was going to take more than two weeks, it would have been helpful to schedule regular Google Hangouts for our team. Discussing things “face-to-face” (in moderation) can really bring out a lot of good ideas and attack vectors to problems.

📝 We could have done more frequent, small written pitches to help describe interactions and systems. When discussing something complex, sometimes rapid-fire conversations in Campfire can be hard to follow. Luckily, Basecamp gives us a lot of options like to-dos, documents, or messages to take things down to a slow gear — letting us write more methodically and thoughtfully to clarify our thinking.

🏃 Rushing gets you nowhere. There were a few moments where I felt the need to push harder, to rush, to race to the finish line. I think that’s only natural when you’re motivated and want to do great work. But my teammates were supportive and we were able to refocus on the long-term. Great teammates will always help you make the right decision.

So in the end, we shipped a pretty nice feature, laid the groundwork for 2016, and learned a lot along the way.

I guess doing all that in six weeks doesn’t seem so bad. 🎉
