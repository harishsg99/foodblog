---
layout: blog
title: I took a challenge to build an API , make $100 in 48 hrs
date: 2021-03-08T02:15:11.981Z
---
[](https://twitter.com/CoderHarish/status/1368083115701268482?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1368083115701268482%7Ctwgr%5E%7Ctwcon%5Es1_c10&ref_url=https%3A%2F%2Fpublish.twitter.com%2F%3Fquery%3Dhttps3A2F2Ftwitter.com2FCoderHarish2Fstatus2F1368083115701268482widget%3DTweet)In this article, I shared  my experience on taking this challenge  and some key learning. I shared my progress on twitter

# 1. Idea

I started searching web espeacially on forums like reddit and quora, My aim was to build a niche API so that I started thinking of how to improve the existing web scraping APIs available in the market. I got a simple idea to improve the existing API is to get an example of things to scraped from the user and give them exactly what they want.

# 2. User Research

I am building a web scraping tool so my target user must be one who needs data from websites. People who are data analysts, machine learning engineers, freelancers, and companies who are looking to generate leads for their product.

# 3. Design

I designed simple multi threaded REST API server architecture which can multiple users at the same time. I choose the AWS lambda service for hosting the API as it doesn't cost me much on outages and it is reliable for this service.

# 4. Programming

I took flask as the web framework and used scrapy framwork on python to scrape websites and make them as a REST API. I used postman to debug and test the API.I integrated this api into Rapid API marketplace after hosting on AWS.

# 5. Marketing

Reaching the first 10 customers is a manual and relatively straightforward process.

* Tweet about your product, slide into existing tweet threads, DM people who engaged with those threads directly.
* Make a genuine post in a Facebook group or Slack community. Message people 1:1 who show an interest.
* Make a post in a related Subreddit (eg. r/Shopify for a Shopify app) and DM people who engage. Or search for existing posts that match your keywords and reach out to people who engaged.
* List on marketplaces - Even if you do the basic optimization for a marketplace (correct naming, description, listing page, screenshots), and if the problem you are solving has established demand, then you should get your first 10 customers from there.
* Cold email outreach to companies that match your parameters, using data sources like BuiltWith

# 6. Finally failed

My target was $100 but what I earned in the final was only $10 with lots of lessons. 

# 7. Key learning

* Think from the user perspective before building the product
* Getting your first users is easy when you know and built exactly what they need.

# Conclusion

Even though I failed in this challenge, I really enjoyed doing this challenge and building this product.

link for the product : <https://rapidapi.com/harishsg99/api/scrapehoney>