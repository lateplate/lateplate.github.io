---
layout: post
title: Rewriting bad writing
subtitle: Become a better writer by taking a poorly written piece and rewriting it yourself
---

Once in a while I read something so complex and poorly written, when I’m finished I have no idea what I just read. It’s insanely frustrating.

While writing isn’t an easy skill, people make it way harder than it needs to be. They think choosing complex language shows skill and smarts.

It doesn’t! Writing plainly and clearly does.

Somewhere along the way, Jason Fried dropped a lesson on our team: if you think something is poorly written, rewrite it.

It 1) is a chance to learn 2) shows you’re willing do the work beyond complaining and 3) helps you think about how to handle a similar situation. Ultimately the exercise makes you a better writer.

Let’s do it.

---

Case study: A Mozilla project announcement

Below is an overly complex, hard to read [project announcement](https://groups.google.com/forum/#!msg/mozilla.dev.planning/j834iDIG3yY/V84Rzw0cEAAJ). Try to fight your way through it. 😰 My rewrite follows.

***Disclaimer**: This is an isolated critique of a single piece of the author’s writing. It’s absolutely not about them as a person or their other work. I’ve written plenty of bad stuff too. Please feel free to go back and critique the hell out of my writing, it’s a good way to learn*.

## Mozilla’s version

>Announcing Project Mortar

> In order to enable stronger focus on advancing the Web and to reduce the complexity and long term maintenance cost of Firefox, and as part of our strategy to remove generic plug in support, we are launching Project Mortar.

> Project Mortar seeks to reduce the time Mozilla spends on technologies that are required to provide a complete web browsing experience, but are not a core piece of the Web platform. We will be looking for opportunities to replace such technologies with other existing alternatives, including implementations by other browser vendors.

> In order to keep costs low, we may use APIs internally that are not considered web standards. These APIs will not be exposed to the web. Solutions that both reduce our support cost, achieve the desired user experience, and make use of web standards will be preferred.

> The project will start by investigating how Firefox handles PDF rendering followed by looking into lower cost approaches to providing Flash support as it’s usage continues to decrease. Project Mortar is currently investigating using the minimum set of Pepper APIs needed to support the PDFium library and the Pepper Flash plugin. If successful, this work will allow us to completely remove NPAPI support from Firefox once NPAPI is disabled for general plugin use.

Here are the main problems with this announcement:

* Its super long sentences are hard to parse and understand.
* It uses a lot of impersonal third-person language.
* There’s too much detail/fat drowning out the main message.

Let’s fix those and see what we can learn.

## My version

> Today we’re launching Project Mortar.

> The goal: advance the web by reducing Firefox’s complexity and long-term maintenance.

> We all want to make the best browsing experience for our users. That means we need to spend less time building non-core web components. Especially when we can replace them with existing alternatives.

> We’ll keep our eyes open for the best options, like those based on web standards. Occasionally we may need to use our internal, closed APIs. Together they’re our best chance at reducing support costs while still giving users a great experience.

> We’ll start with two major areas in Firefox — PDF rendering and Flash.

> We’re starting with PDFium and Pepper Flash as possible replacements. We’re currently looking at what Pepper APIs we need to pull this off. If all goes well, we can completely remove NPAPI support after it’s disabled for general plugin use.

> We’ll continue to post updates on the project wiki.

> As always thanks for reading and for your continued support!

I don’t mean to pat myself too hard on the back, but I think that’s a a lot clearer and easier to understand. 😉

What do you think? Better or worse? What did I do right or wrong?