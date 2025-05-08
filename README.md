## Analysis of the Impact of the Energy Sector on Air Quality and Human Development

I decided to explore the relationship between air quality, the number of power plants, and the Human Development Index (HDI). I believe that these attributes may be connected, at least because the level of air cleanliness can be directly dependent on the operation of certain types of power plants – if they are not environmentally friendly (e.g., coal power plants), air quality in the region will be below standard.

**Purpose of the Data:**
* **Power Plant Data:** Provides information on the type, capacity, and geographic distribution of energy sources, which allows for the analysis of energy self-sufficiency and the focus on renewable sources.
* **Air Quality Index (AQI) Data:** Used to assess the level of air pollution in different regions, allowing for an analysis of how different types of power plants affect air quality.
* **HDI Data:** Allows for evaluating how energy infrastructure impacts living standards and overall human development (health, education, income).

**Goal of the Analysis:** To identify patterns between energy sources, air quality, and human development, with a focus on the role of renewable energy sources in sustainable development.

### Data
For my work, I found 3 datasets that contain several files:

1. Global Powerplant Database
   - globalpowerplantdatabasev110
   - globalpowerplantdatabasev120
   - globalpowerplantdatabasev130
2. Air Quality Index Dataset
   - AQI Value.csv
   - Country.csv
   - Date.csv
   - Status.csv
3. Human Development Index Dataset
   - co2_emissions_dataset.csv
   - demographics_dataset.csv
   - gender_dataset.csv
   - gender_development_index_dataset.csv
   - gender_inequality_dataset.csv
   - hdi_dataset.csv
   - hdi_difference_dataset.csv
   - income_dataset.csv
   - inequality_dataset.csv
   - life_expectancy_dataset.csv
   - material_footprint_dataset.csv
   - planetary_pressures_hdi_dataset.csv
   - schooling_dataset.csv

All these files share a common column **country**, allowing them to be linked through it.

#### Data Sources

The data comes from publicly available sources, such as Kaggle and the World Resources Institute. These sources were selected based on their availability and reliability in researching environmental and socioeconomic factors. All data files were thoroughly checked and cleaned before processing to ensure the most accurate analysis. The goal of this part of the work is primarily to identify possible patterns and dependencies between the mentioned variables that may contribute to a better understanding of the industry's impact on quality of life.

- Global Power Plant Database - [source](https://datasets.wri.org/datasets/global-power-plant-database?map=eyJ2aWV3U3RhdGUiOnsibGF0aXR1ZGUiOjAsImxvbmdpdHVkZSI6MCwiem9vbSI6MywiYmVhcmluZyI6MCwicGl0Y2giOjAsInBhZGRpbmciOnsidG9wIjowLCJib3R0b20iOjAsImxlZnQiOjAsInJpZ2h0IjowfX0sImJhc2VtYXAiOiJsaWdodCIsImJvdW5kYXJpZXMiOmZhbHNlLCJsYWJlbHMiOiJkYXJrIiwiYWN0aXZlTGF5ZXJHcm91cHMiOlt7ImRhdGFzZXRJZCI6IjUzNjIzZGZkLTNkZjYtNGYxNS1hMDkxLTY3NDU3Y2RiNTcxZiIsImxheWVycyI6WyIyYTY5NDI4OS1mZWM5LTRiZmUtYTZkMi01NmMzODY0ZWMzNDkiXX1dLCJib3VuZHMiOnsiYmJveCI6bnVsbCwib3B0aW9ucyI6e319LCJsYXllcnNQYXJzZWQiOltbIjJhNjk0Mjg5LWZlYzktNGJmZS1hNmQyLTU2YzM4NjRlYzM0OSIseyJ2aXNpYmlsaXR5Ijp0cnVlLCJhY3RpdmUiOnRydWUsIm9wYWNpdHkiOjEsInpJbmRleCI6MTF9XV19)
- Air Quality Index Dataset - [source](https://www.kaggle.com/datasets/marieiris/aqi-value-over-the-years-in-different-countries)
- Human Development World Index Dataset - [source](https://www.kaggle.com/datasets/dqazg5/hdi-1990-2021/data)

#### Data Format

###### Global Power Plant Database

This is a comprehensive open-source database of power plants worldwide. It collects data on power plants to make it easier to navigate, compare, and extract insights for further analysis. The database includes approximately 35,000 power plants from 167 countries and covers thermal power plants (e.g., coal, gas, oil, nuclear, biomass, waste, geothermal) and renewable energy sources (e.g., hydro, wind, solar). Each power plant is geographically located, and the records contain information about the plant's capacity, generation, ownership, and fuel type. The data collection has 3 data files (several versions of the dataset), and I will use the most recent version in my work.

The latest version in the data collection currently contains 34,937 rows and 36 columns:
- **country**: Country code where the power plant is located (e.g., AFG for Afghanistan).
- **country_long**: Full name of the country.
- **name**: Power plant name.
- **gppd_idnr**: Unique identifier for the power plant in the Global Power Plant Database.
- **capacity_mw**: Installed capacity of the power plant in megawatts (MW).
- **latitude**: Geographic latitude of the plant.
- **longitude**: Geographic longitude of the plant.
- **primary_fuel**: Primary fuel used in the power plant (e.g., Hydro, Solar, Coal).
- **other_fuel1**: Additional fuel 1, if used.
- **other_fuel2**: Additional fuel 2, if used.
- **other_fuel3**: Additional fuel 3, if used.
- **commissioning_year**: Year the power plant was commissioned.
- **owner**: Owner of the power plant.
- **source**: Source of the station's data.
- **url**: URL for further information about the station.
- **geolocation_source**: Source of the station's geolocation data.
- **wepp_id**: Power plant identifier in the World Electric Power Plants database.
- **year_of_capacity_data**: Year the capacity data was collected.
- **generation_gwh_2013**: Actual electricity generation in 2013 in GWh (if available).
- **generation_gwh_2014**: Actual electricity generation in 2014 in GWh.
- **generation_gwh_2015**: Actual electricity generation in 2015 in GWh.
- **generation_gwh_2016**: Actual electricity generation in 2016 in GWh.
- **generation_gwh_2017**: Actual electricity generation in 2017 in GWh.
- **generation_gwh_2018**: Actual electricity generation in 2018 in GWh.
- **generation_gwh_2019**: Actual electricity generation in 2019 in GWh.
- **generation_data_source**: Source of electricity generation data.
- **estimated_generation_gwh_2013**: Estimated electricity generation in 2013 in GWh.
- **estimated_generation_gwh_2014**: Estimated electricity generation in 2014 in GWh.
- **estimated_generation_gwh_2015**: Estimated electricity generation in 2015 in GWh.
- **estimated_generation_gwh_2016**: Estimated electricity generation in 2016 in GWh.
- **estimated_generation_gwh_2017**: Estimated electricity generation in 2017 in GWh.
- **estimated_generation_note_2013**: Note on estimated electricity generation in 2013.
- **estimated_generation_note_2014**: Note on estimated electricity generation in 2014.
- **estimated_generation_note_2015**: Note on estimated electricity generation in 2015.
- **estimated_generation_note_2016**: Note on estimated electricity generation in 2016.
- **estimated_generation_note_2017**: Note on estimated electricity generation in 2017.

###### Air Quality Index Dataset

This dataset consists of 4 .csv files containing 4 columns: date, country, value, and status (a textual description of the AQI value).

This dataset contains the Air Quality Index (AQI) for most countries worldwide. The AQI is used for daily air quality reporting. It tells you how clean or polluted your air is and what associated health effects may be a concern for you. The AQI focuses on the health effects that may be experienced within hours or days after breathing polluted air.

The dataset provides daily updated AQI data for a wide range of countries around the world, offering a comprehensive view of global air quality trends. The AQI is calculated based on several major pollutants, including ground-level ozone, particulate matter (PM2.5 and PM10), carbon monoxide, sulfur dioxide, and nitrogen dioxide. It is a key tool for public health monitoring, as it helps assess the potential health risks associated with various pollution levels. This dataset can be valuable for research in environmental health, climate change, and the impact of pollution on public welfare.

The files contain the following columns:
- **Date**: The date when the air quality data was recorded.
- **Country**: The country where the air quality was measured.
- **Status**: The air quality status, describing the pollution level (e.g., good, unhealthy, hazardous).
- **AQI Value**: The Air Quality Index value, indicating how clean or polluted the air is and what health effects may be associated with those levels.

The dataset contains a total of 15,066 rows.

###### Human Development World Index Dataset

This dataset consists of 13 .csv files. Each file represents a logical unit responsible for a specific area related to the Human Development Index (HDI): CO2 emissions, gender inequality, HDI itself, life expectancy, material footprint, etc.

The Human Development Index (HDI) is a composite measure of key dimensions of human development: a long and healthy life, education, and a decent standard of living. It is calculated as the geometric mean of normalized indices for life expectancy, years of schooling, and Gross National Income (GNI) per capita. The HDI uses the logarithm of income, reflecting the diminishing returns of income at higher GNI levels. Although HDI provides an insight into national development, it does not account for inequalities, poverty, or empowerment. Other composite indices by HDRO address broader issues of human development, such as inequalities and gender differences.

This collection provides data on key dimensions of human development at the global, regional, and national/territorial levels with various composite indices. In addition to HDI, the indices include multidimensional poverty (MPI), inequality-adjusted HDI (IHDI), gender inequality (GII), gender development (GDI), planetary pressure-adjusted HDI (PHDI), and gender social norms index (GSNI).

This collection contains 196 rows (corresponding to 195 countries) and 880 columns (across all files). The columns represent values for the following indicators over different years, from 1990 to 2021 (or 2010-2021):
- **Adolescent Birth Rate**: The number of births per 1,000 women aged 15-19 years.
- **Carbon Dioxide Emissions per Capita Production in Tonnes**: Average CO2 emissions per person, measured in tonnes.
- **Coefficient of Human Inequality**: Measures inequality in areas like education, income, and life expectancy.
- **Expected Years of Schooling - Female**: The expected average number of years a girl will spend in school.
- **Expected Years of Schooling - Male**: The expected average number of years a boy will spend in school.
- **Expected Years of Schooling**: Total expected years of schooling for both genders.
- **Gender Development Index**: Compares HDI values for women and men to measure gender equality.
- **Gender Inequality Index**: Measures gender inequality in reproductive health, empowerment, and labor market participation.
- **Gross National Income Per Capita - Female**: The average income per woman in the country.
- **Gross National Income Per Capita - Male**: The average income per man in the country.
- **Gross National Income Per Capita**: The average income per person in the country, including both genders.
- **HDI Female**: The HDI value for women.
- **HDI Male**: The HDI value for men.
- **Human Development Index**: A composite index measuring life expectancy, education, and income per capita to assess country development.
- **Inequality Adjusted Human Development Index**: HDI adjusted for inequality in income distribution, education, and life expectancy.
- **Inequality in Education**: Measures inequality in access to education and its quality.
- **Inequality in Income**: Measures income distribution inequalities across the population.
- **Inequality in Life Expectancy**: Measures inequality in life expectancy between different population groups.
- **Labour Force Participation Rate - Female Percentage Ages 15 and Older**: The percentage of women aged 15 and older participating in the labor market.
- **Labour Force Participation Rate - Male Percentage Ages 15 and Older**: The percentage of men aged 15 and older participating in the labor market.
- **Life Expectancy at Birth - Female**: The expected number of years a female will live at birth.
- **Life Expectancy at Birth - Male**: The expected number of years a male will live at birth.
- **Life Expectancy at Birth**: The total average life expectancy at birth for both genders.
- **Material Footprint per Capita in Tonnes**: Measures the amount of raw material consumed per person, expressed in tonnes.
- **Maternal Mortality Ratio - Deaths per 100,000 Live Births**: The number of maternal deaths per 100,000 live births.
- **Mean Years of Schooling - Female**: The average number of years a woman has spent in school.
- **Mean Years of Schooling - Male**: The average number of years a man has spent in school.
- **Mean Years of Schooling**: The average number of years of schooling for the entire population.
- **Planetary Pressures Adjusted Human Development Index**: HDI adjusted for environmental pressures, such as CO2 emissions and resource use.

#### Data Adjustments

In my opinion, all three datasets are good examples for working with large data, but for convenience and consistency, I made a few small adjustments.

In the powerplant dataset, I kept the following columns in the latest version: country_long, capacity_mw, latitude, longitude, and primary_fuel. These columns provide essential information about power plants without overwhelming the dataset, so I removed the rest.

In the AQI dataset, I used only the files "Country.csv," "Date.csv," and "AQI Value.csv," as the "Status.csv" file doesn't provide much useful information. I preferred to rely on the AQI value column, which is numeric and easier to work with.

In the HDI dataset, I kept the following files: "demographics_dataset.csv," "co2_emissions_dataset.csv," "income_dataset.csv," "hdi_dataset.csv," and "life_expectancy_dataset.csv," for the period 2005-2019 (15 years), and removed the rest.

I also slightly adjusted the files in the HDI collection—using the pandas.melt function, I reshaped the columns into rows to create a table of values (Human Development Index, Life Expectancy at Birth, CO2 Emissions per Capita Production in Tonnes, Gross National Income Per Capita) for the period 2005 to 2019. This resulted in 4 updated files ("co2_updated.csv," "gni_updated.csv," "hdi_updated.csv," "life_expectancy_updated.csv"), each containing 3 columns, with 2 columns common across all files (country and year), and the third varying between the files.

Of course, I had to prepare the data for Elasticsearch, mostly by removing some columns and filling NaN values. The HDI dataset contained quite a few zero values, so I used forward fill to handle them. There were no NaN values in the other datasets.

For consistency, I also changed all country names to lowercase and changed Great Britain/United States to UK/USA (lowercase).

The Jupyter notebook, where I made all the aforementioned changes, is located in the "data" directory.

## Conclusion

In the second part of my work, I focused on analyzing the relationships between air quality, the number of power plants, and the Human Development Index (HDI). The aim was to identify patterns between these attributes, with a focus on the impact of renewable energy sources on sustainable development. To achieve this goal, I used three datasets: **Global Powerplant Database**, **AQI dataset**, and **HDI dataset**, which were prepared for indexing in the ELK stack.

After manipulating the data, indexing it, and configuring the related files (including docker-compose.yml, Logstash, Elasticsearch, and Kibana), I designed three more complex queries that allowed me to examine patterns between power plants, air quality, and human development. In the first query, I used a **wildcard** to filter countries with specific letters in their names, in the second query, I used **range** to filter AQI values, and in the third query, I combined **filtering** and **sorting** to retrieve documents with specific parameters. These queries allowed for the analysis of the influence of various factors on air quality and regional development.

For the analysis results, I created visualizations in Kibana that provided clear graphs and tables showing the relationships between these variables. The visualizations helped to better understand patterns, such as the correlation between AQI levels and power plant capacity in certain regions, or the influence of the number of renewable energy sources on HDI.

**Contribution**: My solution provided a deeper understanding of patterns between energy sources, air quality, and human development. Visualizations and advanced queries in the ELK stack enabled easy analysis of complex datasets and the creation of interactive tools for exploring these relationships. The results obtained can be valuable for supporting sustainable development and policies in the energy and environmental protection sectors.

**Challenges**: Some challenges arose when preparing the data for ELK, particularly when dealing with incomplete or inconsistent values in certain columns. Additionally, configuring the integration of multiple data files and efficiently linking them within the queries and visualizations was complex. Nevertheless, it was shown that the ELK stack is a powerful tool for analyzing and visualizing complex datasets, although it requires careful preparation and configuration to deliver optimal results.

This part of the work contributed to a better understanding of the relationships between these important factors and provided tools for further analysis and development of sustainable policies.

## References

#### Logstash Configuration and Pipelines
- [Logstash Configuration Files](https://www.elastic.co/guide/en/logstash/current/config-setting-files.html)
- [Logstash Pipelines](https://www.elastic.co/docs/current/serverless/logstash-pipelines)

#### Kibana and Elasticsearch
- [How to Create a Dashboard in Kibana](https://www.chaossearch.io/blog/how-to-create-kibana-dashboard)
- [Run API Requests with Console](https://www.elastic.co/guide/en/kibana/current/console-kibana.html)
- [Running Queries with Elasticsearch and Kibana](https://dev.to/elastic/running-queries-with-elasticsearch-and-kibana-2nd7)

#### Elastic Stack Overview
- [Official Elastic Stack Website](https://www.elastic.co/elastic-stack)

#### ELK Stack Guide
- [The Complete Guide to the ELK Stack](https://logz.io/learn/complete-guide-elk-stack/)