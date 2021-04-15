# Overview

## Description

Barchart is the leading provider of global crop production and yield forecasts generated through geospatial data and machine learning models.  Daily forecasts for covered crops are released daily throughout the relevant growing season.

For North America, our weather data is aggregated from from Moderate Resolution Imaging Spectroradiometer (MODIS) satellite products and Global Historical Climatology Network Daily (GHCND) stations.  For South American forecasts, our models use MODIS and Climate Prediction Center (CPC). There are seven parameters that we use to make our foecasts which are:
* Normalized Difference Vegetation Index (NDVI)
* Normalized Difference Water Index (NDWI)
* Land Surface Temperature (LST) Day / Night
* Maximum and Minimum Temperature
* Precipitation

## What's Included?

|Dataset | Source |Country     | Coverage     | Crop                            | Start Day    | End Day | Frequency | History Start | 
| :---------------------:| :----------: | :----------: |:---------------------: | :----------: | :----------:  | :----------:  | :----------: | :-----------:
|N. Amer Production Forecasts| Barchart | US | N,S,D,C | corn | 153 | 305 | EOD | |
|N. Amer Production Forecasts| Barchart | US | N,S,D,C | soybean | 153 | 353 | EOD | |
|N. Amer Production Forecasts| Barchart | CA | N,P,D | corn | 129 | 209 | EOD | |
|N. Amer Production Forecasts| Barchart | CA | N,P,D | soybean | 121 | 249 | EOD | |
|N. Amer Production Forecasts| Barchart | CA | N,P,D | spring wheat | 185 | 249 | EOD | |

Location Dictionary - N = Nation, P = Province, S = State, P, D = District, C = County

## Product Roadmap

In the fure, we will also provide
1. county, district, state and national level forecast results for winter wheat in the United States in the first half of 2021;
2. department, province and national level forecast results for corn, soybean and wheat in Brazil in the first half of 2021;
3. microregion, state and national level forecast results for corn, soybean and wheat in Argentina in the first half of 2021.


## What Datasets Are Included?

Weather data used to make predictions:

|Dataset    | Parameter    | Source        | Data Coverage    | Frequency | Historical Start  | Historical End | Format |
| :---------------------: | :----------: | :----------: | :-----------: |:-----------: |:-----------: |:-----------: |:-----------:
| ndvi | ndvi | MODIS | Global     |Every 8 days| 2009-01-01  | at present  | double |
| ndwi | ndwi | MODIS | Global     |Every 8 days| 2009-01-01  | at present | double |
| lst | lst_day | MODIS | Global   |Every 8 days| 2009-01-01  | at present | double |
| lst | lst_night | MODIS | Global |Every 8 days| 2009-01-01  | at present | double |
| ghcnd | tmax | GHCND | North America |Every 8 days | 2009-01-01  |  at present | double |
| ghcnd | tmin | GHCND | North America |Every 8 days | 2009-01-01  | at present | double |
| ghcnd | prcp | GHCND | North America |Every 8 days | 2009-01-01  | at present | double |
| cpc | tmax | CPC | Global | Daily  | 2011-01-01  | at present | double |
| cpc | tmin | CPC | Global | Daily  | 2011-01-01  | at present | double |
| cpc | prcp | CPC | Global | Daily  | 2011-01-01  | at present | double |

Database used to save the forecast results:

|Dataset    | Feature    |  Data Coverage    | Frequency | 
| :---------------------: | :----------: | :----------: | :-----------: 
| county_prediction                | weather impact              | county level | Daily during crop season |
| county_ratio_prediction          | planted-harvested ratio     | county level | Daily during crop season |
| district_prediction              | weather impact              | district level | Daily during crop season |
| district_ratio_prediction        | planted-harvested ratio     | district level | Daily during crop season |
| state_prediction                 | weather impact              | state level | Daily during crop season |
| state_ratio_prediction           | planted-harvested ratio     | state level | Daily during crop season |
| state_harvest_prediction         | harvested acreage           | state level | Daily during crop season |
| state_production_prediction      | production                  | state level | Daily during crop season |
| national_prediction              | weather impact              | national level | Daily during crop season |
| national_ratio_prediction        | planted-harvested ratio     | national level | Daily during crop season |
| national_harvest_prediction      | harvested acreage           | national level | Daily during crop season |
| national_production_prediction   | production                  | national level | Daily during crop season |


## Data Source and processing
NDVI, NDWI, LST data is generated from MODIS satellite images. MODIS is a global product with 8-day period. The resolution of the original MODIS images is 250m https://modis-land.gsfc.nasa.gov/MODLAND_grid.html. For the US and Canada, we use the cropland data layer (CDL) with 30m resolution released by United States Department of Agriculture (USDA) and Government of Canda to find the pixels marked as the target crops. Then we calculate the mean values of weather data for each county or district.

For north america, the tmax, tmin, prcp data is generated from GHCND stations. GHCND stations are located all over the world, but the most of them are distributed in north america regions. For south america, these weather data is calculated from CPC data. CPC is also a global product, which is updated everyday. 

## API Structure

|Attribute                 | Value                            | Description    | 
| :---------------------: | :----------: | :----------: 
| index_group | County/District/State/National | Area level |
| crop | corn etc | Crop name |
| country | US etc | Country abbreviation |
| state | IL etc | State abbreviation |
| crop_district | 10 etc | District code of state |
| county_fips_code | 17001 etc | County_fips code |
| start_date | 2019-06-01 etc | Start date of forecast output |
| end_date | 2019-10-01 etc | End date of forecast output |
| intrument_type | indexYield/indexRatio/indexHarvest/indexProduction | Forecast result type |



## Support
For questions regarding the dataset, you may contact – cashdata@barchart.com


## Terms

* [Trials are available](https://www.barchart.com/cmdty/contact)
* Data is for internal use only, and redistribution is expressly forbidden
* Contact Barchart directly at cashdata@barchart.com for more information.


