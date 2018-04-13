---
layout: post
title:  "Phoenix & Elixir - a web framework review for the business-minded"
date:   2018-02-21 01:00:00 -0400
categories: non-technical project-management
---

## Introduction

At the strong recommendation of a client, I checked out Phoenix, which is a web framework built on top of the Elixir programming language. As a programmer, I was *totally geeking out* about it because it’s a pleasure to work with and is soundly engineered. On top of that, Phoenix/Elixir presents a very attractive engineering proposition; from their website:

> [Phoenix/Elixir is] a productive web framework that does not compromise speed and maintainability.

Of course, while speed and maintainability are important, they are not everything in a wider business context. There were some pretty important business concerns that I would advise you to consider before adopting Phoenix/Elixir in your organization. If those concerns are ones that are acceptable to you, or do not apply to you, then this framework can be a fantastic technical choice, even for an important or flagship product.

## Strengths

### Scalability

A quick introduction to scaling: when popularity rises greatly, web applications need to be able to serve more requests by “scaling up”. Scaling up is often done by adding multiple computers to a “cluster”, because multiple computers acting in concert can serve more requests, faster, than a single computer can. The price of scaling up is complexity and a reduction in maintainability because these machines need to know how to coordinate with each other, which usually means a lot of time spent by your developers in coding up that coordination logic.

Phoenix/Elixir’s killer feature is how easy it makes it to scale up, while at the same time retaining the productivity and reliability of a traditional “MVC” web framework (like Rails or Django). This is because it is relatively easy to work with, and at the same time rests on the solid foundations of Erlang’s BEAM VM, which is the technology that WhatsApp ($19 billion exit with only 50 engineers) was built on.

On a quick technical note, you can share [this (code-heavy) article](https://dockyard.com/blog/2016/01/28/running-elixir-and-phoenix-projects-on-a-cluster-of-nodes) with your developers. Phoenix/Elixir makes it look positively easy to run a full cluster of servers in production.

### Performance

Performance is different from Scalability. Scalability is how well multiple machines can work together within a project, while Performance is how fast a single machine can run your project.

Scalability aside, for such a pretty framework, Phoenix/Elixir is also *blazing fast* on a single machine, and its speed shows immediately out of the box with sub-millisecond response times for pages. That was really cool to see in a framework that promises to be as productive as Rails or Django.

Phoenix/Elixir projects will be *probably faster* when compared to projects built in frameworks that run on Ruby, Python and Node.js, but will be *probably slower* than frameworks built on the Java/JVM and .NET language families. Phoenix/Elixir projects will be *almost certainly slower* on a single machine than projects built on C/C++ and PHP. But Phoenix will probably really shine when you need to scale, as was stated above.

### Productive out of the box

If you need to take your product to market quickly, and at the same time anticipate large scalability needs (say, if you were building the next Pokemon Go), Phoenix/Elixir has you covered. Out of the box, developers will be able to build and style webpages, as well as quickly integrate with one from a number of types of databases. It is also very easy to extend and build out existing features, and Rails developers will feal right at home with lots of Phoenix’s conventions and with the Elixir language, which is built to look a lot like Ruby.

## Weaknesses

### Small developer community

As a developer, it’s very, very difficult to find open source libraries that are of sufficient quality to responsibly use in a production environment. It is also very difficult to find good resources online that will let you learn more advanced concepts in the framework. I have heard from my client that the Phoenix/Elixir Slack channel has a very active community that will answer any questions you may have. This has its appeal, but is still a lot less desirable than having a wealth of online resources from which a developer can learn.

### Hard to hire and train developers

Phoenix is not a mainstream framework, which wouldn’t matter very much had it been built in a mainstream language. However, it’s built in Elixir, which is also a non-mainstream language. As if that weren’t obscure enough, Elixir is also a “functional programming language”. Functional languages tend to be very difficult to hire for because “object oriented” and “imperative” languages are what most companies are using most of the time. As such you might run into issues when you’re looking to hire developers, simply because the number of Phoenix/Elixir developers is much, much smaller than that for another language.

Since Elixir is not only a less-popular language, but is also a functional programming language, you’ll be forced to hire developers who have the interest/ability to work in a lesser-known functional programming language. Training developers to use functional programming languages like Elixir can take a long, long time as well, because functional programming languages are seen as hard to work with or obtuse to most developers. As such, if you’re already foreseeing the need to hire many more developers to work on your project, it might be worth skipping Phoenix/Elixir and checking out a more mainstream framework.

### Finding SDKs and official libraries is hard, and Elixir is unsupported by most communities

If you wanted to integrate a .NET application with Quickbooks, a Java application into Twitter, or a Node.js application with Amazon AWS, you could leverage official toolboxes called “SDKs” (software development kits) to help you do that in your language. However, since Elixir is so niche, it is unsupported by most companies. As such, any API integrations will necessarily have to be homebrewed in Elixir. This alone might be enough reason not to use Elixir for some companies.

## Thank you for reading 

As a developer, I love how beautiful Phoenix/Elixir framework is. It’s certainly business-ready in my opinion, but as a CTO I’d be careful before choosing to use this framework unless you really need the massive scalability. These downsides come from the fact that Phoenix/Elixir is not a mainstream framework/language. It’s worth remembering that almost ALL web frameworks have the capacity to serve thousands of users a day, and that if you’re not there yet, then you might be able to build in another, more mainstream language and save yourself from the multiple downsides that come with using Phoenix.

## Links

* [The Elixir Language](https://elixir-lang.org/)
* [The Phoenix Framework](http://phoenixframework.org/)
