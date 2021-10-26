# Session 4: Cartographic design

**Introduction to GIS | Sciences Po Urban School, GETEC Masters | Fall semester 2021-2022**

Lecturer: Raphaëlle Roffo

.

## **I. Session 4 Overview** 

*[See Slides](https://github.com/raphaelleroffo/intro-to-gis/blob/main/Session4/Intro%20to%20GIS%20-%20session%204.pdf)*

- *Cartographic design principles*
- *Accessibility*
- *Elements of a Map Layout*
- *Choropleths*
- *Choosing the right class breaks (number, method) and colour palette*

.
## **II. Tutorial**

### Goals:

- Loading data from Open Street Map
- Vector symbology
- Building a Choropleth
- Exporting a map: setting up a layout and adding map elements (north arrow, scale bar, legend, title etc.) 

.

### 1. Setting up

Download the `Session4-exercise` geopackage from GitHub. It contains the same London data as last week. Drag and drop the `Borough-Census` layer and the `School` layer onto your canvas. Make sure the CRS is set to EPSG:27700.

Pick a basemap of your choice from the `XYZ Tiles` section of your `Browser` panel. I'll be using `CartoDb Positron`.

<img src="../img/S4-01.png" width="700">


### 2. Loading OSM layer

Now, we have decided we want to look at cycling lanes in the Greater London Metropolitan Area. We will be using crowdsourced data from OpenStreetMap. In order to access this data, we will use the QGIS `QuickOSM` plugin. You can access it through your top menu: `Plugins` > `Manage and Install Plugins...`. Search for quickosm in your searchbar, install the plugin and close this window.

<img src="../img/S4-02.png" width="700">


Now, to access the plugin, you can either click the icon that appeared in your toolbar, or access it via your top menu: `Vector` > `QuickOSM`.

<img src="../img/S4-03.png" width="700">

This plugin basically enables you to query the (very large!) OpenStreetMap SQL database to load selected layers onto your map canvas. You can learn more about what you're querying [at this address](https://docs.3liz.org/QuickOSM/). Here, we will look for all the `cycleway` features and we don't really care about the values (are they one-way, shared lanes, etc) so leave that blank for now.

<img src="../img/S4-04.png" width="700">

Scroll down in the menu and select the spatial extent of your Boroughs layer as the query extent. It means you only want to download cycleways that are within the Greater London boundaries. Press `Run query`.


<img src="../img/S4-05.png" width="700">

After a few seconds to a few minutes, you shold get a success message and 4 new layers are loaded onto your canvas. Close the query window.

<img src="../img/S4-06.png" width="700">

Note that QuickOSM is a very powerful way for you to get access to feature geometries! However attributes can sometimes be a bit messy and tedious to navigate.


**Warning!** 
When you create a new layer using a geoprocessing tool, QGIS will produce a temporary layer, aka "scratch layer". This layer only exists for you in _this_ open session of QGIS and is not saved anywhere on your computer. This means unless you do something about it, the layer will be gone next time you reopen this project. Make sure you avoid this rookie mistake by checking that none of your layers display the little hairy box sign. If they do (like in this case, the layers you just queries from OSM) double click and save each of these layers into your project geopackage (giev each layer a meaningful name) or as a new shapefile in your project folder.

<img src="../img/S4-07.png" width="700">



### 3. Vector symbology

Symbology
https://docs.qgis.org/3.16/en/docs/training_manual/basic_map/symbology.html



You can also play with scale dependent rendering; using this feature, you control the appearance of your layer at different scales (for instance, you might want some layers to stop being visible when you zoom out of the area to avoid clutter)
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#scale-dependent-rendering




Spatial bookmarks
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#spatial-bookmarks 


Note: the colour selector can be a useful
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#color-selector 