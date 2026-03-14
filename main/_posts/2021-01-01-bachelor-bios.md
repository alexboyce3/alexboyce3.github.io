---
layout: post
title:  "Who Will Win Season 25 of The Bachelor?"
date:   2021-01-01
categories: 
---

Tomorrow night marks the premiere of the quarantine season of The Bachelor, and the first with an African American lead, Matt James. After the premiere, fans (including myself) will anxiously discuss who could and should win. But super fans have already been introduced to this years contestants, through the [official bios on the ABC website](https://abc.com/shows/the-bachelor/cast). When released, podcasts like [Bachelor Party](https://www.theringer.com/2020/12/17/22180056/meeting-the-women-from-matt-jamess-season-plus-blueberry-bagelgate) dissected them in incredible depth. 

And it all made me wonder whether I could predict who will go far on the show before seeing any of the season. After all, these bios are probably written by people who have knowledge of the season's outcome. While they won’t outright tell us who wins, they might be slightly guiding us to view some contestants more favorably than others.

![logos-unknown]({{ site.url }}/images/bachelor/bach2.png)

## The work

So that brings us to today, where I’ve analyzed the words used in bios of the previous 4 seasons (it’s increasingly challenging to find these bios the further back we go) and built a model to predict future contestant performance.

Of course many caveats apply:

* In two seasons (Arie & Nick), bios were in the form of explicit Q&A. In more recent seasons (Colton & Peter), these questions likely still exist but are now used to write narrative bios with more flair.
* Bios have more than doubled in length over the previous two seasons - until Peter's season they were 400-500 words. With Peter and Matt, they are now over 1,000 
* As the first African American bachelor, Matt’s contestants are considerably more diverse than past seasons. This possibly means different word usage as pointed out on that Bachelor Party pod (for example, soul has been used in 5 bios this year vs just one in the previous 4 seasons) 
* This sample size is very small and leads to an overfit model! This was a bad idea!


All that said, here's what I did:

* Found all words that appeared at least 5 times in the previous seasons' bios. For the sake of this exercise different forms of a word, such “travel”, “travels”, and “traveling”, are considered the same word.
* For each word and each contestant with that word in their bio, calculate the average week that the contestant's reached in the season (10 weeks per season).
* For each contestant, average the scores of each word they have in their bio.
* There is some additional info we have on the women: age and job title. Those are incorporated into regression models along with the biography score calculated in the previous step. (While we also know the race of contestants, and that this franchise has a spotty history when it comes to race, I did not include that as a variable here).
* Using this framework, predict elimination week and whether a contestant will reach hometowns (the final 4 contestants) 
* Rescale scores of both models, average them together, rank, pick the final 4 (..., profit?)

![logos-unknown]({{ site.url }}/images/bachelor/bach3.png)

## The Results 

For past seasons, this model does ok! It picks about 2 of the 4 correctly for Arie, Nick, and Colton, including the winners (and 2 runners-up). 

But when the bios got longer in Peter's season, things got really good. This predicts 3 of the final 4, with the "villain" of the season as the only miss. Even better, the mis-pick in the top 4, Kelley, is the one Peter eventually ended up dating months after the season ended. So this gives me hope for Matt James' predictions! 

![logos-unknown]({{ site.url }}/images/bachelor/bach4.png)

There are some pretty bad misses though. The model really liked Liz's bio on Nick's season, where she talked about family and her passion for her job. And then womp she flopped in week 2. More egregiously was Tracy on Colton's season, who talked about her career, sister, AND travel. The trifecta.


Before we get to the main event, let's take a quick diversion to the top and bottom words: 

![logos-unknown]({{ site.url }}/images/bachelor/bach5.png)

From this, it seems like women who are described as career-oriented, intelligent, loyal, like to travel, and have sisters have gone far in recent seasons. On the other side, those whose profiles reference more hobbies, talk about marriage, or have brothers bow out early. Of course we shouldn't assume that these words reflect reality either. Or maybe it's just that women with brothers scare the bachelors away because they're afraid of getting beat up.


Finally, my predictions for Matt’s final 4. Spoiler alert(?) 

![logos-unknown]({{ site.url }}/images/bachelor/bach6.png)

After reviewing the actual bios of everyone, these feel like good picks! But Matt James is a complete unknown, having never been on any Bachelor shows, so it's hard to say who he'll go for. If I had to pick a winner from this group, I’d go with Khaylah - Magi is a bit too old (very rare for Bachelor's to pick older women), Serena C is a bit too young, and Khaylah's job in healthcare advocacy feels like a better fit with Matt's work starting a non-profit food organization than Chelsea's modeling career.


Is any of this right? Was it just a colossal waste of time? Probably yes to both! I'll try to remember to post an update here when the season ends in March.