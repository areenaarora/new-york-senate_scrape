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

#### Cleaning and expanding the dataset
- After collecting the initial dataset, I manually built it out further to include the full names and partiesfor all the bill sponsors. An unedited, untouched version of the dataset is also included in the repository and can be found [here](https://github.com/areenaarora/new-york-senate_scrape/blob/main/unedited.csv).
- There were a couple of rows that had picked up bad HTML with the scrape, so I manually cleaned those out.
- After cleaning the data, I made the editorial decision to standardize the "bill law section" a bit. This meant that laws which had — Agriculture and Markets Law, Agriculture and Markets and Agriculture and Markets Commissioner — were all clubbed together as Agriculture and Markets. I also dropped the word "law" from all fields, since the purpose here is to broadly see what sectors are affected. 'Correction' and 'Correctional Services' are also clubbed together as 'Corrections.' I also cleaned the data to have uniform spellings (election and elections). I also clubbed military and veterans into one category since the bills' language was fairly similar across both categories.
- The cleaning process brought down the number of unique bill sections from 249 to 224.


#### Analyses
Once extracted, I analysed the data in a separate notebook. The intial questions I wanted to ask were:
1. How many laws were signed in each session?
2. What were the major categories of laws signed?
3. Are there certain laws more Republicans are sponsoring vs Democrats?
4. How do these laws reflect global events? For instance, did the pandemic fuel an increase in public health-related laws?