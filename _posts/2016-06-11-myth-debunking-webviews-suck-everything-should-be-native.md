---
layout: post
title: Myth debunking — WebViews suck, everything should be native
subtitle: Contrary to popular belief, Android webviews aren’t your enemy — they’re your best friend
---

If there’s one thing that gets a lot of shit on Android, it’s webviews (OK, not as much as fragments, but it’s up there).

How do I know? The next time you talk to an Android programmer or designer, try this little experiment: tell them you use a lot of webviews. Then wait for the confounded looks on their face and the subtle “ouch, sorry” nodding of the head.😲

The reason people feel that way is because we’ve been conditioned to think the “right way” to build apps is by making everything a native screen. Surely no serious, self-respecting native app developer would use a bunch of webviews!

To the contrary! Webviews are wonderful and offer us incredible scale, flexibility, freedom, and happiness.

## 200 screens, 2 programmers, 1 designer, 40 hour weeks, 3 vacations, 1 sabbatical

Being a small company is something we hold dear at Basecamp — it’s a core value of the company.

But Basecamp 3 is not a small app — its feature set is both broad and deep. It has well over 200 unique screens, and new ones are added every week.

And yet with so many features and screens, Basecamp 3 for Android was still built by only two programmers and one designer.

In earnest, the Android app started development in March 2015 (when we assembled our full team), and it launched at the beginning of November 2015. That’s roughly 0 to 100% in 8 months.

The key to shipping was that we leaned on the webviews where we needed to.

While the Android team was building native functionality and views for high-touch screens (things like push notifications, navigation, the home screen), a whole bunch of other webview screens were built by our web team. They had our back, building high-fidelity, mobile-friendly webviews that our app could use.

For the sake of argument, let’s do some back of the napkin math to see how important webviews were to Basecamp 3 for Android. If we assume each screen takes an average of 3 days to build/test natively (which is a highly aggressive estimate, but let’s go with it), the math would work out to:

* 200 screens x 3 days per screen = 600 days
* 600 days / 2 programmers = 300 days per programmer
* 300 days / 20 work days per month = 15 months
* 15 months! That would have been a mere 7 months overdue. Or if you wanted to be a real sadist, we could assume 30 days a month of work, and that would get us to 10 months! 😭

And let’s not forget, this also assumes 1) no new screens are added 2) no screens are ever changed 3) we are 100% efficient every single day and 4) we don’t take a single day off. Yeah right!

The math simply didn’t add up. To make the math work, we had to rely on webviews.

**The result**: we worked 40 hour weeks during the cold months, and 32 hours weeks in the summer months. We took our vacations and sabbaticals. We lived our personal lives. And on launch day, we had full coverage of Basecamp 3, on-time, in-scope, and without burning anyone out.

If your app is moderately large, and keeping your team small and sane is something your team values, you need webviews.

## Programmer happiness and native level-ups

One argument the all-native camp makes is that native screens are simply better all around. But better for who?

Sure, you could argue that a native screen provides the best interaction experience for customers. And whatever is best for a customer, it’s certainly worth doing, right?

But it’s not really that cut and dry.

What’s best for the customer sometimes means doing what’s best for your team. And what’s best for your team is when you’re happy — when you’re excited to work on something and given autonomy over your work. That’s when you produce your best work for a customer.

Webviews give us the flexibility and freedom to choose what screens to level up as native views, instead of being forced to make everything native.
This allowed us to focus on screens we knew would get used a lot (like our home screen) and really fine-tune those. Not only was that good for our customers, it was good for us. Those screens are a ton of fun to build.

Now imagine the opposite scenario — having to re-make native screens for every admin, settings, or text-heavy instructional screen that’s already been made on the web. As a motivated designer or programmer, how quickly would you get bored with that kind of copypasta work? Those aren’t the kinds of things that get intrinsically motivated teams out of bed in the morning.

The freedom to choose our native level ups was a true godsend, and was only possible because we had full webview coverage for everything else.

## You don’t need 100% native fidelity on every screen

I can hear the haters — “Sure, you can use webviews for everything, but everyone can tell they’re webviews and not native”.

So what?

Does every single screen need to have 60 fps animations, with activities that launch from the exact x/y coordinate where my finger touches the screen? Does that kind of fidelity matter on an admin screen? Does it matter to people who are just trying to get their work done if a screen follows the Material Design spec exactly?

Look, I’m all for great design and attention to detail. We take it seriously and I respect it immensely.

But everything is a tradeoff. And under the right circumstances, am I willing to trade a little native fidelity when we can get 90% of the way there with a webview? Absolutely.

## Webviews with Turbolinks 5 enabled are plenty fast

Critics of webviews may point to their page loading performance as a reason not to use them.

But with the introduction of Turbolinks 5, the performance of webviews is pretty much a non-issue.
It doesn’t give you carte blanche to make ridiculously heavy webviews, but it sure will carry you pretty far even if you do.

To take advantage of our Turbolinks enabled webviews in Basecamp 3, we built and open-sourced Turbolinks Android, a library that makes working with Turbolinks trivial. Just add one dependency, then tell the library to load your page:

```
protected void onCreate(Bundle savedInstanceState) {
  ...
  TurbolinksSession.getDefault(this)
    .activity(this)
    .adapter(this)
    .view(turbolinksView)
    .visit("https://3.basecamp.com");
}
```

That’s basically it. Turbolinks Android takes care of the rest — providing you with everything you need for ultra-fast page loads from a single, low-memory webview instance.

## Scaling our apps with independent, complementary teams

Webviews give us immediate and amazing scale across platforms. Instead of using the efforts of just two Android programmers, we can harness the power of all thirteen of our programmers together.

Every team working on a feature has the capability to not only build new stuff, but to deploy them to all of our customers quickly with minimal coordination across teams and zero red tape.

Once a team has tested a new feature on the Android app, they deploy it without any intervention from us. Every customer immediately benefits from the new feature on the web and in the app.

This is a wonderfully independent, yet complementary way to work. No team is ever stymied in deploying new stuff to customers, and every platform, including our Android app, automatically improves.

---

So there you have it — we’ve reaped a bunch of amazing benefits from webviews, a component that gets more scorn than love in the Android world.

But remember, one size does not fit all. The techniques and styles that work for some teams might not fit your team well.

Continue to challenge conventional viewpoints that don’t feel right to you (including this post)! The most important thing is to find what fits your team’s values and build around those. 🤘