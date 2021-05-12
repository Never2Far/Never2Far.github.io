---
layout: post
title:      "Chaining API's or Scraped Sites"
date:       2021-05-12 03:25:57 +0000
permalink:  chaining_apis_or_scraped_sites
---


For the CLI portfolio project I decided to make a simple CLI weather app using the National Weather Service (NWS) as a data source.  The NWS provides an API that accepts coordinates (lat. & long.), and returns the name of the weather grid that encompasses that location.  Using a separate endpoint from the NWS API, that weather grid can then be used to find various types of weather forecasts for that area.  Seems simple enough, but there's one problem: How do I find the coordinates of the location I’m trying to get a forecast for? The NWS API does not have that functionality.

That process (converting an address to coordinates) is called geocoding, and it just so happens there are several API's available for this exact task!   I naturally attempted to use Google Map's API, however as far as I could tell it was not free.  MapQuest’s geocoding API, on the other hand, is definitely free to use and proved to be easy to work with.  The MapQuest API accepts almost any search term, and spits back the coordinates of the location it believes you are searching for.  The search function turned out to be extremely accurate, even with only partial information to search with.  Now that I have a way to get coordinates for a location, I just need to hand them off to the NWS API to get a forecast.

Ruby to the rescue!  The weather app queries the user (via the CLI) for a location, and then hands off the search text to MapQuest’s API.  The MapQuest API then returns the search result, and the user is asked to confirm that the location is in fact the location they were looking for.  Next, the app takes the location's coordinates from MapQuest’s answer, and uses them to query the NWS's API.  The NWS API returns the name of the weather grid encompassing the given coordinates.  Finally, the name of the weather grid can be sent to one of a few NWS endpoints corresponding to the type of forecast being requested (summary, hourly, 3-day, etc.).  A forecast is retuned and displayed for the user on the CLI.
