## Section 1: Dataset General Information
#### What dataset do we offer?
For forecast result, we currently provide 10 datasets blow:

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

#### What is Normalized Difference Vegetation Index(NDVI)?
NDVI is the most popular indicator that can be used to assess how vegetation develops with time. NDVI ranges from -1 to 1.\
High NDVI values (approximately 0.6 to 0.9) correspond to dense vegetation such as that found in temperate and tropical forests or crops at their peak growth stage.\
Moderate NDVI values (approximately 0.2 to 0.5) correspond to sparse vegetation such as shrubs and grasslands or senescing crops.\
Areas of barren rock, sand, or snow usually show very low NDVI values (for example, 0.1 or less).

#### How NDVI is calculated?
The NDVI is derived from spectral reflectance measurements in the near-infrared region and in the red(visible) region, as follows:\
NDVI = (NIR - Red) / (NIR + Red)\
In general, if there is much more reflected radiation in near-infrared wavelengths than in visible wavelengths, then the vegetation in that pixel is likely to be dense.Subsequent work has shown that the NDVI is directly related to the photosynthetic capacity and hence energy absorption of plant canopies

#### What is Normalized Difference Water Index(NDWI)?
The Normalized Difference Water Index (NDWI) is a remote sensing derived index estimating the leaf
water content at canopy level. NDWI ranges between -1 to +1, , depending on the leaf water content but also on the vegetation type and cover.
It is therefore a very good proxy for plant water stress.  Its usefulness for drought monitoring and early warning has been demonstrated in different studies.

#### How NDWI is calculated?
The NDWI is derived from spectral reflectance measurements in the near-infrared region and in the short wave infrared (SWIR)  region, as follows:\
NDWI = (NIR - SWIR) / (NIR + SWIR)\
NDWI is sensitive to changes in liquid water content and in spongy mesophyll of vegetation canopies



## Section 2: Polygons

#### What is the minimum / maximum area of a polygon?

#### What happens if I create a polygon that is greater than or less than the specified minimum / maximum area limit?

#### What is a format of data is used to specify the polygon?

#### How do you calculate the total area of the polygons?


## Section 3: API

#### How do we process satellite imagery
