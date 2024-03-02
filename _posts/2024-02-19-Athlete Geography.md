---
title: The Geography of Pro Athletes 
author: Ari
date: 2024-02-27 00:34:00 +0800
categories: [Baseball, SQL, Python]
tags: [Useless Baseball Stats]
---

Professional athletes in the US represent over 100 countries, reflecting the patterns of each sports' popularity and historic factors. This map plots the origin of players in the MLB, NHL, NBA and NFL born since 1980. 

<iframe src="/assets/html/sports_births_map.html" width="100%" height="500px"></iframe>

Why use 1980 as a cut off? I'm more interested in the current day geography of athlete origins. It is a somewhat arbitrary cut-off, but at least in looking at baseball, the 1970s is both when the percentage of foreign born players started rising and more players were emerging from the west coast as those population centers grew quickly. 

Looking at this data, there are a few things I didn't expect. The lack of baseball players from Jamaica is something I haven't noticed before, but perhaps that shouldn't be surprising due to their British colonial history. Cricket, after all, is popular in Jamaica.

One surprise to me is the lack Norwegian-born hockey players. Scandinavia is well known as a hockey-haven, so why does Norway lag behind Sweden and Finland? Geography might be the simple answer here. Norway is much more mountainous than Sweden and Finland. Norwegian-winter sports are mainly performed on skis and perhaps their would-be hockey talent hit the slopes growing up instead of the ice. 

And here's the breakdown of all athlete origins by sport and country. The US still dominates baseball, basketball and football, but there have been almost twice as many hockey players born in Canada than in the US since 1980. Now I wonder what it would look like ranking "success" by country of origin. Is it harder to land a contract as a foreign-born player and therefore only the truly exceptional foreign athletes make it to the US? 

<iframe title="Pro Athlete Origins Since 1980" aria-label="Stacked Bars" id="datawrapper-chart-tUI9E" src="https://datawrapper.dwcdn.net/tUI9E/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="2998" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r=0;r<e.length;r++)if(e[r].contentWindow===a.source){var i=a.data["datawrapper-height"][t]+"px";e[r].style.height=i}}}))}();
</script>