# 🏛️🗽 Scraping The New York State Senate

# Goal
To see how the state's lawmaking priorities have changed over the years.

# Summary
I collected data about bills signed by the governor from [NYS senate's website](https://www.nysenate.gov/) starting from the 2009-2010 session all the way up to 2021-2022, as of April 29, 2022. At the time of the scrape, New York's Governor Kathy Hochul had signed over 1000 bills into laws. I wanted to see what categories of laws these bills represent — are there more public health related laws signed this year? Is the focus on environment protection related laws? How have the laws enacted changed overtime? To take a closer look, I made a database of all laws passed, along with their dates, sponsor, descriptions and the law sections they affect.

# Process and tech stack used

#### Data collection
- The dataset contains 5052 rows and 6 columns. For the scrape, I used [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/), which is a Python Library.
- All the pages I scraped — 510 — to get the names of all the laws, and then another 5052 pages to get law sections were luckily all fairly standardized in how the html was structured. This meant that I could write a function that was applicable universally!
- The code and function can be found in [this notebook](https://github.com/areenaarora/new-york-senate_scrape/blob/main/Ten-year-scrape.ipynb). The notebook has comments and walk through of how the code works.

#### Analyses
- Once extracted, I analysed the data in a separate notebook. The intial questions I wanted to ask were:
1. How many laws were signed in each session?
2. What were the major categories of laws signed?
