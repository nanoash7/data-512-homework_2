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

## API Documentation
Pageview API: https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html
ORES API: https://www.mediawiki.org/wiki/ORES#API_usage

Python Documentation: https://docs.python.org/3/

## Output Files

### CSV Files
article_quality_no_region.txt: This file was created as output from step 2 and is used as input for step 3. This file contains the article information and the corresponding ORES quality prediction. The columns are as follows: article_title,revision_id,article_quality,country,population,region. Note: Population and Region information is empty (This information is added in future steps)

wp_politicians_by_country.csv: This file was created as output from step 3 is the fully cleaned and merged dataset that we use for the analysis sections. This dataset contains politician information, article quality scores, and country/region populations. The columns are as follows: article_title,revision_id,article_quality,country,population,region. Note: Population is recorded in millions and region names are fully capitalized.

wp_countries-no_match.txt: This file contains a list of countries that did not have match during the merging stage of the data cleaning process.

# Using the Code
The code for this project is found in hw2.ipybn (main code), wp_ores_liftwing_example.ipynb (reference material), and wp_page_info_example.ipynb (reference material). The code also references the politicians_by_country_AUG.2024.csv and population_by_country_AUG.2024 files as input.

To replicate this project, run the code blocks in the same order that they are provided. Note: The code in Step 2 takes a while to run, but the output of this step is already created and available for use in later steps. Therefore, Step 2 can be skipped.
