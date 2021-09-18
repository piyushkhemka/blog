---
layout: post
title:  "How to ramp up fast on a new team as a software engineer"
date: 2021-09-18 14:39
categories: [software_engineering]
<!--permalink: ramp_up-->
---

    

I have worked as a Software engineer at Facebook for the last ~4 years. In those 4 years I have worked with two different teams. Here's what I have learned about ramping up fast in a new team as a software engineer

 

> <i> Disclaimer: All views are my own & not endorsed by my employer
> </i>

  

#### 1. Review other people's code
<br/>
Start reviewing code from **day 1**. Irrespective of whether you are a senior engineer or a newly minted engineer straight out of school start reviewing code from day 1. 

At this stage you would have no context about projects going on in the team & it will make you think that you have nothing meaningful to contribute. However, you should still review code everyday because it will help you achieve the following - 

a. It will force you to understand what the author of the code is trying to do & by extension what the author is working on. Congratulations, you have just learned the name of a new project that your teammate is working on. Do this everyday & in about a week's time you should have learnt what everyone in the team is working on & what is the status of each of those projects. 

b. It is a very easy way to learn where all the code relevant to your team (and therefore you) lives. This is usually a problem in big companies where code spans millions of files, folders & repositories. This will give you an idea of where services, scripts, configuration files, tests, experimental code, analytics relevant to your team lives.

c. You will read all the comments left by other code reviewers & understand what is valued in your team. Usually those comments would be left by the same teammates who will review your code in future. This will help you tweak your code to match your team's style.

d. You will learn how code is tested in your team by reading the test plan attached to the Pull Request/Diff. Figuring out how to setup test environment in a new team takes a while. You can short circuit the entire process. If the code does not have a test plan, adding a comment & asking the author how they tested their code is a good idea.

e. You can suggest code refactors, better name for variables, help identify bugs, logical errors or suggest better design patterns all of which don't require a lot of context. Your teammates will appreciate your help in helping them write better code.  


Remember, you don't have to comment on the code if you don't see anything worthwhile commenting on. You also don't need to accept the change if you aren't confident at this point. But you should still aim to do code review nonetheless. This is the single best way to ramp up quickly on a new team. Make a routine & spend at least 30 mins a day just reviewing code. This will be hard for the first few months because you will feel like you aren't doing anything productive in those 30 mins but this will greatly accelerate your ramp up. 



#### 2. Document everything
<br />
<img src="/blog/assets/images/post_images/ramp_up_software_engineer/biggestlie.jpg" />

Document everything while ramping up. You will be surprised how often you will revisit this document months or even years down the line. That obscure method of setting up testing for some minor configuration change that took you hours to figure out & you will never need to do again? Guess what, your future self will thank you 2 years down the line. 

Share this document with everyone in the team. Get feedback from all your teammates, refine the doc & publish this as an onboarding guide for all the future joinees. Woosh. Instant impact. Your manager will thank you for this. 

Pro tip: A lot of your team mates would a doc like this for themselves where they collect useful information, commands, links. Ask them to share this with you

But don't stop here. Don't just document your ramp up & stop. Continue documenting what you work on a daily basis. Later, at the end of the quarter/half/ year during performance review time come back & revisit this doc. You will have a much easier time remembering what you have worked on - which includes recruiting efforts, meetings to seek alignment with xFN, mentoring other engineers, tech talks, projects, refactoring code, writing tests etc all the things that we tend to forget over time 


#### 3. Ask for help
<br/>
Don't be shy in asking for help. This includes code pointers, references to documentation, design docs, links, tools. Ask questions in team meetings. Remember there are no bad questions. We get a noob discount for the first 2-3 months. Use that to your advantage.

This might seem very obvious but so many of willingly choose to do otherwise because we don't want to make a bad first impression or we don't want to come across as stupid or we are suffering from imposter syndrome & don't want to be 'discovered'.

#### 4. Understand the culture of the team/company
<br/>
Facebook values impact above everything else. Whatsapp values reliability, Google values scale, Startups usually value getting something working quickly & out to users. Your user facing team might prioritize user experience above all or they might be trying to reduce the size of their app on Android & care about that above everything else. Figure out what is it that your team cares about & optimize for that to achieve success. 

So, if you work at a startup that cares about getting something out to users ASAP don't feel very bad about not writing optimal modular code right now. Ship something now & come back & fix it at a later date. If you work at a company that values reliability, it is ok to ship less but make sure to test everything & ensure that the change wouldn't disrupt your users.

#### 5. Learn the tools of the trade

> “If I only had an hour to chop down a tree, I would spend the first 45
> minutes sharpening my axe.” – Abraham Lincoln.

Spend some time & learn the tools of the trade. Learn how to search code within your company including all the advanced filters. Think you know how to search code? Alright, search for a keyword such that only those files should be retrieved which contain another keyword within a particular sub-directory. 

What does your team use for tasks & project management? How is code checked in? How does your team communicate? What tools are used during oncalls? How do they escalate tasks? Are there channels/emailing lists/groups within the company to ask questions?

#### 5. Talk to everyone. 
<br/>
Don't forget to network & get to know your teammates. Setup 1:1s with everyone in your team & get to know them. 

My boss's boss's boss's boss wrote a great post on the [cold start problem](https://boz.com/articles/career-cold-start). This framework of getting started in a new team is relevant for any job including software engineering.


