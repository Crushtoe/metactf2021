# Online Presence

This problem's solution was simple, but getting on the right path to the solution was maybe not. I got a lot of DMs from people asking for hints or talking about their process and asking for hints, and while I only ever directed them to MetaMail, I learned a lot about how people approached and struggled with this problem. In light of that, I'm going to break this write-up into three main sections:

* Reading the Problem
* Getting the Solution
* The Solution

This is because I think, especially in this problem, it's important that one understands the intention behind a problem and what's being hinted at. If one does not understand the clues being given, then they'll end up struggling to solve it, as the dozen DMs I got show. If you want to skip that and go straight to my solution, then go on down to "The Solution."

Ultimately, I conclude with working smarter, not harder, and using a pre-made script to get the job done. If you'd like to see a write-up that goes about this by coding your own solution (or just less of a lesson on recon), see [here](https://github.com/team23ctf/writeups/blob/main/metactf2021/Online%20Presence/Online%20Presence.md).

## Reading the Problem

### Description

> Sources say Vedder may have used Reddit the past two weeks. It would make sense for him to post some comments on some major subreddits related to his main career interests or near his local area. Can you help find his account?

> The answer format is the username followed by the post ID and comment ID in the URL to their shortest comment, underscore delimited. For example, for this comment, the answer would be MetaCTF{Specialistimran_r5mmdj_hmnszk4}.

> Hint: There's a logical way to solve this challenge that doesn't require much time. There are two major (both have 500k+ subscribers) work-related subreddits.

*Note: The original posting of this problem only specified "a few weeks" instead of "two weeks," nor the information about the number of work-related subjects or the subscriber count to them. The problem could (and was!) solved without this information.*

### Givens of the Problem

Let's list out what this problem tells us outright:

* We're looking for a reddit user account. (It might sound silly to bother stating this to yourself, but losing track of your end goal wouldn't be good, would it?)
* This account has posted in the last few weeks. This gives us a date range.
  * Specifically, with the extra information from the problem update, within the last two weeks! This gives us an even better date range!
* He posts comments in subreddits related to his main career interests and his local area.
  * Specifically, with the extra hint information, we know that there's two work-related subreddits, and both have over 500,000 subscribers. This gives us a solid foundation of subreddits to search for and criteria to confirm or reject any guess subreddits. (For instance, /r/personaltraining has only ~19,000 subscribers, so it falls off the radar as a work-related.)
* We also want his shortest comment. This means, whatever his account is, it shouldn't be too hard to find the shortest comment. We won't quite know what this means until we get there, but it shouldn't be an onerous task.
* "There's a logical way to solve this challenge that doesn't require much time." This doesn't mean too much, but we'll keep this in mind for later. Maybe it'll help us decide a method we try is too long-winded?

And that's our givens! Now, let's see what extra information we can find that'll help us explain some of these givens and how they can help us.

### Info-hunting 

To really make this possible, there's two big things we want to try and find: his career interests and his local area. Other information that crops up, we'll make notes of as well, just in case.

We know his name is Vedder Casyn. With a small bit of effort, we can google his name and get a [LinkedIn](https://www.linkedin.com/in/vedder-casyn) that links to his [website](https://veddercasyn.me/). From here, we can get his interests, job, and where he lives and works:
    * He lives in Hammond, Indiana, meaning his homestate is Indiana!
    * He works in Chicagoland, meaning he's involved with the Chicago metropolitan area.
    * He works in personal training at Planet Fitness. 
    * He's obsessed with nutrition advice.
    * He does first-aid.

This is a good chunk of information that should help us narrow down who he is on reddit. From here, we can go ahead and begin trying to find out how to find the solution.

## Getting the Solution

We now know Vedder's interests, his local area, and our goals. Now, we need to figure out how to get from his interests to finding him. As I see it, there's two things we can do:

* Search subreddits related to him for keywords related to interests, find the users who post these keyword messages, and check them for what other subreddits they browse until we find one who matches our profile of Vedder.
* Find users who post in multiple subreddits we can predict that Vedder posts in, and check their accounts to see if they match Vedder's profile.

Each of these has pro's and con's. Keyword searching requires very little in the way of specialized scripts or programs: all you need is to google 'site:subreddit.reddit.com "keyword"', a list of keywords you'd relate to his interests, and time. Infact, if you're lucky, you might not even need to specify a subreddit! How many people possibly post about Hammond, Indiana, Planet Fitness, and nutrition?

On the flipside, keyword searching requires getting just the right keywords. Imagine if instead of talking about Hammond, he just mentions Chicagoland on reddit, or instead of nutrition, he talks about diet. Getting the right keyword is difficult. And if you think about it, what are the odds he actually uses keywords? How often do you really speak in buzzwords related to your work or career online, and how often do you just make vague comments in that direction? I never mention my university online, for instance, just that I attend one. Keyword searching for my reddit based on knowledge of my real life wouldn't go far. How far will it go with Vedder?

What about subreddit correlation? It sounds nice! We know information about the kinds of subreddits he posts on and have very different types, which means little extraneous correlation. There might be a lot of users who post on both /r/Chicago and /r/Illinois, for instance, but how many people post on both /r/Chicago and /r/Fitness? The more subs we correlate, the better we can do. This has the potential to be very efficient!

The downside, of course, is execution. How do you go about this? Reddit has no built-in method of doing this, there's no easy reddit-related website that'll correlate users who post on two subreddits for you, and while you could code it yourself, this'll be difficult and requires a lot of skill. We want to work smarter, not harder, and time spent coding is time spent not doing other challenges. We could manually comb subreddits, but this is onerous, too.

So, what is one to do? My answer was to cheat, and try both, seeing how well each works.

As it turned out, keyword searching was difficult. No clear accounts pop up. Vedder seems to be an illusion, distant in the wind. No clear 'personal trainer planet fitness nutrition hammond chicago' keyword buzzword soup man existed. 
   
That leaves us, of course, with the route I went by for the solution: subreddit correlation. 

## The Solution

There are two ways to go about subreddit correlation: manually going subreddit-by-subreddit and checking each user you see to find out if they also post in another subreddit related to Vedder, or doing it with a script.

I hope it's clear why the first one is a 'bad' solution: it's time-consuming, prone to error, and with the work-related subreddits having 500,000+ posters, this can get overwhelming. It's worth noting this solution isn't *impossible*: I heard multiple teams say, after-the-fact, that they did find Vedder's account using this method. The trouble they had was, because they combined this technique with keyword correlation. When you have 100,000+ comments to comb through, many of them one sentence long, you get desparate for an easy way to cut through the crud: disregarding comments without relevant content is one, and every team I heard from that found his account through manual hunting said they disregarded him when they found him due to a lack of content per comment. It is a flawed method.

This leaves us with a script. As I mentioned above, [there's a write-up available here that focuses on how to solve this by writing your own script.](https://github.com/team23ctf/writeups/blob/main/metactf2021/Online%20Presence/Online%20Presence.md) However, I personally object to this approach: It's a lot of work, and I like to see if other people have already done that work for me. This is Recon, after all -- isn't scouting the field part of the game?

Googling "reddit find user who posts in two subreddit" gives us, pretty immediately, a script worth looking at.

![Google Result](https://cdn.discordapp.com/attachments/315514139491565568/917327646164156496/unknown.png)

As it turns out, Watchful1, maker of RemindMeBot and dozens of other amazing scripts, already went through the effort of making this script: It finds overlapping users between specified subreddits in a certain date range and saves a .txt file of them, including those who were in all specified subreddits, all but one, and even all but two. (Isn't that lovely? A safety net! Even if we over-specify, as long as we didn't get our subreddit guesses *too* wrong, we can still get the answer!)

That script is available [here.](https://github.com/Watchful1/Sketchpad/blob/master/overlapCounter.py)

With this, we can find Vedder in a matter of minutes, and we don't even do the heavy lifting!

All we have to do is input a time range (we'll say 14 days, for two weeks), subreddits to look at (ones I concluded were relevant were /r/Chicago (since he worked in Chicago), /r/Indiana (since Hammond didn't have a subreddit), /r/ChicagoSuburbs (since, again, Hammond didn't have a personal subreddit and it was a suburb), and /r/Fitness (since he works for Planet Fitness and does personal training), and boom, run it in your Python 3.10 IDE of choice.

I set the script to check 'Indiana' and 'Fitness' over the span of the last fourteen days, and to dump into a file named users.txt. (I could've gone with any combination of my handpicked subreddits, as it turned out, in addition to /r/nutrition -- these are just the two I went with on a whim to correlate location and career.)

```python3
import requests
from collections import defaultdict
from datetime import datetime, timedelta
import time
import os
import json

subreddits = ['Indiana', 'Fitness']
ignored_users = ['[deleted]', 'AutoModerator']
lookback_days = 14
min_comments_per_sub = 1
file_name = "users.txt"
```

Within 15 minutes, it spat out the following two users: 

Dptwin
dtdnumberone

Dptwin actually fit the bill pretty well - Chicago, Indiana, Battlefield, Fitness, HealthyFood -- what didn't the guy match? That said, he was also a bit of a character if you read his comments, so for now, let's skip over him and check out the other one. We have two results, it's going to be one of them, why not?

![Bingo.](https://cdn.discordapp.com/attachments/315514139491565568/917330144094470144/unknown.png)

Bingo.

A small number of posts that's easily searchable through for the shortest comment, talks about all the right stuff, obsessed with berries, no controversial statements, conveniently created two days before the competition began, what a man! This is our guy. From here, it's a matter of finding his shortest comment:

![Comment](https://cdn.discordapp.com/attachments/315514139491565568/917330644403650610/unknown.png)

And plugging it all into the flag format, as we were told:

```
MetaCTF{dtdnumberone_r4rant_hmqpa52}
```

And that, my friends, is Online Presence solved.


---

*I hope this was useful for explaining how one not just solves the problem, but figures out **how** to solve the problem. If you have any questions, don't hesitate to reach out and DM me.*
