# Session 6: 

**Introduction to GIS  ·  Sciences Po Urban School, GETEC Masters  ·  Fall semester 2021-2022**

Lecturer: Raphaëlle Roffo

&nbsp; 

## I. Session 6 Overview

**Download the [slides](https://github.com/raphaelleroffo/intro-to-gis/raw/main/Session5/Intro%20to%20GIS%20-%20session%205.pdf)**

*This final session is designed as a Q&A session. Students should have designed a methodology for the final coursework and are encouraged to prepare specific questions. Students will be able to select topics to be revisited in class, or to hear about more advanced GIS techniques if they wish.*

## II. Tutorial

### Goals:

- Carrying out a full risk visualisation exercise using vector data
- 

&nbsp; 


### Context:

In the Greater London metropolitan area, which local areas are the most likely to get flooded? 
What are the demographic characteristics of these areas (age, education, employment status, ethnicity, etc.)?
Visual exercise (not a full analytical exercise)


&nbsp; 

### Data:

Please download the [Session 6 geopackage](https://github.com/raphaelleroffo/intro-to-gis/raw/main/Session6/Session6-London.gpkg). Make sure the CRS is set to `EPSG:27700` and try to use a basemap of your choice from the `XYZ Tiles` section of your `Browser` panel (go back to the Session 3 tutorial for more information on how to load basemaps). I'm using `CartoDb Positron`.

Data sources:

- **flood_zones:** Flood Risk Zones: https://data.london.gov.uk/dataset/flood-risk-zones 
- **census:** Census data for London https://data.london.gov.uk/dataset/lsoa-atlas It’s a csv file (not geographic) and comes at the LSOA (Lower Super Output area) level…
- ... so we also need the LSOA geographic boundaries **lsoa**: https://geoportal.statistics.gov.uk/datasets/lower-layer-super-output-areas-december-2011-boundaries-ew-bfe-1 This LSOA dataset is national so... 
- **greater_london:** We need the Greater London boundaries to only keep the LSOAs we need https://data.london.gov.uk/dataset/inner-and-outer-london-boundaries-london-plan-consultation-2009 
