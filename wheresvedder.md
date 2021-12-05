# Where's Vedder?

This is a pretty simple location identification problem. In this write-up, we'll solve this by outlining our given information, seeing what extra information about Vedder we can gather, and analyzing the photo for more clues. Finally, we'll combine what we've found to resolve the problem in a (hopefully) fast and simple way.
## Description

>Please help find our dear friend Vedder Casyn. His last known location was this location. We believe it's within a public forest area in his home state.

>The answer should represent the MD5 hash of the address of the location. For example, if the address is: "150 Greenwich St, New York, NY 10006" then the flag will be e8244cb2f4d53117e9797af909123e86. Make sure to have the address format the same as above. 

## Givens 

Let's make a list of all the given data we have that can help us find the location where this picture was taken!
* We know his name is Vedder Casyn. With a small bit of effort, we can google his name and get a [LinkedIn](https://www.linkedin.com/in/vedder-casyn) that links to his [website](https://veddercasyn.me/). From here, we can get his interests, job, and where he lives and works:
    * He lives in Hammond, Indiana, meaning his homestate is Indiana!
* We know this photo takes place in his homestate, which we already identified.
* We know the photo was taken within a "public forest area."
* Finally, we have the image that he took at the given location:

![location.jpg](https://metaproblems.com/f7ded7cf8ebd4fd47e2311ec1bee293f/location.jpg)

That's all our given information. Let's see what we can determine from the photo itself.

## Photo Analysis

Let's look over the photo and see what we can possibly identify:

* **The Funeral Home** -- On the right of the photo is a rather unique building. It's got a rather nice front with a pillared entrance, a window over the doorway, a carport on the right side -- it reminds me of funeral homes I've visited in my life. And what's this? Two hearses in the carport, all black? By Jove, that *is* a funeral home! This'll help narrow down the search nicely.

![I Got The Hearses In The Back](https://cdn.discordapp.com/attachments/315514139491565568/917190849446690836/unknown.png)

* **The Trees** -- In the background, we see some rather tall trees. I'm not quite sure the species, but it's something very tall, with few far reaching branches, and rather thin. A pine, maybe a birch or spruce? The exact species doesn't matter, but knowing the *look* of the forest does, and now we can see the forest for the trees.

![The Forest For the Trees](https://cdn.discordapp.com/attachments/315514139491565568/917191528567439360/unknown.png)

* **The Other Building** -- This one offers us little useful detail. It's a long but otherwise unassuming building with a lot of stuff out front. Probably residential, but that doesn't help narrow things *too* much, besides telling us it's a kind of shotgun house area.

![The Other One](https://cdn.discordapp.com/attachments/315514139491565568/917192763244699708/unknown.png)

* **The Street** -- This one is a bit of a stretch, but I find it useful to know. A quick glance at the street shows it's paved, with a shoulder and painted lines on the side. This won't help pin down the locations to guess much, but when we do start guessing, it might help a lot to know if the road we picked is the right one by the shoulder and striping. (A lot of roads in Indiana's forests, as it turns out, lack this.)

![The Road](https://cdn.discordapp.com/attachments/315514139491565568/917192640431276142/unknown.png)

Other than random street garbage (which I did try to identify in vain), there's nothing left to analyze. Let's get to striking off search areas now that we have this info!

## Narrowing Search Areas

As of now, our search area is: Every public forest area in Indiana, and our target is: a funeral home. This is kind of a wide net to cast. It'd help if we could narrow down forests, like maybe if we knew what the trees in that forest looked like...

Oh wait!

[A quick trip to North Indiana](https://www.google.com/maps/@40.8214204,-85.3609935,3a,75y,148.07h,90.63t/data=!3m7!1e1!3m5!1sgWr3VXs28JU7oFDpc0IAEg!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fpanoid%3DgWr3VXs28JU7oFDpc0IAEg%26cb_client%3Dmaps_sv.tactile.gps%26w%3D203%26h%3D100%26yaw%3D309.84424%26pitch%3D0%26thumbfov%3D100!7i13312!8i6656) finds there aren't many public forests. What we do have is in fish and wildlife areas, and, well, the forests are... sure something.

![Wow. Something.](https://cdn.discordapp.com/attachments/315514139491565568/917193953101623356/unknown.png)

A quick trip to South Indiana, meanwhile, shows [forests that resemble our search goal. Tall, dense trees, set a ways back from the road.](https://www.google.com/maps/@38.4169464,-86.4501192,3a,75y,124.02h,88.4t/data=!3m7!1e1!3m5!1sRHcIu630LTqTrvcV-vkJbA!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fpanoid%3DRHcIu630LTqTrvcV-vkJbA%26cb_client%3Dmaps_sv.tactile.gps%26w%3D203%26h%3D100%26yaw%3D278.72278%26pitch%3D0%26thumbfov%3D100!7i13312!8i6656)

Great! We've reduced our search area to the forests of South Indiana! That gets rid of half the state. From here, let's take advantage of the fact that we know the picture was:
* Taken within a public forest area.
* Of a funeral parlor.

How many funeral parlors can there possibly be *within* a forest?

For me, it took three forests to get it right. I went on Google Maps, zoomed in over a state or national forest, searched for funeral home in the bar, and looked at what popped up. The first two had a lot of results, but all on the edges of the parks. Nothing quite seemed obvious enough. Maybe Hoosier National Forest?

![Bingo Image](https://cdn.discordapp.com/attachments/315514139491565568/917195188760375316/unknown.png)

Bingo. Dead in the middle of a forest. NOw let's street view down to it and see how it looks...

[Gentlemen, we got him.](https://www.google.com/maps/place/Denbo+Funeral+Home/@38.3510849,-86.4524429,3a,75y,307.15h,90t/data=!3m7!1e1!3m5!1sMZniiDB2bSzbzSZPdutz6Q!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fpanoid%3DMZniiDB2bSzbzSZPdutz6Q%26cb_client%3Dsearch.gws-prod.gps%26w%3D86%26h%3D86%26yaw%3D307.14664%26pitch%3D0%26thumbfov%3D100!7i16384!8i8192!4m9!1m2!2m1!1sfuneral+home!3m5!1s0x886eba293ff848ad:0x7bee6830f8e3a797!8m2!3d38.3513035!4d-86.4528092!15sCgxmdW5lcmFsIGhvbWWSAQxmdW5lcmFsX2hvbWU)

![Denbo Funeral Home](https://cdn.discordapp.com/attachments/315514139491565568/917195845047308358/unknown.png)

The building, the road shoulder and stripe, the building on the side -- it all matches. We got our address. Now we just take that address from google maps, plug it into an MD5 hash, and our flag is secure.

> 628 IN-64, English, IN 47118

> f77589c3deb4af100c08acc9c1d49036

## The Flag

And thus, our flag: MetaCTF{f77589c3deb4af100c08acc9c1d49036}
