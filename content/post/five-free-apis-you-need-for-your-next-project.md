+++
title = "Five Free Apis You Need for Your Next Project"
description = "Hi! Welcome to a new article! I'll be showing you 5 very useful FREE apis you can easily integrate into your next project for extra functionality!"
date = 2022-11-10T18:11:15-06:00
tags = ['api', 'list']
draft = false
+++
Hi! Welcome, or welcome back to a new blog post! I'm gonna be sharing with you some awesome FREE apis that you can easily implement  into your projects as they don't require any api keys or authentication! Without wasting any more time, let's get started!
<!--more-->

## Table Of Contents
1. [QR Tag API](#qr-tag-api)
2. [EVA - Email Validation API](#eva-email-validation-api)
3. [GeographQL](#geographql)
4. [Image Charts](#image-charts)
5. [Free Forex API](#free-forex-api)
6. [Fun Bonus: EmojiHub](#fun-bonus-emoji-hub)

## [1. QR tag API](https://www.qrtag.net/api/)
Simple api that allows you to generate QR codes! There are multiple use cases for this, and while you can use it as a fun little feature for your project, it could also work as project itself! 

The cool thing about this is that you can specify a lot of perameters like the size of the image, or the format like SVG or PNG.


URL Endpoint: `https://qrtag.net/api/qr(_transparent)(_[size]).[png|svg](?url=[URL])`


Example: `https://www.qrtag.net/api/qr_12.svg?url=https://the-net-blog.netlify.app`

Response: 

![](https://www.qrtag.net/api/qr_8.svg?url=https://the-net-blog.netlify.app)


## [2. EVA - Email Validation API](https://freeforexapi.com/Home/Api) 
EVA is a simple API that allows you to identify spam emails or fake emails with *blazinlgly fast* performance! 


URL Endpoint: `https://api.eva.pingutil.com/email?email=[email]`


Example: `https://api.eva.pingutil.com/email?email=test@mail7.io

Response: ```
```
{
    "status": "success",
    "data": {
        "email_address": "test@mail7.io",
        "domain": "mail7.io",
        "valid_syntax": true,
        "disposable": true,
        "webmail": false,
        "deliverable": true,
        "catch_all": true,
        "gibberish": false,
        "spam": false
    }
}
```

## [3.  GeographQL](https://geographql.netlify.app/) 
Get information about countries, states, cities using GraphQL


URL Endpoint:`https://api.geographql.rudio.dev/graphql`

Queries: `cities, city, state, states, country, countries`

Example Response for a city query: 
```
{
  "data": {
    "city": {
      "id": 127759,
      "name": "Los Angeles",
      "state_id": 4655,
      "country_id": 236,
      "country_code": "US",
      "latitude": 34.05223,
      "longitude": -118.24368
    }
  }
}
```


## [4. Image Charts](https://documentation.image-charts.com/)
Create any type of chart image you can think of! I even learnt some new type of charts while going through their documentation.

Might not be the easiest thing to get started with, but this can definitely spice up your websites and in my opinion worth giving a try.

URL Endpoint: `https://image-charts.com/chart ?cht=<chart_type> &chd=<chart_data> &chs=<chart_size> &...additional_parameters...`


Example URL: `https://image-charts.com/chart?chs=700x190&chd=t:60,40&cht=p3&chl=Hello%7CWorld&chan&chf=ps0-0,lg,45,ffeb3b,0.2,f44336,1%7Cps0-1,lg,45,8bc34a,0.2,009688,1`

Response: ![](https://image-charts.com/chart?chs=700x190&chd=t:60,40&cht=p3&chl=Hello%7CWorld&chan&chf=ps0-0,lg,45,ffeb3b,0.2,f44336,1%7Cps0-1,lg,45,8bc34a,0.2,009688,1)


## [5. Free Forex API](https://freeforexapi.com/Home/Api) 
The Free Forex API gives real-time information about foreign exchange rates, and as the name implies it is of course free to use, but they are strict when it comes to abusing their service.

URL Endpoint: `https://www.freeforexapi.com/api/` 

Example URL: `https://www.freeforexapi.com/api/live?pairs=EURGBP,USDJPY`

Response: 
```{
    "rates":{
        "EURGBP":{
            "rate":0.891724,
            "timestamp":1532429549281
        },
        "USDJPY":{
            "rate":111.1307,
            "timestamp":1532429549281
        }
    },
    "code":200
}
```


## [Fun Bonus:  EmojiHub](https://github.com/cheatsnake/emojihub)
EmojiHub returns random emojis from already filtered categories and groups. As well as get all the emojis from one specific group. Who knows, maybe you might find a good use for this!

URL Endpoint: `https://emojihub.herokuapp.com/api/[Option]`


Example : `https://emojihub.herokuapp.com/api/random`

Response: 
```
{
  name: "hugging face",
  category: "smileys and people",
  group: "face positive",
  htmlCode: [
    "&#129303;"
  ],
  unicode: [
    "U+1F917"
  ]
}
```

I appreciate you spending your time reading this post, if you'd like to read more here you go:

[🔥  What Is Open-source? A Simple Introduction - My Last Post](https://the-net-blog.netlify.app/post/get-started-with-git/)

[🏠  Home Page](https://the-net-blog.netlify.app/)
