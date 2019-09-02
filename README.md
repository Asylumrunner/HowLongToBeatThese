# HowLongToBeatThese
A web-scraper using Selenium to batch-query How Long To Beat

## What is this?
HowLongToBeat is a very useful website, which allows users to see approximately how long a video game will take to complete by aggregating user-reported completion times and sorting them into bare minimum, completionist, and somewhere-in-between buckets. If you're someone who has a lot of bought-but-unplayed video games (which is a ridiculous problem which I 100% have), it's a wonderful website for figuring out what game in your overstuffed collection you should dig into based on the time you're willing to commit. I have, like, a job and hobbies and stuff, I don't always wanna be starting a 60 hour RPG.

While HLTB is a fantastic website, it's also very difficult to query in a batch format. So, I decided to build a Python tool to do it for me. If HLTB ever introduces a batch functionality, or a public-facing API, this will be rendered unnecessary, but for the moment, it'll certainly help me.

## How Does It Work?
Usage: python3 hltbt.py <file name>
The file referenced should be a text file in which every game title to be searched is separated by newlines. It will then query HLTB for every title given, using Selenium, scraping the completion times, and compiling them into a csv called "completion_times.csv".
  
## Why Selenium?
HowLongToBeat uses Javascript to render page elements, so regular ol' page scraping isn't really an option, sadly. I'd hit the game pages directly, but the URLs for these pages are indexed completely arbitrarily, so I'd have no idea how to programmatically hit one of them.
