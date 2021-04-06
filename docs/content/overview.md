## Short Description

Production forecast overview consists of two parts, yield and harvested acreage forecast. Our forecast result is updated daily during crop season.

For north america, we gather weather data from Moderate Resolution Imaging Spectroradiometer (MODIS) satellite products and Global Historical Climatology Network Daily (GHCND) stations, while for south american, we use MODIS and Climate Prediction Center (CPC). We choose 7 parameters to make forecast, which are Normalized Difference Vegetation Index (NDVI), Normalized Difference Water Index (NDWI), Land Surface Temperature (LST) in day and night, maximum and minimum temperature, and precipitation. 

## Roadmap
For now, we provide 
1. county, district, state and national level forecast results for corn and soybean in the United States;
2. district, province and natioal level forecast results for Canada.

In the fure, we will also provide
1. county, district, state and national level forecast results for winter wheat in the United States in the first half of 2021;
2. department, province and national level forecast results for corn, soybean and wheat in Argentina in the first half of 2021;
3. microregion, state and national level forecast results for corn, soybean and wheat in Argentina in the first half of 2021.

The update time periods of the current national level results are shown as below:

|Country                 | Crop                            | Start Day    | End Day | 
| :---------------------: | :----------: | :----------: | :-----------:
| US | corn | 153 | 305 |
| US | soybean | 153 | 353 | 
| CA | corn | 129 | 209 |
| CA | soybean | 121 | 249 |
| CA | spring wheat | 185 | 249 |

The historical crop yield and production data is available in cmdtystats https://www.barchart.com/cmdty/data/fundamental/explore.


## What Datasets Are Included?

Weather data used to make predictions:

|Dataset    | Parameter    | Source        | Data Coverage    | Frequency | Historical Start  | Historical End | Format |
| :---------------------: | :----------: | :----------: | :-----------: |:-----------: |:-----------: |:-----------: |:-----------:
| ndvi | ndvi | MODIS | Global     |Every 8 days| 2009-01-01  | until now  | double |
| ndwi | ndwi | MODIS | Global     |Every 8 days| 2009-01-01  | until now | double | 
| lst | lst_day | MODIS | Global   |Every 8 days| 2009-01-01  | until now | double |
| lst | lst_night | MODIS | Global |Every 8 days| 2009-01-01  | until now | double |
| ghcnd | tmax | GHCND | North America |Every 8 days | 2009-01-01  |  until now | double |
| ghcnd | tmin | GHCND | North America |Every 8 days | 2009-01-01  | until now | double |
| ghcnd | prcp | GHCND | North America |Every 8 days | 2009-01-01  | until now | double |
| cpc | tmax | CPC | Global | Daily  | 2011-01-01  | until now | double |
| cpc | tmin | CPC | Global | Daily  | 2011-01-01  | until now | double |
| cpc | prcp | CPC | Global | Daily  | 2011-01-01  | until now | double |

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

For north america, the tmax, tmin, prcp data is generated from GHCND stations. GHCND stations are located all over the world, but most of them are distributed in north america regions. For south america, these weather data is calculated from CPC data. CPC is also a global product, which is updated everyday. 

## API Structure
(Need to discuss more with Mike)
|Attribute                 | Value                            | Description    | 
| :---------------------: | :----------: | :----------: 
| Start Date | 20180401 etc | Start date of downloading period |
| End Date | 20181028 etc | End date of downloading period |
| State | IL etc | State abbreviation |
| District | 10 etc | District code of state |
| County_fips | 0 | County_fips code |
| Polygon | (Python format polygon) | Polygon region of interest |


## User cases
Images are stored as the raster format of GeoTIFF with US district shape. Users can define polygon regions and the start-end period based on their own interests to effeciently read or download these GeoTIFF as series directly from Barchart database. Users can also input district or county fips code to directly get the information or download the corresponding images.
* One can monitor crop growth within a large or small region based on these past and current year data.
* One can investigate how to use EVI, NDVI, NDWI to make crop classification without downloading the whole tiles like before.
* One can study the changing tendency of vegetation features during crop season.
* One can take advantage of crop classification result to estimate the total production of crops within a certain region, to make better trading decisions such as futures based on these crop-classification.


## Support
For questions regarding the dataset, you may contact – cashdata@barchart.com


## Terms

* [Trials are available](https://www.barchart.com/cmdty/contact)
* Data is for internal use only, and redistribution is expressly forbidden
* Contact Barchart directly at cashdata@barchart.com for more information.


