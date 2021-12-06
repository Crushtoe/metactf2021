# Online Presence

This problem's solution was simple, but getting on the right path to the solution was maybe not. I got a lot of DMs from people asking for hints or talking about their process and asking for hints, and while I only ever directed them to MetaMail, I learned a lot about how people approached and struggled with this problem. In light of that, I'm going to break this write-up into three main sections:

* Reading the Problem
* Getting the Solution
* The Solution

This is because I think, especially in this problem, it's important that one understands the intention behind a problem and what's being hinted at. If one does not understand the clues being given, then they'll end up struggling to solve it, as the dozen DMs I got show. If you want to skip that and go straight to my solution, then go on down to "The Solution."

Ultimately, I conclude with working smarter, not harder, and using a pre-made script to get the job done. If you'd like to see a write-up that goes about this by coding your own solution, see [here](https://github.com/team23ctf/writeups/blob/main/metactf2021/Online%20Presence/Online%20Presence.md).

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
