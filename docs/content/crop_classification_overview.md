## Short Description

Crop classification product is a land-cover mapping purpose prediction using remote-sensing imagery. This classification is based on three important features of crops, Normalized Difference Vegetation Index (NDVI), Enhanced Vegetation Index (EVI), Normalized Difference Water Index (NDWI). The training data comes from Sentinel-2 level-2A satelliate images. This product will be released anuually at the end of October or the beginning of November of current year.

## What's Included?

|Dataset                 | Source                            | Data Coverage    | Frequency | Format |
| :---------------------: | :----------: | :----------: | :-----------: |:-----------: |:-----------: |:-----------:
| crop-classification | Barchart | The United States | Anuually | Geotiff |

## Roadmap
This product is now available for the United States. The location coverage will increase to other great agricultural countries by 2021.

## Product Value
* One can take advantage of this product to estimate the total production of crops within a certain region, by which one will make better trading decisions such as futures based on these crop-classification.

## Data Format
Images are stored as raster format of GeoTIFF with US district shape. Users can input district or county fips code to directly get the information or download the corresponding images. All the classification values are the same as cropland data layer (CDL) released by USDA, except for the unclassified pixels, which will be marked as 255. At the same time, the NODATA value is 0. This product is generated from Sentinel-2 level-2A. To make it easy to use with CDL, the original tiles are reprojected and corrected to have the same coordinate reference system (CRS) and resolution with CDL. This means the resolution of our final product is 30m.


## Attributes

|Attribute                 | Value                            | Description    | 
| :---------------------: | :----------: | :----------: 
| Projection | EPSG:5070 | CDL native projection |
| Resolution | 30m | 30m*30m spatial resolution |
| Period | Annually | Crop classification is release annually |
| Band | 1 | Each GeoTIFF is stored as 1-band image |
| No Data Value| 0 | Same as Sentinel-2 level-2A |
| Unclassified pixel| 255 | Pixels cannot be classified due to long-term clouds |
| Data Type| Unit-16 | Values of GeoTIFF pixels format is uint-16 |
| Shape | District | Users can input district or county-fips to read and download |


## API Structure
|Attribute                 | Value                            | Description    | 
| :---------------------: | :----------: | :----------: 
| State | IL etc | State abbreviation |
| District | 10 etc | District code of state |
| County_fips | 0 | County_fips code |
| Polygon | (Python format polygon) | Polygon region of interest |


## Product Limitations
* There would be a gap of ~1 pixel between the results and scenes, which is caused by resampling during the projection process. But the shape will be the same as truth, which means little influence on crop production calculation.
* Some pixels cannot be effective classified due to long-term cloud issue. These pixels are masked with value 255.
* The boundary of district level data might be different from that of CDL, which is caused by the small difference of boundary shapefile. But the accuracy of value would not be affected.
* Only pixels that were farmland during the last year will be classified in our model. 


## Support
For questions regarding the dataset, you may contact – xin.shi@barchart.com, yi.jin@barchart.com

## Terms

* [Trials are available](https://www.barchart.com/cmdty/contact)
* Data is for internal use only, and redistribution is expressly forbidden
* Contact Barchart directly at cashdata@barchart.com for more information.


