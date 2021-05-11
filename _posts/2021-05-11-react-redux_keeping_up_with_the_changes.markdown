---
layout: post
title:      "React-Redux: Keeping Up With The Changes"
date:       2021-05-11 22:02:24 +0000
permalink:  react-redux_keeping_up_with_the_changes
---


After finishing the lessons on React/Redux, I felt confident that I was familiar enough with the concepts to churn out the portfolio project with ease.    I started by attempting to set up the directory structure of my program and I was already lost.  The React framework does not give recommendations or best practices regarding directory structure, but rather encourages users to set things up the way they see fit.  The problem was that I had no experience setting up a React app--sure, we came across a few in the lessons, but those were already set up, or instructed us on how to set it up.  I turned to Google to find some more information and was met with an overload of contradicting opinions, new standards, new versions of React, Redux, React-Redux and no single, authoritative source of information.

For someone with only a basic understanding, the lack of uniformity made it difficult to wrap my head around the overall concepts/flow of developing with react/redux.  For example, it seems that right now is a transitional period in the React community.  The more familiar Class components and methods of accessing the store soon felt too restrictive--yet the newer functional components, along with hooks, and the ability to access the store from anywhere felt like a big unknown.  The vast majority of literature/examples that can be found on the internet are for the older Class components--however the most recent tutorials, even on the React-redux site itself, implied that functional components/hooks were the way to go.

A seasoned React developer would be able to see the big picture, and quickly form opinions regarding any new additions to the framework.  They might decide to incorporate something new into their existing workflow, or decide they are better off without it.  Without this experience, I did not have enough background to make those kinds of decisions.  As with most new things in the development world, I had to learn by doing.  Not only that, the multiple solutions I came across to any issues that arose allowed me to create my own workflow with preferences of my own.


As it turns out, I am definitely a fan of using functional components over class components.  Class components began to feel too restrictive, and the easiest solutions to bugs/issues were predominantly made up of functional components/hooks.  When it came to organizing my code, however, I opted for the more familiar separation of actions and reducers instead of creating slices of the state and combining actions/reducers into slice files.  

By launching into the code before I had a solid understanding, I was able to figure out concepts for myself and develop preferences and best practices that suited my own specific workflow.  Now, on the 5th iteration of my project, I am able to appreciate React/redux, and feel much more comfortable developing with this powerful framework.
