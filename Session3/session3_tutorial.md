# Session 3: Working with vector data: the attribute table

**Introduction to GIS | Sciences Po Urban School, GETEC Masters | Fall semester 2021-2022**

Lecturer: Raphaëlle Roffo

.

## **I. Session 3 Overview** 

*[See Slides](xxxxxxx)*

- *Understanding the attribute table*
- *Querying data based on spatial qualities or their attributes*
- *Joining layers: why and how?*

.
## **II. Tutorial**

### Goals:

- Access summary statistics about a field
- Understand the attribute table
- Explore how features and records are related
- Create a new field in your attribute table 
- Create a refactored copy of a field (change the data type)
- Create a query to select features by attribute
- Use queries to only display a subset of your layer's features
- Create a point layer from a `*.csv` file
- Run an attribute-based join


.

### Statistics summary panel
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#statistical-summary-panel


### Building expressions
https://docs.qgis.org/3.16/en/docs/user_manual/working_with_vector/expression.html 
QGIS expressions are used to select features or set values. Writing an expression in QGIS follows some rules:

The dialog defines the context: if you are used to SQL, you probably know queries of the type select features from layer where condition or update layer set field = new_value where condition. A QGIS expression also needs all these information but the tool you use to open the expression builder dialog provides parts of them. For example, giving a layer (building) with a field (height):

pressing the expressionSelectSelect by expression tool means that you want to “select features from buildings”. The condition is the only information you need to provide in the expression text widget, e.g. type "height" > 20 to select buildings that are higher than 20.

with this selection made, pressing the calculateField Field calculator button and choosing “height” as Update existing field, you already provide the command “update buildings set height = ??? where height > 20”. The only remaining bits you have to provide in this case is the new value, e.g. just enter 50 to set the height of the previously selected buildings.

Pay attention to quotes: single quotes return a literal, so a text placed between single quotes ('145') is interpreted as a string. Double quotes will give you the value of that text so use them for fields ("myfield"). Fields can also be used without quotes (myfield). No quotes for numbers (3.16).


From the Field Calculator, calculate a “pop_density” field using the existing “total_pop” and “area_km2” fields:

"total_pop" / "area_km2"
Label or categorize features based on their area:

CASE WHEN $area > 10 000 THEN 'Larger' ELSE 'Smaller' END
Update the field “density_level” with categories according to the “pop_density” values:

CASE WHEN "pop_density" < 50 THEN 'Low population density'
     WHEN "pop_density" >= 50 and "pop_density" < 150 THEN 'Medium population density'
     WHEN "pop_density" >= 150 THEN 'High population density'
END
Apply a categorized style to all the features according to whether their average house price is smaller or higher than 10000€ per square metre:

"price_m2" > 10000
Using the “Select By Expression…” tool, select all the features representing areas of “High population density” and whose average house price is higher than 10000€ per square metre:

"density_level" = 'High population density' and "price_m2" > 10000
The previous expression could also be used to define which features to label or show on the map.

Create a different symbol (type) for the layer, using the geometry generator:

point_on_surface( $geometry )
Given a point feature, generate a closed line (using make_line) around its geometry:

make_line(
  -- using an array of points placed around the original
  array_foreach(
    -- list of angles for placing the projected points (every 90°)
    array:=generate_series( 0, 360, 90 ),
    -- translate the point 20 units in the given direction (angle)
    expression:=project( $geometry, distance:=20, azimuth:=radians( @element ) )
  )
)
In a print layout label, display the name of the “airports” features that are within the layout “Map 1” item:

with_variable( 'extent',
               map_get( item_variables( 'Map 1' ), 'map_extent' ),
               aggregate( 'airports', 'concatenate', "NAME",
                          intersects( $geometry, @extent ), ' ,'
                        )
             )





ALL FUNCTIONS: https://docs.qgis.org/3.16/en/docs/user_manual/working_with_vector/functions_list.html 


If you are used to Python and want to define your own custom function, you may use the function editor: https://docs.qgis.org/3.16/en/docs/user_manual/working_with_vector/expression.html#function-editor 
More info here https://docs.qgis.org/3.16/en/docs/pyqgis_developer_cookbook/index.html#pyqgis-developer-cookbook 















### Displaying only a subset of your data
https://docs.qgis.org/3.16/en/docs/user_manual/working_with_vector/vector_properties.html#query-builder
The Query Builder dialog is accessible through the eponym button at the bottom of the Source tab in the Layer Properties dialog, under the Provider feature filter group.

The Query Builder provides an interface that allows you to define a subset of the features in the layer using a SQL-like WHERE clause and to display the result in the main window. As long as the query is active, only the features corresponding to its result are available in the project.




### Fields Property 
https://docs.qgis.org/3.16/en/docs/user_manual/working_with_vector/vector_properties.html#fields-properties 

sourceFields The Fields tab provides information on fields related to the layer and helps you organize them.

The layer can be made editable using the toggleEditing Toggle editing mode. At this moment, you can modify its structure using the newAttribute New field and deleteAttribute Delete field buttons.

You can also rename fields by double-clicking its name. This is only supported for data providers like PostgreSQL, Oracle, Memory layer and some OGR layer depending on the OGR data format and version.

If set in the underlying data source or in the forms properties, the field’s alias is also displayed. An alias is a human readable field name you can use in the feature form or the attribute table. Aliases are saved in the project file.

Depending on the data provider, you can associate a comment with a field, for example at its creation. This information is retrieved and shown in the Comment column and is later displayed when hovering over the field label in a feature form.

Other than the fields contained in the dataset, virtual fields and Auxiliary Storage included, the Fields tab also lists fields from any joined layers. Depending on the origin of the field, a different background color is applied to it.

For each listed field, the dialog also lists read-only characteristics such as its type, type name, length and precision. When serving the layer as WMS or WFS, you can also check here which fields could be retrieved.




### Selecting features
https://docs.qgis.org/3.16/en/docs/user_manual/introduction/general_tools.html#interacting-with-features


### Importing a Delimited Text File:
https://docs.qgis.org/3.16/en/docs/user_manual/managing_data_source/opening_data.html#importing-a-delimited-text-file 

In QGIS, you can load spatial **and** non-spatial tables. Vector layers are spatial tables; each vector layer contains a geometry and an attribute table. But you can also load **delimited text files** in your QGIS projects (files such as `*.csv`, `*.txt`, `*.dat` or `*.wkt`). They may only contain text, or they may contain coordinates / geometries that you could want to utilize. This is what the `Add Delimited Text Layer` import tool is designed for.



### Loading OSM layer
https://docs.qgis.org/3.16/en/docs/training_manual/qgis_plugins/plugin_examples.html#hard-fa-the-quickosm-query-engine 


### Joining two layers based on attributes
https://docs.qgis.org/3.16/en/docs/user_manual/working_with_vector/vector_properties.html#joins-properties

### Joining two layers based on location