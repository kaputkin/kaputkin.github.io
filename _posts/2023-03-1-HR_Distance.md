---
layout: post
title: "Baseball Hit Distance Bot"
author: ""
categories: posts
tags: [baseball]
image: baseball.jpeg
---

The birth of a new baseball statistic. Through the magic of Statcast, a combination of cameras and radars mounted around baseball

I thought about also including foul balls in this metric, inspired by Anthony Rizzo's habit of blasting 400 foot foul balls down the right field line, sometimes multiple times per at bat. Would including all batted balls, fair or foul, make this a more meaningful stat? I suppose it could  if this is just a proxy for how well a player is squaring up to the ball. 

The bot itself is written in R and scrapes Statcast data from BaseballSavant every day at 6am. Hit Distances are tallied daily per player and the top ten by total distance for the season are graphed. 


<a class="twitter-timeline" data-width="800" data-height="800" data-theme="dark" href="https://twitter.com/howfartheball?ref_src=twsrc%5Etfw">Tweets by howfartheball</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

{{ twitter_widget_code | sanitize }}