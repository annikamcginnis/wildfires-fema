# Analyzing FEMA Data on Wildfires

## Goal
***
- To analyze how the frequency and locations of wildfires in the United States are changing over time.
- To analyze the trends of FEMA's aid delivery for wildfire victims.

## Main Findings
***
- The Federal Emergency Management Agency (FEMA) has declared over 1,600 wildfire disasters since 1953, with numbers increasing especially since 1996.
- Since November 2002, when FEMA started recording the data, the agency has helped over 2,000 communities (divided by zip code) across the nation respond to wildfires.
- More areas in the American West are experiencing wildfires in recent years.
- While many of the same places, such as communities around Los Angeles, continue to fall victim to wildfires, almost 1,000 zip codes that had not experienced any fire from 2002-2019 also had at least one wildfire between 2020 and Feb. 2025.
- Since 2002, FEMA has helped about 4,300 cities across the nation respond to wildfires, including providing over $416 million for about 33,000 homeowners and 40,500 renters to make their homes safe and livable again. The number of people and amount of money provided by FEMA has increased especially after 2015.
- The majority of homeowners and renters supported by FEMA have been in California (78% as of publishing this repo), but people in 9 other states have also received financial aid for home damages.
- Renters have received around $700-7,500 and homeowners around $700-42,000, depending on their needs.
- The average financial aid both renters and homeowners have received on average is smaller with a higher number of people receiving aid in the zip code.
  
## Data Collection
***
I acquired datasets through OpenFEMA:
- [Disaster Declarations](https://www.fema.gov/openfema-data-page/fema-web-disaster-declarations-v1)
- [Housing Assistance Program Data - Owners](https://www.fema.gov/openfema-data-page/housing-assistance-program-data-owners-v2)
- [Housing Assistance Program Data - Renters](https://www.fema.gov/openfema-data-page/housing-assistance-program-data-renters-v2)
- [Public Assistance Funded Projects Details](https://www.fema.gov/openfema-data-page/public-assistance-funded-projects-details-v1) (not included in the final analysis)
  
## Data Analysis
***
I used the following languages and libraries in my data cleaning and analysis: 
- Python
- Pandas
- Regex
- Requests
- BeautifulSoup
- Playwright
- R
- ggplot

Most of my cleaning and analysis is done in Pandas. I filter fire incidents, sum various columns in the owners and renters dataframes, and merge them with the disasters dataframe to create one uniform dataframe used for analysis. I also conduct exploratory analysis on each individual dataframe.

I bring the dataframe to a Python list, and I use the requests library and BeautifulSoup to search for the city names by zip code on zip-codes.com, which I save into each dictionary. 

In Python, I create another dictionary value that notes the zip codes that appear only after 2020. I also use the Google Maps Geocode API to find the latitude and longitude for each city, which I save to each dictionary.

Finally, I read in some of the revised CSVs in R and do some exploratory data visualization in ggplot. 

I save several sub-datasets as CSVs that I use for visualization in Datawrapper.

## Reflection
***
I improved my skills in analyzing, consolidating and merging datasets to obtain insights. This project also helped me improve my skills using BeautifulSoup and Playwright to add more information from an external site to all elements in a list of dictionaries. 

This was also one of my first experiences using ggplot in R for exploratory data visualization. I practiced moving between Pandas, R, and Python all in the same Jupyter Notebook.

I started this project intending to make a map of wildfires by scraping the NOAA Billion Dollar Weather and Climate Disasters website. After scraping and cleaning this site (included in the repo), and using Claude for Sheets to extract location names from the disaster descriptions, I realized the locations were too broad and inconsistent (some did not even include state names) to do a comprehensive analysis. This is when I pivoted to FEMA. 

**In the future:** 
- I would analyze the Public Assistance Funded Projects Details dataset to understand where FEMA put in funds, other than for homeowners and renters. Same for the Hazard Mitigation projects (grants helping communities prevent disasters).
- It would be interesting to combine an analysis of FEMA spending on wildfires with state-level spending.
- The dataset needs a bit more cleaning to fix values that aren't appearing on the ggplots in R.
 
