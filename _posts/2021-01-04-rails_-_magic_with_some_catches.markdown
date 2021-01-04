---
layout: post
title:      "Rails - Magic with Some Catches"
date:       2021-01-04 14:20:35 +0000
permalink:  rails_-_magic_with_some_catches
---

When speaking to anyone familiar with web development, I have almost invariably been asked the question, "Have you started Rails yet?"  With no prior experience, I probably would have assumed that Rails was the name of a programming language, and that Ruby was its antiquated predecessor.  We hear so much talk and praise about "Rails Magic" and a treasure-chest of "gems," that it's easy to lose sight of the real picture:  Rails is simply a *framework*, a structure built upon a foundation of Ruby.

Throughout the Flatiron lessons on Rails, we were reminded of the importance of actually understanding how Rails or a gem performs its magic before using or relying on it (a structure can't stand without a sturdy foundation).  This became apparent almost immediately after beginning the Rails Portfolio Project.  One of the project's requirements was to use an external provider for user authorization in addition to our standard sign-up/log-in process.  Having just completed the lessons on OAuth, this should have been a very simple task.  Despite only requiring simple authorization from just one provider, I wanted to try one of the magical gems for Rails!

Enter, Devise.  Devise is a widely-used, recommended, authorization gem for Rails that is supposed to simplify the integration of different authorization providers, or strategies, into your app.  That sounds great! So, what was the problem?  Much like the Rails generators, Devise is overkill for the extremely (relatively) simple apps we were assigned to make for this project.  The moment I installed Devise was the moment my app no longer seemed like my own.  With a plethora of new Devise Controllers, views, initializer, routes, etc. I was quickly in over my head.  The project's one-provider authorization requirement paled in comparison to the power, capability, and complexity that just invaded my humble app.

Determined to make it work, I spent just as much time, if not more, disabling/removing unused Devise features than I did on the functions of the app itself.  Over time, the more Devise code I peeled away, the more recognizable my program became.  In hind-sight I probably should have just started over, sans-Devise, however the time I spent debugging errors and trying to understand what exactly this powerful gem was doing was definitely not time wasted.  Through the backwards approach of *removing* code to reach the underlying program, I believe I now have a much better understanding of user authorization and the integration of external provider strategies.  One thing is certain:  "Rails Magic" definitely comes with a few catches.



