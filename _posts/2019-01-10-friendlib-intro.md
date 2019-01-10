---
layout: single
classes: wide
title:  "FriendLib - Intro to my current side project"
date:   2019-01-10 20:50:00 +0100
header:
  image: /assets/images/keyboard.jpg
  teaser: /assets/images/friendlib-intro/teaser.jpg
sidebar:
  - image: /assets/images/friendlib-intro/teaser.jpg
categories: coding
---

Since a August 2018 I'm working on a new side project called _FriendLib_. 
The basic idea about the app is that you can check which books your friends own and instead of buying the books you ask you friends if you can lend the book. 
The name is a portmanteau of friendship and library.

I don't remember exactly how I came to the idea, but I remember that I read something about the book [__Thinking, Fast & Slow__](https://amzn.to/2Rs4t1m)* by Daniel Kahneman and I thought it might be interesting to read (that's how it found it's way on my [Reading List]({{ site.baseurl }}{% link _pages/readinglist.md %}) for 2019.
The next day at the office, by chance a colleague started to talk about that new book he just bough and started to read. Guess what he was taking about Thinking, Fast & Slow. So instead of buying the book myself I now knew that he owns it and asked if I can lend if once he has read it. Easy.

So I thought is [there an app for that?](https://www.youtube.com/watch?v=DtwJCkqU-_E) And apparently there isn't. So I decided to use this use case for a (not so) little side project. There are a few tools, frameworks, architectural styles that I want to try out anyway and I like rather to have a meaningful (aka real world) example than a Todo List App.

Using the [Event Storming technique](https://en.wikipedia.org/wiki/Event_storming), the awesome [RealTimeBoard](https://realtimeboard.com/) and the help of some friends I quickly outlined the basic functionalities of the app.

![FriendLib Event Storming in RealTimeBoard]({{ site.baseurl }}/assets/images/friendlib-intro/realtimeboard.png)

These are:

* Registration / Login
* Management of the own library (how else could your friends know the books that you own)
* Managing Friendships
* Browsing the library of friends
* Searching books (with an indication if any of your friends has an exemplar of it)
* Managing book lendings (accept lend requests, follow-up the status, reminders ...)

Turns out its quite a lot of functional stuff to do. Additionally I have some learning goals for that project.

For example:

* Angular 2+ and Ionic
* Serverless using AWS (I already did things with [ClaudiaJS]({{ site.baseurl }}{% post_url 2017-11-24-simple-web-api-using-claudiajs %}) before)
* App Store deployments for iOS and Android (automated using tools like [fastlane](https://fastlane.tools))
  * the iOS part already looks quite good as you can see [here](https://github.com/carlo-mr/friendlib-app/pull/3)
* Documenting the whole solution using the [arc42](https://arc42.org) template and the [docs as code philosophy](http://www.writethedocs.org/guide/docs-as-code/) using the [docToolchain](https://doctoolchain.github.io/docToolchain/)
  * A first result can already be found [here](https://carlo-mr.github.io/friendlib-documentation/)
  
Ideally I find the time to write a few posts during the development. So far (since August 2018) I was not so successful with this intend.

So as you can see a lot of plans for 2019. Stay tuned for updates.

_Teaser Photo by Alfons Morales on [Unsplash][teaser]_

\* personalized link

[teaser]: https://unsplash.com/photos/YLSwjSy7stw?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText