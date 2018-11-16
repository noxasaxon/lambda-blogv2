---
title: Week Two
date: "2018-11-16T22:12:03.284Z"
---

##Individual Accomplishments this Week#
![](https://i.imgur.com/jFcq3Qe.png)
[Github Handle: @noxasaxon](https://github.com/noxasaxon)


Over the weekend one of the team members made a great styled wireframe for our app, so this week I started out switching the current app towards that style. I converted all of the 
vanilla css code to the ```styled-components``` library and implemented a global dark theme to be accessed by any React components.

Next I worked on finding and implementing a Spaced-Repetition algorithm to provide some logic to the decisions on when and how to serve the next cards. The first 
option I found was Anki's implementation of the open source algorithm SuperMemo 2. SuperMemo 2 is from 1989 and there have been many closed-source improvements since then.
While Anki has made their own improvements and the code is open source, it is extremely specific to their app and I felt it would be extremely counterproductive to reverse
engineer a java algorithm from decades ago that belongs to the app we are trying to improve upon. So diving back into research, I discovered an open source javascript implementation of SM2+, which made some tweaks to the original Anki code to try and remove specifics for that app. As I studied the code and read many issue trackers and comments, it seemed that there
were still too many ties to the Anki app that could not be removed.

I searched again for an alternative and found this [repo](https://github.com/lo-tp/memory-scheduler) by lotp. I read his blog post explaining the algorithm and essentially it is a
modern day rethink of what an SRS algorithm is trying to do, stripping out many unnecessary parts. I cloned the repo and began testing, adding comments for every line of code and 
renaming variables to more easily understand their intent. I also consolidated much of the external calls needed to set up and implement the algorithm so that it now takes one function
call to receive an updated card progress and due date, regardless of whether its the initialization of the card progress data or just an update. The algorithm now also reads 
current time inside its own code without requiring an additional argument. 

Other things I worked on this week: 

Helping connect auth0 to the app, fixing netlify deploys with auth0 (for my group and another group), teaching how to use environment variables in heroku, netlify and node.js,
brainstorming a better way to structure data in postgres (researched Objection.js for jsonB support), and fixing plenty of merge conflicts.

###Front End# 
####Ticket 1
Convert app to  ```Styled-Components```, Implement new global style and theme
[Github](https://github.com/Lambda-School-Labs/Labs8-SpacedRep/pull/22)         [Trello](https://trello.com/c/WzJXj55Q)


###Back End#
####Ticket 1
Research and implement SRS algorithm


####Ticket 2
Bug fix introduced with a bad merge  
[Github](https://github.com/Lambda-School-Labs/Labs8-SpacedRep/pull/23)
[Trello](https://trello.com/c/Tv7TFIPL)


#Detailed Analysis# Pick one of your tickets and provide a detailed analysis of the work you did. This should be approximately ¼ page of text, and at least three screenshots.

#Part 2 - Milestone Reflections# Put your response to the weekly question and a link to your team journal assignment here.