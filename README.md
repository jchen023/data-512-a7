## Goal
The purpose of this project is to understand the relationship between covid, unemployment and the labor force. The project is the final assignment for the University of Washington DATA 512 [A7 assignment](https://docs.google.com/document/d/1nT1V8I-RLQN3ZxCjpF6Mse9w7-dP1_s1nnW7MfIevgk/edit#heading=h.cb9wthtz43qg). The goal for this project is to understand if we can use Granger causality test to prove whether the covid infection rate granger caused higher unemployment rate and lower labor force participation in Bernalillo County, NM. The final report is [here](https://docs.google.com/document/d/1cNug9Q91fM6t2z4gtcAEJCnU4c0hrTZeq5TK1WS80GU/edit?usp=sharing).


## Data Source
- [Kaggle repository of Johns Hopkins University COVID-19 data](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv): COVID-19 total case number by day by county.
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
|time|the month end date|calculated from Year and Month|
|unemployment_diff|the change in unemployment from the previous month|calculated from US Bureau of Labor Statistics|
|labor_force_diff|the change in labor force from the previous month|calculated from US Bureau of Labor Statistics|
|covid_monthly_infection_diff|the change in new covid infection in each month|calculated from Kaggle|


## Known Issues
- My research produced counterintuitive results that unemployment rate and labor force granger caused covid infection rate. That is likely caused by the public policy in the US and a lack of more granular employment data.
- The imprecision in determining the number of close contacts limited my ability to draw any conclusion regarding the mask effectiveness.


## Granger Causality Test Python Code
I utilized code from [Rishiraj Adhikary's public Github repository](https://rishi-a.github.io/2020/05/25/granger-causality.html).


## License and Terms of Use
- [Kaggle repository of Johns Hopkins University COVID-19 data](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv) is licnesed under Attribution 4.0 International (CC BY 4.0).
- [CDC Masking Mandate by State](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i) is government-published data for public use.
- License for [The New York Times mask compliance survey data](https://github.com/nytimes/covid-19-data/tree/master/mask-use) can be found [here](https://github.com/nytimes/covid-19-data/blob/master/LICENSE). It allows for non-commercial use and requires credit to NYT. 
- [US Bureau of Labor Statistics (Labor Force, not seasonally adjusted)](https://data.bls.gov/timeseries/LAUMT351074000000004?amp%253bdata_tool=XGtable&output_view=data&include_graphs=true) is government-published data for public use.
