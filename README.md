## Goal
The purpose of this project is to understand the relationship between covid, unemployment and the labor force. The project is the final assignment for the University of Washington DATA 512 [A7 assignment](https://docs.google.com/document/d/1nT1V8I-RLQN3ZxCjpF6Mse9w7-dP1_s1nnW7MfIevgk/edit#heading=h.cb9wthtz43qg). The goal for this project is to understand if we can use Granger causality test to prove whether the covid infection rate granger caused higher unemployment rate and lower labor force participation in Bernalillo County, NM.


## Data Source
- [Kaggle repository of John Hopkins University COVID-19 data](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv): COVID-19 total case number by day by county.
- [CDC Masking Mandate by State](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i): CDC masking mandate by state
- [The New York Times mask compliance survey data](https://github.com/nytimes/covid-19-data/tree/master/mask-use): Mask compliance data from a NYT survey
- [US Bureau of Labor Statistics (Labor Force, not seasonally adjusted)](https://data.bls.gov/timeseries/LAUMT351074000000004?amp%253bdata_tool=XGtable&output_view=data&include_graphs=true): Labor force and employment data


## Data Description


Here is a description of the final dataset (final_data_testing) after cleaning and processing.
|Column Name|Description|Data Source|
|-|-|-|
|Year|the year of the data|Kaggle|
|Month|the month of the data|Kaggle|
|labor force|the number of people employed and looking for jobs|US Bureau of Labor Statistics|
|employment|the number of people employed|US Bureau of Labor Statistics|
|unemployment|the number of people unemployed|US Bureau of Labor Statistics|
|unemployment rate|the unemployment rate (unemployment/labor force)|US Bureau of Labor Statistics|
|time|the month end date|calculated|
|unemployment_diff|the change in unemployment from the previous month|calculated|
|labor_force_diff|the change in labor force from the previous month|calculated|
|covid_monthly_infection_diff|the change in new covid infection in each month|calculated|


## Known Issues

- Pageview API has the ability to filter out views from spiders/crawlers, while the Legacy Pagecounts API does not have such abilities. 
- There was about 1 year of overlapping traffic data between the two APIs, and data from both APIs in the 1 year of overlapping period is included.
- Mobile data before Oct 2014 is not available.
- 0 values were reverted back to null values when graphing to capture the essence of the missing data. The views were not actually zero, even when there was no data.
- The background of the graph was set to blank, but it can be easily changed in Matplotlib based on user preference.

## API

- API calls are modeled after this [Jupyter Notebook](https://public.paws.wmcloud.org/User:Jtmorgan/data512_a1_example.ipynb).
- [Legacy Pagecount Endpoint](https://wikimedia.org/api/rest_v1/metrics/legacy/pagecounts/aggregate/{project}/{access-site}/{granularity}/{start}/{end})
- [Pageviews Endpoint](https://wikimedia.org/api/rest_v1/metrics/pageviews/aggregate/{project}/{access}/{agent}/{granularity}/{start}/{end})


### License and Terms of Use
Documentation for the Legacy Pagecounts API can be found [here](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts) 
Documentation for the Pageview API can be found [here](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) 
The license and terms of Wikimedia Foundation Rest API can be found [here](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions)
