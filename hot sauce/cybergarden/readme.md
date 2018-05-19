Hi 👋 and be ready for some 🌶🌶!

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
Nobody wants some ordinary hot sauce. Nah, we have to make it a bit more - well... open source! So while growing it this year, I monitored the temperature of the soil, the humidity of the soil and the outside luminosity. It doesn't do anything, but maybe next year I can actually do something more what that information 🤓. 

All sensordata is being transfered over [The Things Network](http://thethingsnetwork.org/) using a [Things Uno](https://shop.thethingsnetwork.com/index.php/product/the-things-uno/). This thing sends the data every 60 seconds and is being stored in a database. Basically it works like this:

![schema](https://user-images.githubusercontent.com/238946/40270653-714938f4-5b91-11e8-93f8-a64a21da49f4.png)

And this is the actual code: https://github.com/davidvanleeuwen/cybergarden

### Hardware
[<img width="265" alt="screen shot 2018-05-19 at 17 38 38" src="https://user-images.githubusercontent.com/238946/40270331-83c4eaf6-5b8b-11e8-9927-2f5d5845ff7a.png">
](https://user-images.githubusercontent.com/238946/40270326-5f8d1e24-5b8b-11e8-9337-6e85de31275f.png)
<img width="828" alt="screen shot 2018-05-19 at 18 10 35" src="https://user-images.githubusercontent.com/238946/40270577-1cce112e-5b90-11e8-873a-675c2becf707.png">

### Dashboard
* https://www.mongodb.com/cloud/atlas
* https://docs.bitnami.com/aws/apps/redash/
[<img width="618" alt="screen shot 2018-05-19 at 17 46 19" src="https://user-images.githubusercontent.com/238946/40270379-9a5f483c-5b8c-11e8-843d-954adf5f4378.png">](https://garden.davidvanleeuwen.nl/public/dashboards/qFxzixm2UwpHUIRO7e8jz2u61N3v8Yb8afp8zDYa)


