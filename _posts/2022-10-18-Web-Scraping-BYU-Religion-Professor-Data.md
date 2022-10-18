---
layout: post
title:  "Web Scraping BYU Religion Faculty Data"
date:   2022-10-18
author: Jackson Switzer
description: Pulling contact info, job titles, and Rate My Professor ratings about all present and past faculty and staff from the BYU Religious Education Department
image: /assets/images/bookofmormon.png
---

First, a disclaimer: All the data I scraped for this project is publicly available. I am a BYU student, but I was never required to log into my BYU account to access the information I share here about the professors. Rate My Professors is also a public site, with all ratings accessible via Google search without logging in. And my resulting dataset is relatively small (only a few hundred lines), so I never made enough requests to risk overwhelming their servers. (Always be courteous when you're scraping.)

## Intro: Why would I want a table of information about religion professors?

My biggest long-term professional goal is to become a BYU religion professor. BYU religion professors come from a variety of educational backgrounds, ranging from family science to philosophy to ancient near eastern studies. My junior year of college, I started thinking seriously about what I wanted to study in grad school, and a natural step was to get to know more religion professors so I could better understand their academic paths. But as an undergraduate statistics major and math minor, I've didn't naturally form relationships with much faculty of the religion department. I had to be proactive in finding out which religion faculty did research in topics that interested me and seeking out opportunities to talk with them. It would have been useful to have their contact info and other information easily accessible.

I've also been a heavy user of Rate My Professors throughout college and thought it would be interesting to compare the average ratings of full professors with those of associate and adjunct professors.

If you're in a similar situation, I hope this tutorial can help get you on the right track!

## Web Scraping Process

To pull data from the BYU website, I primarily used the Python packages `requests` and `BeautifulSoup`, with the occasional help of some regular expressions and a unicode reformatting function. Import the following:

```
from bs4 import BeautifulSoup as bs
import numpy as np
import pandas as pd
import requests
import re
import unicodedata
```



Don't forget:
links
subheadings
visuals/code segments
conclusion paragraph with call to action
