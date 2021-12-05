# New Spot


On its face, New Spot seems difficult, but as we’ll find out, it’s a rather textbook recon problem.

## Givens 
Let’s begin with outlining our given information:
* We know his name is Vadder Casyn. With a small bit of effort, we can google his name and get a LinkedIn (url) that links to his website (url). From here, we can get his interests, job, and where he lives and works:
    * He lives and works in Chicagoland (this description includes his actual hometown of Hammond, Indiana)
    * He works in personal training and has a high interest in nutrition
    * He works for Planet Fitness
* Next, the event: We know that there is an event in his area that reoccurs, with no cost, related to his interests and ran by his friend.
* Finally, we know that at some point, we need to jump to Instagram.

This givens don’t seem like much individually, but they actually give us a wealth of information together. 

## Eventbrite

Our first stop is to Eventbrite to hunt down the event. When it comes to trying to find an advertised event, Eventbrite is basically the be-all-end-all for searching in the US: a quick search of event sites and it’ll pop up as the top result. 

We want to search for an event in the Chicago area that’s free. Punch this into the filters. Useful terms for the content search are ‘personal trainer’, ‘nutrition’, or ‘planet fitness.’ Any one of these will instantly drop the results to one clear, obvious event: Chicagoland Personal Trainer and Nutritionist Meeting, hosted by Justin Rodriguez. Its reoccurring, sounds carbon copied from Mr. Casyn's website, it’s even sponsored by Planet Fitness! What are the odds!

![Image](https://cdn.discordapp.com/attachments/315514139491565568/917162612226138172/unknown.png)

And what's this? A convenient address? I wonder where this could lead...

## Instagram

This is where the finsta comes in. With an address and the knowledge that he attends this event, there surely must be some information we can find if we punch in the address to Instagram's built-in search. Sure enough, when you punch in the event's address and look at recent posts, one stands out: This post by 'jrod'. 

![JRod Post](https://cdn.discordapp.com/attachments/315514139491565568/917163367800668160/IMG_8795.png)

Sound familiar? We saw this name earlier as the event organizer, Justin Rodriguez. Wasn't he a friend of our friend, Vedder? I wonder where his post leads us...

Scroll through all the images in this post, keeping a careful eye for content -- and look! The very last post! It tags someone! A Mr. "VC". Sound familiar?

![VC Tag](https://cdn.discordapp.com/attachments/315514139491565568/917163368131993700/IMG_8796.png)
  
Follow through [and we get linked to the key of this hunt, the fabled finsta.](https://www.instagram.com/the_1_and_only_vc/) He only has one post: him at an unidentified location, enjoying the scenery.

![Pic 1](https://cdn.discordapp.com/attachments/315514139491565568/917164659755327508/263788934_602746667630176_4577603561907956396_n.jpg) ![Pic 2](https://cdn.discordapp.com/attachments/315514139491565568/917164659755327508/263788934_602746667630176_4577603561907956396_n.jpg) ![Pic 3](https://cdn.discordapp.com/attachments/315514139491565568/917164660246085723/263796545_424680515913874_7260156234909162154_n.jpg)
## Geolocating a Picture

Here, our recon toolkit should kick in. We have multiple pictures, so what do we do with it? We check it. First, we check for EXIF data. If there's a coordinate attached to it, that'd speed things up big time. Unfortunately, no coordinates, so we're going to have to do this the old fashioned way: identify where the pictures were taken.

Let's go through our given information:

* He's in the Chicagoland area, so the picture must be taken reasonably near-ish to Chicago.
* Our end goal here is to find one address, so these pictures must all be at one address.

How do we turn this into an answer? With some looking!

These three pictures show a pretty big diversity of landscapes. There's a standard tree scene with sidewalks, an open field, and even a waterfront shot! Not many places can have this kind of description. To me, this immediately narrowed the location down to being a park.

From here, I focused on the third picture (the watershot) and what it could tell us

* It was a large body of water, much bigger than a pond. However, we could see the other shore, so it wasn't one of the Great Lakes. This was a picture of a Chicagoland lake that was very big with both shores visible.
* It had a path in front of it. This seems like a minor detail, but it's important! This trail looks well kept. It's thin, only enough for a person or bike, suggesting a pedestrian trail. It had no cracks, potholes, or other visible defects, so it's well maintained, reinforcing that it's a park and also telling us it's likely a major-ish park, not one that's become rundown. It also has a nice curb to it, which helps rule out any parks-with-a-lake-and-a-trail-next-to-it-but-the-trail-has-no-curb.
* The other shore has power lines in the distance.
* It has a small smattering of tiny islands in it. (This is significant because, as a quick glance at Google Maps will show, a lot of the small lakes in Chicago don't have this!)
* The area **is not built up.** Unlike most of Chicago's in-city lakes, there would be a ton of high rises and buildings visible in the background. Here, it's just open sky, so we know we're in the outer edges of the area.

With this information, we have a lot going for us: We want a large lake in Chicagoland (note: Chicagoland isn't just Chicago proper itself, it's Chicago and the surrounding areas!) with islands in it, a pedestrian trail, a wide range of landscape with some forested area nearby, and little build-up. A traipse through Google Maps will find us a lot of lakes that match some of the criteria, but only one really does: Wolf Lake. (It even happens to border Hammond! How convenient!) 

![Lake Wolf Google Maps](https://cdn.discordapp.com/attachments/315514139491565568/917167309225869322/unknown.png)

It's large, it's got a lot of open space around it, it's got recreation -- what else could you need?

From here, it becomes a matter of lining up our shot. Let's pick [here](https://www.google.com/maps/@41.6813338,-87.515885,3a,75y,222.12h,84.62t/data=!3m6!1e1!3m4!1sv6kVuOFKZpTbda81imyy_Q!2e0!7i16384!8i8192), right next to these two islands, circled in blue:

![Google Maps Circled](https://cdn.discordapp.com/attachments/315514139491565568/917167696301412392/unknown.png)

And bam! We have the shot!

![The Money Shot](https://cdn.discordapp.com/attachments/315514139491565568/917167892552896563/unknown.png)

We know exactly where our friend was when this picture was taken. Let's grab the address of this park (Forsythe Park) and throw it through an MD5 hash on CyberChef:

> 1800 Caroline Ave, Whiting, IN 46394
> 
> f77589c3deb4af100c08acc9c1d49036

And that's our flag! Congratulations, you've solved New Spot!
