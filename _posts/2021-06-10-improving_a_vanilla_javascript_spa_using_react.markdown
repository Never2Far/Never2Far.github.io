---
layout: post
title:      "Improving a Vanilla JavaScript SPA using React"
date:       2021-06-10 18:08:31 +0000
permalink:  improving_a_vanilla_javascript_spa_using_react
---

In the spirit of always learning and improving my skills, for one of my first post-graduation projects, I will be improving the [Component Calculator](http://www.near-net.com) app I made for the JavaScript Portfolio Project. (knowledge of circuit-boards is not necessary for the purpose of this post, however if you are curious look [here](https://en.wikipedia.org/wiki/Electronic_color_code)

If you visit the app, the first thing you might notice is the delay before the site's content (colorful bars) loads, or if you're (un)lucky it might not load at all (a page refresh usually fixes this).  When I created the app, I was not very familiar with sync/async concepts so I used timeouts to ensure the content fetched from the server did not arrive before the containing HTML loaded.  While developing the app on my local computer, fetches from the server took milliseconds (it didn't have very far to go) which explains why it might come in before a plain HTML page loaded.  After deploying the app on Heroku, however, the time varied with each load of the page. Having just completed the React/Redux Portfolio project, I knew just how to fix this.

## React to the Rescue!

Aside from fixing the load time issue mentioned above, React is great for logically organizing code, and keeping it DRY (Don't Repeat Yourself).  The building blocks of a React app are called '**components**', which are portions of code that can be re-used throughout the app.  

### But wait...

Anyone with even the slightest experience with React might already see the problem -- The calculator I created is used for determining the values of certain electrical **components** (think resistors, capacitors, etc.).  Without any previous knowledge of React, I unwittingly used one of, if not the, most used word in the React universe.   Face, meet palm.  As far as I can tell, 'Component' is not actually a reserved word in React JS, however to avoid future confusion, I renamed the app, "Resistor Calculator" (while it is possible to use the app for other electrical components, the color-coding system is used predominantly for resistors.).

Armed with new knowledge and a new name, I am ready to start working with some code!  In my next post I will be describing the initial set-up of a React app and how it compares to the directory structure of my original app.  Stay tuned...
