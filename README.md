# data-512-homework_2
 Assignment: Considering Bias in Data

Author: Ashwin Naresh

License: This project uses the MIT license.

In this assignment, we use the Wikipedia Pageviews API and the ORES API to collect page quality data on various world politicians. This data will be collected, parsed, and stored in csv files which we will later use to create some tables to help understand the data.

## License and Terms of Use
Wikimedia Foundation: https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use

Sample API Code: https://creativecommons.org/licenses/by/4.0/

ORES falls under the same guidelines as the rest of the wikipedia APIs.

The sample code license allows us to freely modify and use the code, porvided we acknowledge the license and cite it as we have done here. We also adhere to the Wikimedia terms of use by following all media laws with the information gathered and no not violate copyright in any way. The datasets and images created in thsi project also follow the terms of use by protecting private data and not being used for profit. This project acknowledges both licenses.

## API Keys and Authorization
The API's we use in this project require Wikipedia authorization tokens. For security purposes, the tokens I used are not included in the project repository. Contact me if you would like to get access to these tokens!

## API Documentation
Pageview API: https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html
ORES API: https://www.mediawiki.org/wiki/ORES#API_usage

Python Documentation: https://docs.python.org/3/

## Output Files

### CSV Files
article_quality_no_region.txt: This file was created as output from step 2 and is used as input for step 3. This file contains the article information and the corresponding ORES quality prediction. The columns are as follows: article_title,revision_id,article_quality,country,population,region. Note: Population and Region information is empty (This information is added in future steps)

wp_politicians_by_country.csv: This file was created as output from step 3 is the fully cleaned and merged dataset that we use for the analysis sections. This dataset contains politician information, article quality scores, and country/region populations. The columns are as follows: article_title,revision_id,article_quality,country,population,region. Note: Population is recorded in millions and region names are fully capitalized.

#### article_quality_no_region.txt and wp_politicians_by_country.csv contain the same columns:

article_title: The full article name of the politician's page.

revision_id: The revision id for the most recent revision of the article page. This is acquired through an API info call.

article_quality: The ORES prediction for the article. This field takes on the following values from best to worst: FA, GA, B, C, Start, and Stub. 

country: The country of the politician.

population: Population of the country in millions.

region: Geographic region of the world. These regions are in all caps (eg: NORTHERN AFRICA, EAST ASIA, etc).

wp_countries-no_match.txt: This file contains a list of countries that did not have match during the merging stage of the data cleaning process.

# Using the Code
The code for this project is found in hw2.ipybn (main code), wp_ores_liftwing_example.ipynb (reference material), and wp_page_info_example.ipynb (reference material). The code also references the politicians_by_country_AUG.2024.csv and population_by_country_AUG.2024 files as input.

To replicate this project, run the code blocks in the same order that they are provided. Note: The code in Step 2 takes a while to run, but the output of this step is already created and available for use in later steps. Therefore, Step 2 can be skipped.

# Research Implications

### General Reflection
Overall, this project was extremely fun and fulfiling. Python is a really easy language to use and the pandas library makes table operations trivial. One slight issue I was running into was that the data aquisition portion of the code took a very long time to run. Each API call took over a second, and with around 7000 article titles, this small delay adds up quite a bit. There might be a way to batch these requests, but I did not look into that any further. Apart from that small inconvenience, there were no major hurdles in this. After the final dataset was constructed, creating the tables was just a matter of a few lines of code. I think the tables highlight some interesting biases which I'll touch more on in the following section. In conclusion, I think the project goals were easy to follow and the steps made sense. I'm happy with the final result and learned more about biases in the world of data science.

### Guiding Questions

#### What biases did you expect to find in the data (before you started working with it), and why?
The concept of article quality was new to me. I didn't actually know that wikipedia has a model that rates the millions of articles on the website. But even without this prior knowledge, I had a feeling that biases would be present. Notably, I had a feeling that "accomplished" politicians' articles would be graded higher than those who were less "accomplished". Furthermore, I expected to see a Western bias, leading to European and North American articles being rated higher than African and Asian ones. These two biases are pretty standard throughout media, and I expected both of them to show up in dataset in one way or another.

#### What might your results suggest about (English) Wikipedia as a data source?
After going through this project, my initial expectations about bias were somewhat confirmed. While I don't think the politician's success has that much to do with article quality, the geographic region absolutely does. Europe has some of the highest per capita rates for both total articles and "high quality" articles while Africa and parts of Asia are among the lowest. This geographic disparity makes me hesistant to recommend wikipedia as a datasource but I would likely need more evidence to fully back this claim.

#### What might your results suggest about the internet and global society in general?
I think the results of this project speak to the state of Western Media and the English Internet. It's natural for a culture to have a positive bias toward themselves and a negative bias toward others. This harsh reality is clearly shown in this project as English Speaking politicians are likely to be much higher rated than non enligh speaking ones. This trend likely carries over to countless other fields in a variety of media types. This project has opened my eyes to this type of bias and I will be actively looking out for it in the future.
