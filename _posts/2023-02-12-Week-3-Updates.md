---
layout: post
title:  "Week 3 Updates"
date:  2023-02-12 12:05:25
categories: jekyll update
tags: featured
image: /assets/article_images/2023-02-12-Week-3-Updates/image.jpg
---
# Research Takeaways: 
### Shop Pickle; peer-to-peer clothing rental marketplace
 I found an app called Pickle that is NYC based which a similar pitch-line: potential for same day rentals, a platform for NYC users to list their closets up for rent and to find pieces to rent! I downloaded the app and played around to get a better sense of what I want to take away from their implementation of this idea as well as where I would like to differentiate. 

**User-Market Fit:**
While their marketing suggests that they have the potential for same-day rentals, that is not the normal experience in practice and is completey dependent on the availability of both the lister and renter. I stand by the idea that when implemented and isolated to a campus environment there will is strong guarantee for same-day rentals and even returns. Pickle relies on filtering user preference through an algorithm shaping the idea of the trends and styles that individual users will prefer to have suggested. Their same-day rental marketing is attempted by trying to suggest listers and renters within siilar zip-codes. Algorithm and zip-code isolation isn't something we will have to worry about in our implementation since user preferences are already isolated down to similar age-range of 20-26 year olds and located on/near campus. Upon more research, Pickle's full company name is Pickle Polls and their monetization scheme is to collect and sell data on user preferences.


**UI/UX:**
Pickle provides a great shortcut in my design process as I have an interactive app to remind me of all the screens I need to design and the dynamic functions I desire. My main gripe with Pickle is that they overload users. There is way too much information on display at all times and for their monetization purpose, collecting data should be as simple as needing users to click on things, not for users to see through the entire buying and renting process. This has helped me narrow down some concepts for user experience. Across most mobile apps I think Pinterest's Home/Explore page is what I would like to implement for displaying/curating products to users. There is no information other than image and I think this will encourage users to click into things - if they want the information such as clothing size and cost, they can click into it to get the information. On another hand, something conceptual that Pickle implements that I absolutely love is the idea that renters can make a bid to rent or buy the item from the lister. This is an idea I would love to steal because it combines the concept of renting clothes exclusively such as Rent the Runway with the idea of Poshmark's online second-hand marketplace.


# Development Updates:
### The growing pains of neglecting soure-control

Per picture header of this week's blog post, playing around in my react-native sandbox and continued learning-through-doing of Typescript has been fruitful. I have a much clearer idea of how to structure the development of this app and future apps in terms of file/component organization as well as knowledge of many many many useful react-native libraries that make life (for someone new to frontend development both conceptually and in practice) much less painful. 

**Progress:** 
Cohesive Home/Explore page layout with dynamic features of clickable product images that enlarge as well as back button to return to home page. Product screen design WIP to replace simple enlargement of selected product image to bring users to product screen with more information. Navigation between screen was solved by discovering `@react-navigation/native` and `@react-navigation\stack` libraries. Previously was playing around with dynamic implementations with way too many components all on the home page file with `TouchableOpacity` and `TouchabelWithoutFeedback` modules from `react-native`. 

**TO-DO for next week:**
- flesh out details for product screen
- user profile screent (similar to instagram)
- rent and posting screen design (steal from Pickle w/ amendements)
- learn dyanmic display implementations (scrolling, refresh, etc)

**Learning My Lesson...**
As I alluded to in the subheader... I did not commit anything I was playing around with and well... as many before me have encountered: I broke everything by attempting to implement the navigation file between screens which I then realized it was because my screens did not pass the same type of `Props` into screen component. And I couldn't roll back to the version that worked. Yes, I know the disappointment and frustration now, but honestly could happen again. 



