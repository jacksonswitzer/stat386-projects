---
layout: post
title: "Where Should I Live? An Avocado Lover's Guide"
date: 2022-12-05
author: Jackson Switzer
description: Avocado prices vary significantly over time and by region. If you want to live somewhere where avocados are cheap, this post will show you the best regions to choose and how avocado prices fluctuated in those regions over a three-year period (and, for comparison, in the region with the most expensive avocados).
image: /assets/images/us-outline-map.jpg
---

This project began with a conversation I had with my sister and her roommate a few weeks ago. They're twenty years old and they love avocado toast, the Gen Z snack of choice. One evening, as both munched away on their favorite snack, I ventured to say avocado toast was overrated. They looked at me in disgust and adamantly disagreed, going so far as to say that wherever they live as independent adults, the avocados will have to be cheap, in order to fuel their obsession. That's where my research question was born: Where **is** the best place to live, if avocados are so important to you?

I set out to find a suitable dataset to answer the question, and found [this one](https://www.kaggle.com/datasets/neuromusic/avocado-prices). It's a record of the average weekly price of avocados by U.S. region, defined by proximity to major urban centers, from the start of 2015 through March 2018. I began with some exploratory data analysis, getting a feel for the data--how much prices varied, what the interesting features were, and so on. The code and explanations for that analysis are in this [previous post](https://jacksonswitzer.github.io/statistically-insignificant/2022/11/13/Exploring-Avocados.html)).

After understanding and visualizing the data, I determined that I needed a simple graphic to summarize the findings related to my original question. To do so, first I averaged each region's avocado prices across the whole timeframe to find out which had the cheapest avocados overall. Then I made a plot of monthly average avocado prices, displaying only the region with the most expensive avocados on average and the four regions with the cheapest ones. This lets prospective avocado-loving homebuyers see the four best options of places to live, and it allows them to see how these regions differ from the most expensive region. Because the prices fluctuate, some of the lines cross each other, making it hard to see clearly from the plot alone which regions are the cheapest on average in the long term; the legend therefore states explicitly which region is cheapest overall, moving to second, third, and fourth cheapest from there. For my sister, her roommate, or anyone else with similar tastes, the Houston area is your best bet, closely followed by Dallas/Fort Worth, Cincinnati/Dayton, and Nashville. The complete graphic is below.

For questions about implementation, see [the GitHub repository](https://github.com/jacksonswitzer/avocado_eda/tree/master) for this project. Thanks for reading!

![Test Image](https://raw.githubusercontent.com/jacksonswitzer/statistically-insignificant/main/assets/images/datastory.png)
