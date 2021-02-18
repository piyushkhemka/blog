---
layout: post
title:  "How to transfer all your subreddits from one account to another"
date:   2021-02-06 00:45
categories: [subreddit_migrator]
---

I created a new Reddit account recently & wanted to start using that account as my primary account. I wanted to transfer all my subreddits from the old account to the new one. I searched a lot but couldn't find any way of doing it. So, I built one myself. This post outlines a step by step process to copy all your subreddit subscriptions.

Let me warn you - Reddit doesn't make this process easy. This is only a hack & a little cumbersome.

1.  Download the zip file from this <a href="https://github.com/piyushkhemka/Subreddit-Migrator" target="_blank"> link</a>

2.  Open a terminal & cd into the path of the downloaded unzipped folder

{% highlight python %}
cd /path/to/downloaded/folder_in_step_1
{% endhighlight %}

{:start="3"}
3.  Login to your old account. <a href="https://www.reddit.com/prefs/apps" target="_blank"> Create a new application</a>

<img src="/blog/assets/images/post_images/subreddit_migrator/1.png"/>

{:start="4"}
4.  Choose the following options

- Type of application - script
- You can put the redirect url as http://localhost:8080
- Rest of the things like description don't matter. Put anything there

<img src="/blog/assets/images/post_images/subreddit_migrator/2.png"/>

{:start="5"}
5.  Once the application is created, copy the client id & secret id into old_user_config.json file

<img src="/blog/assets/images/post_images/subreddit_migrator/3.png"/>

{:start="6"}

6.  Put down your username & password in username & password section. Don't worry, the code always stay on your local machine. It is only used to authenticate your account.

7.  Repeat steps 1 to 5 with your new account. Copy the client_id & client_secret code into new_user_config.json. Add your username & password of the new account there as well.

8.  Run the file subreddit.py. CD into the folder containing the file & run the command -

{% highlight python %}
python subreddit.py
{% endhighlight %}

{:start="9"}
9. All your subreddits should be copied from old account to new account.

<img src="/blog/assets/images/post_images/subreddit_migrator/4.png"/>



Your new account should now be subscribed to all the subreddits from your previous account. Happy Redditting! 

<br/>
P.S: If you like to Reddit, you should totally download
<a href="https://redditenhancementsuite.com/" target="_blank"> Reddit Enhancement Suite</a> (Not affiliated to them or paid by them). It will make your life easier. Trust me ;)
