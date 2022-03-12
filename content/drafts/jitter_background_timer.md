---
title: "Jitter Background Timer"
date: 2022-01-22T16:47:20-08:00
# weight: 1
# aliases: ["/first"]
tags: ["computer science", "movies", "baking", "cooking", "misc"]
author: "Akshat Harit"
showToc: true
TocOpen: false
draft: true
hidemeta: false
comments: true
description: "DESC TEXT"
canonicalURL: "https://akshat-harit.github.io/posts/jitter_background_timer/"
disableShare: false
disableHLJS: true
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShareButtons: ["reddit", "ycombinator", "facebook"]

cover:
    image: "<image path/url>" # image path/url
    alt: "Jitter Background Timer"
    caption: "Jitter Background Timer"
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/akshat-harit/akshat-harit.github.io/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

I am usually good about adding jitter on retry timers. So we don't run into a situation where if server fails due to concurrent clients at one time, we don't get into a situation where the retry logic just keeps repeating the same load.

But hadn't thought about it from the context of background threads. I have usually seen backgrounds threads doing everything from contacting the server to populate some cache, refresh some access token before expiry, cleaning up some cache etc. Usually these are on a fixed timer, like update the cache every five minutes.

This is usually fine. If you have thousands of machines, the likelihood of them starting at same time is low as deployment is staggered. We practice safe deployment! And there is a natural jitter inherent to the service if you are getting response from a server. However, we had to do a massive service restart recently and seeing this graph was uncomfortable.

Even adding a couple of seconds of jitter would have reduced this substantially.

The only concern I see is generating the random number. I have to suppress my strong urge to do 
(https://stackoverflow.com/questions/31739792/is-uninitialized-local-variable-the-fastest-random-number-generator)[https://stackoverflow.com/questions/31739792/is-uninitialized-local-variable-the-fastest-random-number-generator] since it is the cheapest way to get a pseudorandom number here. But lets not use UB. I guess there must be some intrinsic to do this cheaply that doesn't cause UB, if we really want to get into the weeds.

But for 99% of the cases, you don't have to worry about this. For the .9 % of cases use your standard libraries random number generator. 
