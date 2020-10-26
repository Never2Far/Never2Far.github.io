---
layout: post
title:      "Using Entity Relationship Diagrams to untangle ActiveRecord Associations"
date:       2020-10-26 16:04:19 +0000
permalink:  using_entity_relationship_diagrams_to_untangle_activerecord_associations
---




For the Sinatra portfolio project, we were tasked with creating an MVC/CRUD application that "keeps track of things"  for a user (like a Content Management System, or CMS).  Like with all new apps, I began by brainstorming different "needs" a user might have that could be solved with my app.  As i flipped through ideas, the management of some type of collection seemed to be a natural use for a CMS.  My eyes settled on the binders of Baseball cards I have taking space on a shelf.

I began thinking about how i might model baseball cards--"A baseball card has a team, a player, a position, etc."  As i thought more about a Baseball Card domain, I noticed that the models I was coming up with did not have to be specific to Baseball cards, but rather could be extended to any of the other sport card collections that were also resting on my shelf.  So now, "A user has sport card collections that each have a sport, which has teams, players, and positions, etc."  Because sports are already such a defined/organized topic, i figured it would be an easy domain to model.  Once I had some model names "stubbed-out", I began thinking of the relationships, or associations, that would be required to connect them all.  A tangled, convoluted, mess of incorrectly defined associations soon followed.

Re-reading the project prompt, and thinking back to the newly introduced concept of an MVP (Minimum Viable Product), I decided that this project's designer(s) probably had something a little simpler in mind--at least to start off with.  By this point, however, my Engineering background took over and I was already fully invested in solving/sorting out the mess I had begun.

My biggest challenges at that point came from my unclear understanding of the difference between a "has_one" and "belongs_to" association, and which model received the 'foreign key.'  Also, in order to accomplish the types of actions I had in mind for my app, my models had to be associated in almost every way possible (think "through:", and join tables).  It was actually a *Baseball* Card I have of Michael Jordan when he played for the Chicago White Sox that kept tripping me up. (A player can not only belong to many teams throughout their career, but even many sports!)

The number of models I had continued to increase, while my grasp of their relationships and the  "whole picture" decreased.  I experimented using the Tux gem, and after not achieveing the behavior i had in mind I soon hit a brick wall.  I needed a way to *visualize* this web of associations.

Enter the Entity Relationship Diagram.

I searched the internet for a way to visualise my Sport Card domain, and quickly hit upon the concept of an ERD (Entity Relationship Diagram).  More specifically, I found the ['rails-erd' gem by github user voormedia](https://voormedia.github.io/rails-erd/) .  This gem is primarily meant for Rails applications, however the install documentation provides instructions for installing/using the gem outside of rails as well.

This gem spits out a PDF visualization of your domain's associations, but I was pleasantly surpirsed to find that this wasnt even the most useful feature.  When running the command to generate an ERD, the rails-erd gem intelligently finds errors/discrepencies/missing dependencies within your domain models and provides suggestions right in the terminal!  For example, using the messages in the terminal, I discovered that i was missing a model that connected a team with a player--this necessitated the creation of a join table, team_player, otherwise known as a contract.  (A player can have many contracts over their career, with many teams (and therefore many sports)--solving my issue of Michael Jordan's short foray into baseball.)

[Here](https://user-images.githubusercontent.com/30479783/97195646-96000f00-1779-11eb-90d8-218c84fb017c.png) is an example of an ERD generated using this gem.
![erd](https://user-images.githubusercontent.com/30479783/97195646-96000f00-1779-11eb-90d8-218c84fb017c.png)

Using this gem and the generated ERD's, I was able to successfully untangle the mess of associations i had previously created.  Now that I was achieving the desired behavior while testing the domain using Tux, I was free to move on with the "V and C" (views and controllers) portion of my app.

If you are having trouble understanding or getting your domain's associations just right, I highly reccomend checking out the rails-erd gem!


