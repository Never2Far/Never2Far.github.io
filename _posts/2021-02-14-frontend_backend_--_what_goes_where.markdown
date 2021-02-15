---
layout: post
title:      "Frontend, Backend -- What goes where?"
date:       2021-02-15 01:53:06 +0000
permalink:  frontend_backend_--_what_goes_where
---


I began the Javascript Portfolio Project by following the provided guide for setting up the structure of a JavaScript/Rails application.  Everything was going smoothly--I created a new Rails API-only application in my 'backend' directory, and added the necessary files (html, js, css) to the frontend directory.  At this point, nothing was app-specific, meaning I was simply setting up a blank structure.  

After figuring out what kind of app I would make for this project, I went full-steam ahead and, on autopilot, created models, contollers, associations--everything to build a good Rails app.  But this wasn't meant to be a Rails-only app!  When I normally would have started setting up my views, I switched gears and flipped over to the front-end directory.  Having just completed lessons on Object Oriented JavaScript, I confidently began creating classes, grouping related logic/functions, etc. until it suddenly dawned on me:  I was re-creating alot of the behavior I had just added to my backend!

This realization quickly put an end to my cruise-control, and I took a step back.   Many of the things I was trying to achieve could be carried out by either the front, or the backend.  But what was supposed to go where?  I thought back to the lessons and remembered asking myself that same question multiple times.  I knew what *could* be done, and how to do it, but I didnt know what *should* be done.  I tried taking the easy way out and searched things like "rails, javascript, what goes in frontend, what in backend" but I didnt get that lucky...

I decided to go back to my code and start with what I *knew* was definitley supposed to happen in the frontend -- anything related to views, fetch calls to the server, DOM manipulation, etc.  I found myself steadily removing things from the backend, undoing much of what I started off coding!  After a while, I took a step back again and looked at my work.  I was definitely starting to catch-on to the strategy of separating backend/frontend concerns.  I continued working on my app, and everything just fell into place.  My backened was extremely slimmed-down.  My initial 5 models, became just 2!  My controllers looked neat and bare--facilitating the role of middle-man between the database and the code.  My JavaScript classes contained all of the view-logic, and after drying things up and removing extraneous comments, I finally had the answer to my initial question.    What goes in front, and what goes in back?  Just start coding and the concepts will fall into place.  This was definitely a 'learn-by-doing' concept, and I am greatful for the mistakes that I made along the way that helped to solidify my understanding.
