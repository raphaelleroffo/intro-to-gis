# Introduction to GIS - Session 5
**Sciences Po Urban School, GETEC Masters, Fall semester 2021-2022**

**Lecturer: Raphaëlle Roffo**


### Session 5: Working with vector data: geoprocessing**

*Class Content:*

- *Use cases; why may you need to buffer, clip, intersect?*
- *Crossing multiple layers: common geoprocessing tools*
- *Walk-through common mistakes and data errors*
- *Coursework guidelines*

*Tutorial:*
- *Learn about the main geoprocessing tools, and where to find more advanced functionalities*






### Building a Choropleth

**4.1**

**4.2**

**4.3**


https://docs.qgis.org/3.16/en/docs/training_manual/vector_analysis/basic_analysis.html





### 5. Exporting a map: setting up a layout and adding map elements (north arrow, scale bar, legend, title etc.) 


**5.1 Introducing the Print Layout Composer**

We've established that GIS files ( `*.gqz` or geopackages) are a "recipe" to represent datasets as layers, and to display them in a specific way. Such files are _not_ images; if you want to export an image of your map (as `*.png`, `*.jpeg`, `*.pdf` or even to a printer directly), you must use the QGIS `Print Layout Composer`, which you can access from your menu `Project` > `New Print Layout...`. Give it a name such as `Session4-layout` and press Enter. 

<img src="../img/S4-63.png" width="700">


_Note that this layout, and the changes you make to it (and save) will now be accessible from your top menu `Project` > `Layouts` > ..._

<img src="../img/S4-65.png" width="700">

Back to your layout composer! It is for now a simple white space. Right-click on this blank space, select `Page properties…` and look at the context menu to your right. Make sure that you're working with an A4 map and the orientation is Landscape. Now we can start thinking about the elements to add to our layout. You can use the top menu `Add items`, or the corresponding icons to the left of the window. 

<img src="../img/S4-64.png" width="700">


First we'll want to add a Map. Click the `Add Map` button. With this tool activated, you can place a map on the page. Draw a box on the blank page:

<img src="../img/S4-66.png" width="700">

Once you release, your map appears on the page. You can move the box and edit its dimensions as much as you need. Now, let's explore how it links to your map canvas. Go back to your map canvas and switch to your other bookmark view (in my case: the `City & Canary Wharf` zoom). You can use this button to update the map on your layout to match the extent on the map canvas. You can also use the refresh button next to this one to refresh your layout when you've changed the layers that are turned on / off on your canvas. Please also note that a `Save` button is available for you to frequently save your changes to the layout.

<img src="../img/S4-67.png" width="700">


**5.2 Adding a legend**


**5.3**

**5.4**

