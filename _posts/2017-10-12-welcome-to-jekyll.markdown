---
layout: post
title:  "JavaScript: What's the matter with it? Question and response."
date:   2017-10-12 16:29:31 -0400
categories: jekyll update
---

>
 I understand and agree with [some points against JavaScript you mentioned earlier], but it's quickly becoming the most used language / stack (top 5 at least) and it's momentum is not going to slow any time soon. I think Java is the #1 most used language, but isn't Java a lot older and less sophisticated?
(Disclaiminer I am somewhat new and learning more everyday, my focus being on the JavaScript MERN stack right now.)
>
> -- a friend of a friend on Facebook.


Those are great comments, and that's a great question! JS is absolutely the most talked-about language in the world right now, and I wouldn't be surprised if it was indeed the #1 most-used language in the world as of today. You are right in the trenches with the MERN stack, and that's a fantastic place to be. I started off with JavaScript as my first language as well, and I continue to think in JavaScript a lot of the time 😄

The reason Java is so popular is because of how safe (in terms of bugs) and productive (in terms of maintaining and refactoring a large codebase over several years or even decades) a language it is when it comes to working in teams and building scalable software. 

Working with Java using Eclipse or IntelliJ is an absolute pleasure once you've spent a few weeks grokking the Java ecosystem; the psychological flow, enjoyment, and productivity achievable in Java are beyond what is achievable in JavaScript. 

Don't get me wrong! JS is a perfectly OK language to develop in for many use cases, including the web, but Java gives you superpowers.

To give a small example, the command to rename any function of a class (for example, 'getUsers()', which might be used across 100+ unrelated files, can be accessed in three keystrokes. The change (which has touched all 100+ files) can often be safely committed without local testing. Can you imagine how many classes of bugs are eliminated with this ability? Can you imagine how productive you can be?

Another example: if you try to assign a String to a Boolean type variable, the compiler will not let you compile your code, and will give you the filename and line number where you messed up (similar to TypeScript, except much more powerful). I've personally written more type-checking logic than I can remember in JS; but none is needed in Java.

Sure, Java is old. But age has very little to do with the quality of a language. From my experience, the people exhorting you to try something new usually stand to gain from greater adoption of that new thing; from what I've seen, 'new' in software engineering is a marketing buzzword. You should give Java a shot if you get the chance in a professional setting; you'll be pleasantly surprised I think.

Apologies for the long reply :) TL;DR: Try Java, you'll like it!