---
title: "Better interviewer?"
date: 2022-03-12T15:21:50-08:00
# weight: 1
# aliases: ["/first"]
tags: ["computer science"]
author: "Akshat Harit"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: true
description: "How to figure out someone is a good software engineer in 50 minutes and also tell someone that you are a good one too."
canonicalURL: "https://akshat-harit.github.io/posts/who_asks_the_questions/"
disableHLJS: true # to disable highlightjs
disableShare: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShareButtons: ["reddit", "ycombinator", "facebook"]

cover:
    image: "<image path/url>" # image path/url
    alt: "The Interviewing problem"
    caption: "The Interviewing problem"
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/akshat-harit/akshat-harit.github.io/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

I read hacker news and a fairly common upvoted topic is how software engineering interview is really bad. It doesn't measure anything and everyone knows that performance on leetcode style interview is not an indicator of job performance. I got promoted recently and it is quite possible that in the near future I will be asked to interview candidates. So have been thinking about this.

Seems to me that people criticizing are in charge and are still asking the leetcode style questions? I am not sure I understand it completely. Is it a case of people not wanting to go against the established process. Are you held responsible for a bad hire? Especially in places where interview is taken by random pool if interviewers that might not be in the same team.

Lets go over the common constraints that big companies. This is all hypothetical and particular company might be more lax or strict.

I am given a time limit of 50 minutes and then I have to provide a feedback based on some rubrick that might contain a scale of 1-10 to rate factors like problem solving ability, coding knowledge, culture fit etc. The interview training material at your company may give examples of asking leetcode style questions but there doesn't seem to be anything forcing me to follow that.

I am ignoring stuff like take home assignments etc. as those are something that require structural changes. I am just going with the current constrains and thinking that ass long as I rate the candidate on the asked rubrick after 50 minutes, I assume it will be fine.

So leet code is bad. What else can I do?

The other thing I am trying to struggle as well is that this is a two way process. How would I like to be interviewed? There is a definite advantage of leetcode style interview becoming binary success/failure. Even if the original intention was to approach it as figuring out problem solving skills, in reality, people do seem to recommend against a candidate if you are not able to come up with the established solution. 

From a candidate point of view, it is easier to know whether I have screwed up or not. And if not easier in terms of time and effort required, it is easy to figure out what effort is required. You fail an interview, you do more leetcode.

Of course the goal becomes passing the interview, rather than becoming a better software engineer. But at least it is concrete.

I am just brainstorming here.

1. Ask leetcode question, but one that I have myself solved without looking at the solution so I can actually judge the time taken to come up with the solution. It does feel like lot of interviewers have just looked up the solution so are not cognizant of the potential tricks etc. involved in the solution and enumerate the background information required. It is easy to underestimate that some leetcode questions were graduate problems at one time. And just looking up the solution doesn't give you the appreciation of the question.

1. We could do a collaborative code review, but that will devolve into language knowledge and product knowledge. If the candidate has public github, that could work, but I work on closed source systems and I expect that to be the case for a lot of people. Also, expecting people to know the knitty-gritty of a language like C++(insert your language here) is not going to work well. I have worked with c++ for multiple years and still continuously google cppreference.
Also, I think code review does depend a lot on knowing about the full product anyway.

1. Pick a random new hard problem from leetcode, preferably a recent one that you haven't seen before and give the solution to candidate in the language of choice. You are now coming from similar prior knowledge base. It also avoids the problem where you start expecting more when you keep asking the same favorite problem. Ideally the language is somewhat familiar to both the interviewer and interviewee or at least not as different as say Haskell and C++. Then we start trying to understand the solution and perhaps write a better version of it. Leet code solution are usually bad from code review standpoint and ignore readability, idiomatic language use etc. 

This seems like a good idea to me. I am still in the domain where a lot of candidates have been preparing. So I'll not be throwing a weird curveball and make people nervous. And this evaluates understanding a problem, understanding an existing solution, and then explaining/improving the solution, which seems to be what I am doing in my job. The only thing not tested here is coming up with the solution themselves, but if I am being honest, that is usually not what a software engineer does day to day.

The risk here is that I could come off looking stupid and embarrassed if I don't understand the solution myself. If we both don't understand the solution we are now in the vague state where instead of passing/failing the candidate, I am left in the fuzzy state and can't give any feedback. That can be mitigated by trying to solve the problem on your own, and solving it yourself, but doesn't feel honest. 

Ideally I would like candidate to reject me, if they don't feel me to be a good engineer. But I feel bad as it seems like I could be dragging my brilliant colleagues down with me.

Is there a better way, given the constraints?
