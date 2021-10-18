# Introduction to GIS - Session 4
**Sciences Po Urban School, GETEC Masters, Fall semester 2021-2022**

**Lecturer: Raphaëlle Roffo**


### Session 4: Cartographic design**

*Class Content:*
- *Kepler.gl tutorial: quick off-the-shelf data visualisation*
- *Styling a map: basemap choice, preferred symbologies, class breaks definition, scale*
- *Exporting a map: setting up a layout and adding map elements (north arrow, scale bar, legend, title etc.) 

*Tutorial:*
- *Source and load basemaps*
- *Apply symbology of choice to vector data*
- *Export maps using layouts*


Loading basemaps (using Python)
https://opengislab.com/blog/2018/4/15/add-basemaps-in-qgis-30 
One way to add basemaps in QGIS is to use XYZ Tiles by connecting to a tile service. You can do that very quickly using the Python console!
Go to https://raw.githubusercontent.com/klakar/QGIS_resources/master/collections/Geosupportsystem/python/qgis_basemaps.py  . Select and copy the entire text on that page (Ctrl+A, Ctrl+C). Now open the Python Console, go to Plugins Menu >> Python Console.

Paste the script that you just copied. Run it and you should see a list of basemaps under the XYZ Tiles in the Browser panel.
That's it!


Symbology
https://docs.qgis.org/3.16/en/docs/training_manual/basic_map/symbology.html



scale dependent viz
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#scale-dependent-rendering


scratch layer
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#more-information-on-layers-and-groups-using-indicator-icon


Spatial bookmarks 
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#spatial-bookmarks 

Measuring
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#measuring 

colour selector
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#color-selector 