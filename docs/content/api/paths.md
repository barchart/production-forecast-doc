# Paths

## GET /getCropFeatures 

> The getCropFeatures API provides feature geospatial image of requested region. Crop features can be requested for state names, for district codes, for county_fips, and for self-define polygons. Crop features can be filtered by start date and end date, maximum, minimum or mean value of features.


**Summary**: Resturns feature geotiff image of requested region.

#### Query Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| apikey | <code>String</code> | true | false | The authorized API Key |
| locationType | <code>String</code> | true | false | The locationType points to location or a self-define polygon which identifies a certain region that geo-spatials image of feature will be returned for.<br> |
| location | <code>String</code> | true | false | A valid location have one format of below (1) state abbreviation, or (2) state name abbreviation + district code, or (3) county_fip. A valid self-define polygon consists of valid series of longitude and latitude pairs. Coordinates MUST follow the right-hand or left-hand rule with respect to the area it bounds. The location and self-define polygon are mutually exclusive.<br> |
| state | <code>String</code> | false | false | This is the two digits state abbreviation where geo-spatial images are requested.<br> |
| district_code | <code>String</code> | false | false | This is the two digits district_code of a certain state where geo-spatial images are requested. State abbreviation must be input if one wants to use district_code,<br> |
| fipsCode | <code>Integer</code> | false | false | A concatenation of state FIPS code and county FIPS code without separator to define the county that cash bids will be returned for. A list of possible values can be found at (here)[https://www.nass.usda.gov/Data_and_Statistics/County_Data_Files/Frequently_Asked_Questions/county_list.txt].<br> |
| polygon | <code>Object</code> | false | false | A self-define polygon consists of valid series of longitude and latitude pairs. Coordinates MUST follow the right-hand or left-hand rule with respect to the area it bounds.<br> |
| feature | <code>String</code> | true | false | The geo-spatials image of feature will be returned for<br> |
| featureType | <code>String</code> | false | false | All the options include 'maximum','minimum','mean' and the api query will return the corresponding feature type of a certain region. No data value will be excluded from summary.<br> |
| start date | <code>String</code> | true | false | Valid datetime which can determine the first day (inclusively) of requested geotiff image, formatted in YYYYMMDD<br> |
| end date | <code>String</code> | true | false | Valid datetime which can determine end day (exclusively) of requested geotiff image, formatted in YYYYMMDD<br> |

#### Responses

**Status Code**: 200

> OK

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetCropFeaturesResponse&gt;</code>](/content/api/components?id=schemasGetCropFeaturesResponse)

* * *

**Status Code**: 400

> Bad Request

* * *

**Status Code**: 500

> Internal Server Error

* * *

## GET /getCropClassification 

> The getCropClassification API provides crop classification geotiff image of requested region. Crop classification can be requested for state names, for district codes, for county_fips, and for self-define polygons. Crop features can be filtered by year.


**Summary**: Resturns crop classification geotiff image of requested region.

#### Query Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| apikey | <code>String</code> | true | false | The authorized API Key |
| locationType | <code>String</code> | true | false | The locationType points to location or a self-define polygon which identifies a certain region that geo-spatials image of feature will be returned for.<br> |
| location | <code>String</code> | true | false | A valid location have one format of below (1) state abbreviation, or (2) state name abbreviation + district code, or (3) county_fip. A valid self-define polygon consists of valid series of longitude and latitude pairs. Coordinates MUST follow the right-hand or left-hand rule with respect to the area it bounds. The location and self-define polygon are mutually exclusive.<br> |
| state | <code>String</code> | false | false | This is the two digits state abbreviation where geo-spatial images are requested.<br> |
| district_code | <code>String</code> | false | false | This is the two digits district_code of a certain state where geo-spatial images are requested. State abbreviation must be input if one wants to use district_code,<br> |
| fipsCode | <code>Integer</code> | false | false | A concatenation of state FIPS code and county FIPS code without separator to define the county that cash bids will be returned for. A list of possible values can be found at (here)[https://www.nass.usda.gov/Data_and_Statistics/County_Data_Files/Frequently_Asked_Questions/county_list.txt].<br> |
| polygon | <code>Object</code> | false | false | A self-define polygon consists of valid series of longitude and latitude pairs. Coordinates MUST follow the right-hand or left-hand rule with respect to the area it bounds.<br> |
| year | <code>Integer</code> | true | false | The year when crop classification images are requested.<br> |

#### Responses

**Status Code**: 200

> OK

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetCropClassificationResponse&gt;</code>](/content/api/components?id=schemasGetCropClassificationResponse)

* * *

**Status Code**: 400

> Bad Request

* * *

**Status Code**: 500

> Internal Server Error

* * *

