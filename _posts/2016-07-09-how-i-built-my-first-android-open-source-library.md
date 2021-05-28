---
layout: post
title: How I built my first Android open source library (and how you can too)
subtitle: A practical, step-by-step guide for building your own open source library.
type: default
---

In early 2015 I recognized a major hole in my professional work — I hadn’t made a single open source contribution. That’s pretty embarrassing to admit, considering I work with some major open source contributors on a daily basis.

Shortly after that depressing realization, I set a goal for myself: find a way to make at least a few small open source contributions within the next year.

As luck would have it, I knew that Turbolinks 5 would be released in early 2016. And one of the goals of the Turbolinks 5 project was to have adapter libraries for all three major platforms — web, iOS, and Android.

So having never done any open source work at all, what did I do? I volunteered to lead the charge and build a brand new Android open source library from scratch. 😳

Sure, I stumbled along the way, but in the end I somehow figured it out and we successfully launched [Turbolinks Android](https://github.com/turbolinks/turbolinks-android) in February 2016. 🎉

## Why create a guide like this?

Creating an open source library has been such a rewarding, fulfilling experience — so much so that I want to encourage any open source newbies to give it a shot.

But hey, I get it — if you’ve never open sourced anything before, it can be a bit daunting. You don’t know how or where to start and you don’t have a map to tell you where to go.

And that’s exactly why I wrote this gigantic article —to hopefully give open source newbies some general direction on how to get started.

Keep in mind, this is based solely on my experience, and I’ve only done this once. Still, if you’re just getting started with building your own Android open source library, I hope it helps. Onward!

## Step 1: Build a real app for yourself

First and foremost, build an app that does what you need it to do. Don’t worry about open sourcing anything at this point.

This is important — you don’t want to get bogged down with a bunch of questions about open sourcing that don’t matter yet. Hell, you don’t even have anything to open source yet!

Just keep building your app as you normally would. Your goal at first is to take care of yourself and make a great app, not worry about other people and their projects (at least, not yet).

And build only what you need — nothing more, nothing less. If you start worrying about open sourcing too early, you’ll start making premature design decisions in your code, like prioritizing “flexibility” over convenience and clarity. It’s not worth it— you’re just making complete guesses!

## Step 2: Identify a problem your code is solving

Once you’ve got your app in a good place, it’s a perfect time to look at your code and determine what parts of it might be useful to others.

Scan your app and keep an eye out for…

* Code you’ve re-used from a previous project. If you’re borrowing code from something you worked on before, there’s a good chance it’s doing something useful and could be bundled up as a library. At the very least, it’ll save you the trouble of using it in your next project.
* Code that’s “your version” of another third party library. If you’ve written code that does roughly the same thing as another library, that’s actually a good indicator of a potential library. Even if your implementation is similar, how you approach the problem — your style — is what will come through. If existing libraries didn’t meet your needs, then there are probably hundreds of developers who are in the same boat.
* Code that solved a particularly difficult (or tedious) problem set. Think about how appreciative we all are for libraries like Retrofit, GSON, and Robolectric. If you’ve solved something painful but necessary, think of how much good you can do for the community!
* Code that is a unique solution to a common problem. As an example, Turbolinks Android falls into this category. It speeds up WebView performance by using a shared WebView, with Turbolinks doing all the work of requesting, rendering, and caching. That’s our unique take on solving a performance problem, but there are dozens of other ways to improve WebView performance too (caching, pre-fetching, mobile-specific views, etc.).

## Step 3: Extract the relevant parts

Once you have an idea of what your library will do, it’s time to extract that code out into it’s own package and classes.

The goal here is simply to put together a rough outline of what the library components might be, and to see them all together. This also starts to put a soft delineation between your app’s code and what will eventually be your library.

You’ll need to hunt down all the relevant methods and slowly move them into new classes, most likely in a new package. Android Studio’s refactoring capabilities should make this pretty straightforward.

I’d recommend doing this in small pieces, slowly testing your app as you move things over a few things at a time.

Don’t get too hung up having it perfectly organized yet. Hell, you can even just throw them all in one giant class for now.

And definitely don’t worry about what the public interface is going to look like — method names and signatures don’t matter yet. Just do a “raw” extraction and get your app compiling and running.

## Step 4: Refactor everything into a private interface

Get ready — this is going to be the lion’s share of the work!

Now that you’ve gone through the work of extracting the code into their own classes/package, it’s time to refactor everything. Update your method names, method signatures, dependencies, class structure. Refactor everything until you’re happy with how the library’s code looks on its own.

As you’re going along, keep this in mind: everything should click in your brain and feel natural.

Part of what’s great about building your own open source library is that it’s opinionated software. You want it to serve you and other likeminded people. So building the library in a way that fits your brain is the first step toward making a great public interface (the next step).

Beyond doing the pure plumbing of refactoring, you’ll want to gut check how your library’s interface feels in the context of your app.

If you’re on the right track, you’ll get good vibes about how the library integrates into your app’s code — readability, clarity, and the convenience it brings will all feel very natural. If it doesn’t, it’s time to go back and refactor some more.

This is also an excellent time to solicit as much feedback as you can from other programmers, regardless of their language preference. Some of the most valuable feedback I received was from Rails and iOS programmers. Iterate your code and create pull requests early and often.

## Step 5: Stabilize a public interface

Now that you have an interface you’re comfortable with, it’s time to start thinking about other developers.

The good news is that you’ve done 80% of the hard work already with your private interface.

The bad news is that the remaining 20% is going about making things super stable, which means repetitive, check-everything-with-a-fine-toothed-comb work. The goal is to review every last detail of the library to make sure it’s solid.

This is the time to take a final pass through everything — naming, visibility modifiers, method signatures, every object passed in or out of your library, and whatever else you can think of.

Then test, test, and test some more.

All that said, I don’t want to make too fine a point of this. While you’ll do your best to make sure you’ve covered everything, the reality is that you’ll still miss stuff. Don’t fret — it’s software, things break. We’ll understand. 😉

## Step 6: Document it

Since this is so late in the game, you might have thought you’d get away without having to do any documentation — nope, it’s a necessary step!

While I can’t say writing documentation is boatloads of fun, I did find it to be super valuable when building an open source library (I’m still generally anti-comments in private app code). Here’s what you’ll need to do.

**Javadocs** — You’ll want to comment every single class and method, public or private. Assume that nobody has any idea what you’re doing in the library code.

To be clear, I don’t mean you should comment every line of a method — your code should still do most of the talking. But writing a Javadoc comment for every class and method will 1) help people looking at the source and 2) let’s you to generate a nice Javadoc.

Once everything is commented, generate a Javadoc and give it a read. Look for holes and things you’ve missed. Have others read it. Does everything you wrote make sense to you and to others?

**README** — A good Github README does a few things:

* It describes what the library is and does at a high level
* It provides clear instructions for basic configuration and getting started
* It provides instructions for advanced techniques or configuration for those who are interested

I’ve found the best thing is to mimic READMEs from other libraries that you’ve found helpful. Here are a few recent ones that we’ve written that I think do a good job:

[Trix](https://github.com/basecamp/trix#readme)
[Turbolinks](https://github.com/turbolinks/turbolinks#turbolinks)
[Turbolinks Android](https://github.com/turbolinks/turbolinks-android#turbolinks-android)
[Turbolinks iOS](https://github.com/turbolinks/turbolinks-ios#turbolinks-for-ios)

## Step 7: Move the library code to its own project

Now that code complete and fully documented, you’re inching your way to publishing this to the world!

Before publishing you’ll want to move all the library classes to its own Android Studio project. This ensures the library is completely self-contained, eliminating any unexpected dependencies on your app. You basically want to see if it can compile and stand on its own two feet.

Once you’ve moved everything to a new project, you’ll need to setup a dependency to that project’s files. This is weirdly tricky in Android Studio, so here’s how to do that.

In settings.gradle:

```
include ':app'

// name of the module
include ':turbolinks'

// location of the dir in your app’s build.gradle file:
project(':turbolinks').projectDir = new File(settingsDir, '../turbolinks-android/turbolinks')

dependencies {
    compile project(':turbolinks')
}
```

With those two configurations in place, the two projects are now file linked — any changes to the library files from either your app’s project or from your library’s project will update the same files.

## Step 8: Publish it!

Finally, it’s time for all that hard work to pay off!

Relatively speaking this step is pretty easy, albeit a bit tedious. You’ll be publishing to jCenter, which is the default repository with Android’s Gradle plugin. You’re simply packaging up your library in a way that Android Studio understands, and in a place that Gradle already knows about.

My recommendation is to follow a combination of the three resources below. They are pretty much step by step and walk you through the entire process of publishing to jCenter.

* [How to distribute your own Android library through jCenter and Maven Central from Android Studio](https://inthecheesefactory.com/blog/how-to-upload-library-to-jcenter-maven-central-as-dependency/en)
* [Publishing Gradle Android library to jCenter repository](https://www.virag.si/2015/01/publishing-gradle-android-library-to-jcenter/)
*[ Publish an aar file to jCenter with Gradle](https://github.com/danielemaddaluno/gradle-jcenter-publish)

Once you’ve done that, your library is published. Congratulations! 🎉

## Step 9: Maintenance and community relations

Now that your library is public, there will be more eyes on your work — questions, issues, pull requests and discussions will crop up. This is a good thing!

I’m always thankful that people are interested in the project and want to be involved. But there will be times when you disagree with a discussion or you simply don’t have time to address everything. That’s OK!

Maintaining a library is no small task. There’s going to be some pressure from the community to keep things moving. We all want things to be better. But it’s also OK for you to say no or to defer work. There is literally always more to work on.

The most important thing is that you keep you continue enjoying working on the library. If that means addressing all the community requests, do it. If that means saying no, do it. If that means working only on the things you want, do it. Keeping your sanity and happiness working on this library will be what sustains it for the long run.

## Summary & Acknowledgements

If you’ve made it this far, you’re well on your way to launching your own Android open source library. You’ll soon be helping a lot of people by making their lives easier and their work better. Great job! 👏🏆

If you have questions about anything I wrote about or just want to chat, I’m always glad to help! Feel free to email me or hit me up on Twitter.

Also, this process is the furthest thing from a one-person show. Literally none of what I talked about above — creating the actual library and having the opportunity to do so — would have been possible without the help and encouragement of everyone at Basecamp. Thank you all!

I’d like to thank a few specific folks for their unwavering support and contributions in helping launch and maintain Turbolinks Android: Jay Ohms, Jamie Dihiansan, Sam Stephenson, Jeffrey Hardy, and Zach Waugh. ✊
