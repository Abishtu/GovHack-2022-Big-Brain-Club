# GovHack 2022
* **Team: The Big Brain Club**
* **Project: Microfarming at scale**

![](Graphics/Big_Brain_Crest.svg)

Exploring the feasibility of creating a microfarming economy. Whether through community-based farms or privately owned farms, is there room to take the strain off the food supply in our increasingly growing population. Further, the option to reduce the reliance on imports for food will increase self-sufficiency for Australia. Transport emissions both international and domestic would be reduced due to the proximity of local farms and the centralised distribution centres.

## How They Work
* Farm location is decided based on government open datasets pertaining to [parks locations](https://www.data.qld.gov.au/dataset/built-features-queensland-series/resource/8cc4416e-0f0a-445b-9e90-9a1318366fa2) and [administrative zones](https://www.data.qld.gov.au/dataset/local-government-area-boundaries-queensland). 
* They are operated by community volunteers and they will form bodies to manage the farm, this includes quality controls, production, and other such regulations.
* The community farms will all internally have a section of land reserved for growing transplants. This operation is run the by councils.
* The farms will have a farm market to sell produce and transplants at a cheaper price to the community.
* In addition to this, the farms will also offer subsidies in the form of cheap or even free food to lower income members of the community, making it an open and inclusive environment.

### Internal Organisation of a Farm
![](Graphics/Garden_Map.png)

## App
As part of the solution we're including an app that can be used by members of the community to interact with their community farms, they can use the app to 
  * Check for availability of grown produce and transplants.
  * Find opertutnities to volunteer at the farm (minimum of 1 hour)
  * Have access to a daily overview of the farm, this includes information like
    * Stock availability of produce and transplants
    * News and updates on the farm an how its engaging with the community.

![](Graphics/combined.png)

## Data Processing 
[Rec Area Data] (https://www.data.qld.gov.au/dataset/built-features-queensland-series/resource/8cc4416e-0f0a-445b-9e90-9a1318366fa2)
[LGA Data] (https://www.data.qld.gov.au/dataset/local-government-area-boundaries-queensland)

We’ve used data from the Queensland Government to source potential locations of the microfarms. We used a vectorised spatial dataset about local government area boundaries and converted it into coordinates using QGIS. We’ve then used a second vectorised spatial dataset about every recreational area in the state. From this recreational area data set, we've kept only the parks and botanical gardens. We’ve then combined the information in both datasets to classify every park in Queensland into its local government area. We've then removed parks and local government areas that are rural or reigonal. Then, we've used a notebook to collate the parks available in each LGA that can be a potential community microfarm. 

This is just the beginning of this data-based solution. If we had more time, we would've used more data to find out exactly which parks were more suitable for community garden than others. e.g. a large park with dwindling visitor numbers would be a good candidate for a potential microfarm. Likewise, census time series profiles could be used to track which lgas have the largest increases in high density apartments etc. This would identify a populace without backyards that required community gardens more than other LGAs with plenty of single-unit housing. 

## Raw Data Analysis
* [Rec Area Raw Data](Data_Analytics/Recreation_areas.shp)
  Raw Spatial Data from Queensland Government about all recreational areas in Queensland 
* [LGA Raw Data](Data_Analytics/Local_Government_Areas.shp)
  Raw Spatial Data from Queensland Government about local government areas in Queensland 
* [Consumer Price Index (CPI) and wages](Data_Analytics/Data.ipynb)
* [Parks and LGAs](Data_Analytics/ParksToLGA.ipynb)
* [Processed Spatial Data](https://drive.google.com/drive/folders/1IiSZHWv2ENhMNbnsD0aOi2NgwzbNHjbe)
	* `vals.csv` is processed spatial data of the recreational areas into _(x,y)_ coordinates.
	* `vertex4.csv` is processed spatial data of LGA boundaries into _(x,y)_ coordinates. The processing was completed by extracting vertices in QGIS.
