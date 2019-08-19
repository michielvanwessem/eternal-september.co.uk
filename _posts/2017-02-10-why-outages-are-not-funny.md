---
layout: post
cover: 'assets/images/cover-cloud.jpg'
navigation: True
title: Why outages are not funny
date: 2017-02-10 18:26
tags: sysadmin technical outages
subclass: 'post tag-sysadmin tag-technical'
logo: 'assets/images/ghost.png'
author: 'michiel'
categories: michiel 
---

<br />
This post comes a few days/weeks after the large outage at Gitlab, where a mistake and an unfortunate series of events took out their main database. This is really to write down my take on Gitab's outage, recovery, and the reactions of people during and after.

As most people know, [gitlab](https://gitlab.com) suffered a severe data outage on Tuesday the first of February. There is plenty of documentation of what happened, including that from Gitlab themselves who kept an open and honest communication of what steps had lead to the outage and the concurrent steps they had taken to restore their business back to order. Even going to the lengths of putting up a live feed of their restore process in action.

Here is the thing, we all mistakes, and if you haven't yet, you will. Even more so in my field. Ask any system operator, server monkey, system administration, you can be assured: mistakes were made in the line of duty. No matter what it was. I, myself have made various mistakes from removing the entire /etc directory as well as the changing my login to the wrong shell or changing permissions to the wrong settings, rendering a system entirely useless. Some, are however easier to recover from.

So, thus also at Gitlab. Yes, a mistake was made and in this case one with a big impact. Deleting a production database. It happens. People seemed to find this very humorous for some reason. I know, I know, it is a very human reaction to laugh. After all we have a term for this: Schadenfreude.

Honestly, I think I should say this up front. My respect for the way Gitlab handled the situation. Almost immediately they opened a google document and shared their findings, what steps they were taking to restore order out of the chaos they found themselves in. Many companies that I know would not do such a thing

Here is the thing, much like my earlier statement, as every system-, server-, or network administrator in his or her career will know, outages do happen. There is nothing funny about an outage. It's a pain for the people on the ground, for your customers, your clients, and their clients.

So, yes, it may be a human reaction that you have a bit of shadenfreude. I stopped doing it. I think of how I would handle it, what the causes could be. And have a thought of those in the trenches. Yes I am aware it sounds loftly. So be it.

I have been there often enough, sweating, toiling through the night, through my bank-holiday weekend because one of my co-workers in a moment of panic had fumbled over his commands and moved off a whole series of customers sites. We worked over the weekend restoring, communicating with management and our then chief-monkey.

Or the long evening I had to work through because our then (this a job many moons ago, when I was still a young system-administrator) SUN-Microsystems HA-Cluster had developed a so called split-brain situation where each node would think the other node would be down. It took us working through several scenarios with SUN support to figure out that a network card had become enabled, which we had disabled many weeks earlier, causing the network to stumble. 

Admittedly this also shows you the need for documentation, procedures, and backups to fall back on. Admittedly in the case of Gitlab, none of their backup strategies seemed to work or failed outright. Which of course is one of the sysadmins ethos: "*No backup really does exist, unless you have properly tested*". 

So no, outages are not funny. I don't think we should think them funny. It's a pain for everyone involved. Try to learn lessons from what others tell you about their outage. Offer help if you have help/knowledge that you can offer. Yes, it may be turned down, it may be accepted. At least you have offered rather then only standing there much like Nelson out of the Simpsons; pointing and laughing.

As my old man is quite happy to say: "*Shit happens*", and that it does. Don't let our field being defined by our failures. They happen. As surely as the sun rises in the morning. Let us define on how we solve these problems, what actions we take to tackle any problems that arise in our infrastructure and what solutions we put in place to prevent such a thing from happening again.





