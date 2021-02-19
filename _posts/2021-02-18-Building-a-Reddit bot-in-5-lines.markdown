---
layout: post
title:  "Building a Reddit bot in 5 lines to help teach the correct spelling of Gandhi "
date: 2021-02-18 02:00
categories: [gandhi_bot]
<!--permalink: gandhi_bot-->
---


I login to Reddit to a full inbox like this everyday

<img src="/blog/assets/images/post_images/gandhi_bot/1.png" />

These are the usual replies that <a href="https://www.reddit.com/user/GANDHI-BOT/" target="_blank">/u/GANDHI-BOT</a> gets on a day to day basis when it corrects the spelling of Gandhi on Reddit.

For a long time, I have noticed that folks on Reddit always mis-spell the name of Mahatma **Gandhi** as **Ghandi**. 

<img src="/blog/assets/images/post_images/gandhi_bot/2.png" />

This annoyed me so much that I decided to create a bot help people learn how to spell Gandhi correctly.

Here's how I did it

## Finding the Reddit API

<br/>
The first thing I did was to search if Reddit offered a public API. Luckily, <a href="https://www.reddit.com/dev/api/" target="_blank">it did</a>. On further research (and by research I mean furious Googling), I found a convenient Python wrapper for Reddit API called <a href="https://praw.readthedocs.io/en/latest/" target="_blank">PRAW</a> & decided to setup the script in Python. Then I went through the documentation to see if it provided the features I needed.

## API Requirements

<br/>
What I wanted the bot to do was that everytime someone spelt Gandhi as Ghandi, the bot would post a motivational quote & then conclude the sentence with " Just so you know, the correct spelling is Gandhi."

To translate that into coding requirements what I needed were the following - 

1. An API that monitors comments posted on Reddit in real time
2. An API that allows the the bot to post a reply
3. A list of quotes that I can store somewhere


1 & 2 were provided by PRAW's APIs. For 3, I decided to store a bunch of quotes in a list & pick one randomly.

<br/>
## Coding the Bot
<br/>

Reddit API dictates that we first authenticate the bot. We do this by providing our username, password, client id & secret here. 

{% highlight python %}
reddit = praw.Reddit(username=config.username,
                         password=config.password,
                         client_id=config.client_id,
                         client_secret=config.client_secret,
                         user_agent=config.user_agent)
{% endhighlight %}

After successful authentication, we need to provide the list all of subreddits that the bot will monitor. We want the bot to monitor all of Reddit. So, we put down 'all' subreddits to monitor

{% highlight python %}
subreddits = reddit.subreddit('all')
{% endhighlight %}

Now here's the 5 line code snippet. The logic of the code is very simple. If we find the word 'Ghandi' in a comment, we randomly pick a quote from the pre-populated list of quotes & add a conclusion to it. Then we post it as a reply to the comment containing the misspelling of Gandhi. 

{% highlight python %}
# misspelling to make the bot angry
ghandi = 'ghandi'
quotes_list = [my list of pre populated motivational quotes]
reply_conclusion = " Just so you know, the correct spelling is [Gandhi](https://en.wikipedia.org/wiki/Mahatma_Gandhi)."

# monitors stream of comments
for comment in subreddits.stream.comments():
    # if misspelling found in the post 
    if ghandi in comment.body.lower():         
            # construct the reply
            reply_start = random.choice(quotes_list)      
            # post the reply
            comment.reply(reply_start + reply_conclusion) 
{% endhighlight %}

Finally, I wrapped all the API requests in a try-catch block and instructed the bot to sleep for a few seconds in between replies to rate limit it. You can view the entire code on my <a href="https://github.com/piyushkhemka/reddit-gandhi-bot" target="_blank">github</a>

## Testing
<br/>
After the bot was coded, I created a new reddit account. Luckily, I managed to snag the username GANDHI-BOT. Then, I created a new <a href="https://www.reddit.com/prefs/apps" target="_blank">Reddit app</a> and replaced the authentication part of code with this account's username & password. I also replaced the client id & secret with the newly created app. Then I ran the code on my terminal

{% highlight python %}
python main.py
{% endhighlight %}


After few rounds of debugging, I managed to fix all the errors & could see that the code was working. The next step was to deploy this on the cloud so that I didn't have to run it on my laptop 24 X 7. 

## Hosting the bot
<br/>
I didn't want to shell out any money for this silly project. So, I searched for a free solution. 

I initially went with <a href="https://www.pythonanywhere.com/" target="_blank">Python anywhere</a>. The service provided a free tier which allowed hosting of one web app with low CPU/bandwidth.

I simply uploaded all the files & executed the program from its local terminal. However after a few weeks, I noticed that the program would often crash & my free bandwidth would run out. 

So, I started searching for an alternative solution. This is when I stumbled upon Heroku. I created a new app on heroku & followed the guidelines on the 
<a href="https://devcenter.heroku.com/articles/getting-started-with-python?singlepage=true" target="_blank">instruction page</a> to host the bot. The deployment process at Heroku was slightly more complex than Pythonanywhere but the free hours of hosting provided by Heroku ensures that the bot runs 24 X 7. Since I deployed the bot few months back, it hasn't crashed even once. If you are looking to host a cheap Python script, I highly recommend Heroku highly. 







