---
title: Baseball's Best Day
author: Ari
date: 2024-02-21 00:34:00 +0800
categories: [Baseball, SQL, Python]
tags: [Useless Baseball Stats]
---

Superstition rules baseball. Rituals and routines come in many forms with players, managers, coaches and fans all taking part. When batters string together a few hits you can bet there is a superstitious habit formed to preserve the streak. Even more so when trying to break a slump. Aaron Judge reportedly will chew two pieces of double-bubble before his first at bat, and if he gets a hit, he keeps it until he doesn't, then it's time for a new chew. 

Some days are just good days, and some days are just bad days. But what about birthdays? Are there any players that have performed exceptionally well on their birthdays? One way to get at this is simply looking at batting average on a players birthday throughout their career. 

Warren Cromartie takes the cake on this one. Cromartie, once a popular Expos outfielder and later the 1989 MVP in Japan's NBP league, played four times on his birthday going 7 for 12 for .538 average. Only 21 players in MLB history who have at least 10 at bats on their birth have hit over .500 those days. 

### Best Birthday Batters

<iframe title="Best Birthday Batters " aria-label="Table" id="datawrapper-chart-gEbJx" src="https://datawrapper.dwcdn.net/gEbJx/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="1246" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r=0;r<e.length;r++)if(e[r].contentWindow===a.source){var i=a.data["datawrapper-height"][t]+"px";e[r].style.height=i}}}))}();
</script>

What about other days? Do some players just have a special day that they have performed exceptionally well? No one who has played at least five games on a particular day is batting 1.000 on that day, but there are some stand outs. Ketel Marte is 14-21 for a .667 average on Just 20th. Hall-of-Famer Frankie Frisch, who emerged in 1919 and played 19 season, certainly has a special day. Over 42 at bats on June 9th, Frisch batted .643. 

### Notable Good Days



| Who? | When?  | H/AB | Average |
|--|--|--|--|
| Frankie Frisch | June 9s (1919-1937) | 27/42 | .643 |
| Ketel Marte | June 20s (2015-2023) | 14/21 | .667 |

How about exceptionally bad? There are 108 players in MLB history, who have had at least 20 at bats on a particular date throughout their careers but never had a hit that day. Nomar Garciaparra is 0-34 on July 15th throughout his 14 year career (some of those games were all-star games).


Thanks to the incredible baseball.computer project for access to the stats. The query is set up to pull every at bat a player had in their career and then group by the month and day. The baseball.computer database makes this easy. 

SELECT
	 a.first_name,
	 a.last_name,
	 a.player_id,
	 a.month,
	 a.day,
	 a.total_hits,
	 a.total_at_bats,
	 a.avg,
	 b.birth_city,
	 b.birth_country,
	 b.birthdate
FROM
	(SELECT
		  p.first_name as first_name,
		  p.last_name as last_name,
		  p.player_id,
		  EXTRACT(MONTH FROM g.date) AS month,
		  EXTRACT(DAY FROM g.date) AS day,
		  SUM(m.at_bats) AS total_at_bats,
		  SUM(m.hits) AS total_hits,
		  SUM(m.hits) / NULLIF(SUM(m.at_bats),0) as avg
		FROM player_game_offense_stats AS m
		JOIN people AS p USING (player_id)
		JOIN game.games AS g USING (game_id)
		GROUP BY p.first_name, p.last_name, p.player_id, month, day
		HAVING SUM(m.at_bats) >= 20
		ORDER BY month, day ASC
	) AS a
JOIN misc.bio AS b ON a.player_id = b.player_id
ORDER BY avg DESC;

