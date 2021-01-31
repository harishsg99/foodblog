---
layout: blog
title: How to build a discord bot using python3 Series Part1
date: 2021-01-31T02:46:40.163Z
---
<!--StartFragment-->

 Hopefully, this tutorial will get you started on the right path to building your own Discord bot using Python.

<!--StartFragment-->

# 1. Install discord.py

There are several libraries out there to hit Discord’s API, each with their own traits, but ultimately they all achieve the same thing. Since we are focusing on Python, `discord.py` is probably the most popular wrapper for Python.

Assuming you already have Python and `pip` installed, you're going to want to run this command:

```
pip install discord.py
```

`discord.py` has some requirements that will automatically be installed if your machine doesn't already have them. Once you have run this command, you should see something along the lines of this:

```
Installing collected packages: discord.py
```

Success! You now have access to Discord’s API. Before we get into coding a Discord bot’s version of “Hello World,” we need to set up a few other things first.

<!--StartFragment-->

# 2. Create a Discord Application and Bot

Before getting into the code, we need to create a “Discord application.” This is essentially an application that holds a bot. It can be accessed [on Discord](https://discordapp.com/developers/applications).

If you don’t have a Discord account, then you’re going to want to create one. But if you don’t have a Discord account, I don’t see why you would even look at this type of tutorial in the first place.

The page should look something like this:

![Image for post]()

![Image for post]()

Once you are on this page, you’re going to want to go to the “New Application” button:

![Image for post]()

![Image for post]()

After you click on the button, you’ll be prompted to name your application:

![Image for post]()

![Image for post]()

I’m going to name mine “SampleDiscordBot,” but you can really name it anything you want.

So once you’ve created your application, you get brought to a menu that looks like this:

![Image for post]()

![Image for post]()

There’s a lot of information and settings here, but as of right now, we only really care about the “Bot” setting on the left-hand side. So let’s go ahead and click that to get us to the Bot page:

![Image for post]()

![Image for post]()

We then want to click on the “Add Bot” button. A pop-up will come up asking if you want to tie a bot to your application. You want to smash that “Yes, do it!” button.

A bot has now been created and is attached to the application. We are going to need to create a brand new Discord server — or “guild,” as the API likes to call it — so that we can drop the bot in to mess around with.

<!--EndFragment-->

<!--EndFragment-->

<!--EndFragment-->