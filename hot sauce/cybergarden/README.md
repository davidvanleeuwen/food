Hello 👋 and be ready for my fiery friends 🌶🌶!!

To make hot sauce you need a few ingredients. The main ingredient are obviously peppers, but instead of simply buying them, I decided to buy some seeds from [peperzaden.nl](http://peperzaden.nl/) and grow them myself. However, I'm defintely missing that green thumb and I'm by all means no expert on peppers ([these guys are though](https://cpi.nmsu.edu)). That's why I decided to do this my way. Let me walk you through it.

## Quick introduction
Before I started I bought some peppers and thought that I could simply use the seeds to make more. So I got a few pepers to try out the taste and made it into a sambal. But I quickly realised this stuff is too inconsistent and not really the best flavor to proceed. So I did some research and figured I needed to work with [Fresno chili peppers](https://en.m.wikipedia.org/wiki/Fresno_Chili_pepper) instead. Oh, and this will be my first fermentation project.

The result of the sambal was pretty nice though, but really useless in the end.
![sambal](https://user-images.githubusercontent.com/238946/40270498-ede15e08-5b8e-11e8-8f44-b2133a87820a.png)

## Plants
For the actual growing of the plants I wanted to start a bit early in the year. I got a tip about [winter sowing](https://en.wikipedia.org/wiki/Winter_sowing). Simply put: you put your seeds in a small container, create some holes in the bottom, give it some water and close it. It's super easy and it doesn't require too much effort. This is perfect for me, because it doesn't require any attention.

<img width="480" alt="screen shot 2018-05-19 at 18 11 35" src="https://user-images.githubusercontent.com/238946/40270580-25d659d4-5b90-11e8-991a-227994b1d009.png">

After some period of time with enough sunlight, it will start to grow rapidly. Then you move it to another spot to become a bigger plant. Once that stage is reached, we can put the actual sensorbox near it. Yep, a sensorbox!

## Sensorbox
Wait what?! Yep. We're going to do some nerdy things here. Because nobody wants some ordinary hot sauce. Nah, we have to make it a bit more - well... open source! So while growing it, I want to monitor the temperature of the soil, the humidity of the soil and the outside luminosity. It doesn't act on that information or anything just yet 🤓. 

All sensordata is being transfered over [The Things Network](http://thethingsnetwork.org/) using a [Things Uno](https://shop.thethingsnetwork.com/index.php/product/the-things-uno/). This thing sends the data every 60 seconds and is being stored in a database. Basically it works like this:

![schema](https://user-images.githubusercontent.com/238946/40270653-714938f4-5b91-11e8-93f8-a64a21da49f4.png)

And this is the actual code: https://github.com/davidvanleeuwen/cybergarden.

### Hardware
When I was discussing this with a few people, they said the had build the same thing. Not for hot sauce, but simply knowing when they should water their plants. There are existing solutions for that already. Some of them can be nice if you're looking for something simple and quick. However, the general response I got from those things is that they start to corrode very quickly, which in my mind isn't really nice for the plants and the lifespan of your hardware.

Eventually I ended up with the [adafruit humidity/temperature sensor](https://www.adafruit.com/product/1298). A bit expensive ($49.95), but it is really meant to in contact with water. I also got a light sensor from a friend, which you can get anywhere and can be very cheap as it'll stay inside of the container.

So I hooked them up to the Things Uno, put it in a nice container and made it airtight, like so:

[<img width="265" alt="screen shot 2018-05-19 at 17 38 38" src="https://user-images.githubusercontent.com/238946/40270331-83c4eaf6-5b8b-11e8-9927-2f5d5845ff7a.png">
](https://user-images.githubusercontent.com/238946/40270326-5f8d1e24-5b8b-11e8-9337-6e85de31275f.png)
<img width="428" alt="screen shot 2018-05-19 at 18 10 35" src="https://user-images.githubusercontent.com/238946/40270577-1cce112e-5b90-11e8-873a-675c2becf707.png">

### Dashboard
This is the most exciting part to be honest. Putting everything into something visual, something you can look back at and see what happened over time; what to do better. The data needs to be stored somewhere, so I decided to find something relatively cheap or better yet: free. Although it's not really popular these days, I used MongoDB and their hosted version called [Atlas](https://www.mongodb.com/cloud/atlas). It can be hooked up to [Redash](http://redash.io/), the dashboard tool somebody suggested to me. With Redash you can query your MongoDB how you'd like and simply present a graph like so:

[<img width="618" alt="screen shot 2018-05-19 at 17 46 19" src="https://user-images.githubusercontent.com/238946/40270379-9a5f483c-5b8c-11e8-843d-954adf5f4378.png">](https://garden.davidvanleeuwen.nl/public/dashboards/qFxzixm2UwpHUIRO7e8jz2u61N3v8Yb8afp8zDYa)

[Click here to view the actual live data](https://garden.davidvanleeuwen.nl/public/dashboards/qFxzixm2UwpHUIRO7e8jz2u61N3v8Yb8afp8zDYa). Click the things in the legenda to view more specific things.

I'm also getting an alert on Slack whenever the humidity of the soil is getting below 50% (relative humidity a.k.a RH %). I'm not sure at what percentage it'll need water, but it's definitely something I need to figure out. This is what the notification looks like:
<img width="667" alt="image" src="https://user-images.githubusercontent.com/238946/40449969-7fdefbfa-5eda-11e8-84d9-4b616a9afcf7.png">

I installed Redash and all its dependencies through a pre-installed [linux distribution from Bitname](https://docs.bitnami.com/aws/apps/redash/) and put it on an AWS EC2 instance, but you can put it on any server you'd like.


