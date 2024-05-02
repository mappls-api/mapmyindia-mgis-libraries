[<img src="https://about.mappls.com/images/mappls-logo.svg" height="60"/> </p>](https://about.mappls.com/api/)


mGIS Widgets
============

# Introduction #

mGIS Widget wrapper includes many out-of-the-box widgets.These widgets provide standard functions to easily create GIS web portals. 

This wrapper has all of the parameters that allow configuration and customization.

These widgets are categorized as integrated In-panel widgets which can be added to your app.

# List of Available mGIS Widgets #
1.[Map View-2D and 3D](#Map-View-2D-and-3D)  
2.[Workview](#Workview)    
3.[Basemap Option](#Basemap-option)  
4.[Basic Map Tools](#Basic-Map-Tools)  
5.[3D Landmark](#3D-Landmark)  
6.[Real_View](#Real-View)   

# Demo #


![mGIS-widget](https://user-images.githubusercontent.com/103164131/165482651-8440ab8a-fccb-454d-9be7-c4b5ffa06d9b.gif)




**How to use mgis widget?**

* Add mgis-widget script into html page
```html
  <script src="https://mgis.mappls.com/mGIS_widgets/widgets.js"></script>
```
* Declare widget container where widget to be initialized
```javascript
  <div id="widgetContainer" style="height: 600px; width: 800px;"></div>
```

* Available Otions

  
| Option        | Type   | Default Value                   | Description                    |
|---------------|--------|---------------------------------|--------------------------------|
| widgetName    | String |                                 | Name of the widget             |
| widgetKey     | String |                                 | Use Access Token as widget key |
| widgetOptions | Object | [widgetOptions](#widgetoptions) | Widget options                 |


* widgetOptions

| Option          | Type    | Default Value | Description                                                                                                 |
|-----------------|---------|---------------|-------------------------------------------------------------------------------------------------------------|
| mapViewMode     | String  | 2d            | View mode of the map: "2d" or "3d"                                                                          |
| defaultBaseMap  | String  | mmi-raster    | Default base map options: "mmi-raster", "mmi-vector", "hr-imagery", "hr-imagery-hybrid", etc.             |
| defaultView     | Object  |               | Default view settings for the map (see below for details)                                                   |
| mapControls     | Boolean | true          | Whether to show map controls (true/false)                                                                   |
| workViewName    | String  |               | Name of the workview to load workview data                                                                  |
| Scene           | Array   |               | Scene options for adding 3D Landmark GLTF Object or 3D Landmark tile on Cesium (see below for details)      |

* defaultView

| Option | Type   | Default Value | Description                                       |
|--------|--------|---------------|---------------------------------------------------|
| center | Array  |               | Center of the map [latitude, longitude]           |
| zoom   | Number |               | Zoom level of the map                             |

* Scene

| Option          | Type    | Default Value | Description                                                  |
|-----------------|---------|---------------|--------------------------------------------------------------|
| timeline        | Boolean |               | Show/hide timeline bar from the scene                        |
| landmarkOptions | Object  |               | Landmark options for adding 3D landmarks on the scene (see below for details) |

* landmarkOptions

| Option    | Type   | Default Value | Description                                                     |
|-----------|--------|---------------|-----------------------------------------------------------------|
| type      | String | GLTF          | Type of 3D object: ".gltf" for GLTF object                      |
|           |        | TILESET       | "TILESET" for 3D tileset (collections of multiple tiles)        |
|           |        | TILE          | "TILE" for 3D tile (single tile)                               |
| name      | String |               | Name of the 3D object or tileset                                |
| url       | String |               | URL of the 3D landmark object or tileset                        |
| latitude  | Number |               | Latitude used to set the initial view of the 3D landmark object |
| longitude | Number |               | Longitude used to set the initial view of the 3D landmark object|
| height    | Number |               | Height of the 3D landmark object or tileset                     |


  

# Map View-2D and 3D

* Declare widget options
```javascript
// Widget options
  var widgetOptions = {
    "widgetName": "map-widget", //Name Of The Widget
    "widgetKey": "", // Access Token as widget key
    "widgetOptions":{ // Widget Options
      "mapViewMode": "2d", // Default view mode map 2d or 3d
      "defaultBaseMap": "mmi-raster", // Set Default Base Map
      "defaultView": { // Set Default View Of The Map
        "center": [
          28.7041,
          77.1025
        ],
        "zoom": 12
      },
      "mapControls": true, // Show/Hide map controls
    }
  }
```
* Create Instance of mgis-widget
```javascript
// Create widget
  var mgisWidget = new MGIS.Widget('widgetContainer',widgetOptions);
```
* Initialize mgis-widget
```javascript
  // Initialize widget
  mgisWidget.init();
```
* Update widget properties at run time
```javascript
  //Change View Mode
  mgisWidget.setWidgetProperties({
    "mapViewMode": viewMode
  });

  //Show Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": true
  });

  //Hide Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": false
  });
```
# Workview
* Declare widget options
```javascript
// Widget options
  var widgetOptions = {
    "widgetName": "map-widget", //Name Of The Widget
    "widgetKey": "", // Access Token as widget key
    "widgetOptions":{ // Widget Options
      "mapViewMode": "2d", // Default view mode map 2d or 3d
      "defaultBaseMap": "mmi-raster", // Set Default Base Map
      "defaultView": { // Set Default View Of The Map
        "center": [
          28.7041,
          77.1025
        ],
        "zoom": 12
      },
      "mapControls": true, // Show/Hide map controls
      "workViewName": "styleTest", // Load default workview,
    }
  }
```
 * Create Instance of mgis-widget

```javascript 
// Create widget
  var mgisWidget = new MGIS.Widget('widgetContainer',widgetOptions);
```
* Initialize mgis-widget
```javascript
  // Initialize widget
  mgisWidget.init();
```
* Update widget properties at run time
```javascript
  //Change View Mode
  mgisWidget.setWidgetProperties({
    "mapViewMode": viewMode
  });

  //Show Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": true
  });

  //Hide Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": false
  });

  //Hide Map Controls
  mgisWidget.setWidgetProperties({
    "workViewName": 'ww5'
  });
```
# Basemap Option

* Declare widget options
```javascript
// Widget options
  var widgetOptions = {
    "widgetName": "map-widget", //Name Of The Widget
    "widgetKey": "", // Access Token as widget key
    "widgetOptions":{ // Widget Options
      "mapViewMode": "2d", // Default view mode map 2d or 3d
      "defaultBaseMap": "mmi-raster", // Set Default Base Map
      "defaultView": { // Set Default View Of The Map
        "center": [
          28.7041,
          77.1025
        ],
        "zoom": 12
      },
      "mapControls": true, // Show/Hide map controls
    }
  }
```
* Create Instance of mgis-widget
```javascript
// Create widget
  var mgisWidget = new MGIS.Widget('widgetContainer',widgetOptions);
```
* Initialize mgis-widget
```javascript
  // Initialize widget
  mgisWidget.init();
```
* Update widget properties at run time
```javascript
  //Change View Mode
  mgisWidget.setWidgetProperties({
    "mapViewMode": viewMode
  });

  //Show Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": true
  });

  //Hide Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": false
  });
```
# Basic Map Tools

* Declare widget options
```javascript
// Widget options
  var widgetOptions = {
    "widgetName": "map-widget", //Name Of The Widget
    "widgetKey": "", // Access Token as widget key
    "widgetOptions":{ // Widget Options
      "mapViewMode": "2d", // Default view mode map 2d or 3d
      "defaultBaseMap": "mmi-raster", // Set Default Base Map
      "defaultView": { // Set Default View Of The Map
        "center": [
          28.7041,
          77.1025
        ],
        "zoom": 12
      },
      "mapControls": true, // Show/Hide map controls
    }
  }
```
* Create Instance of mgis-widget
```javascript
// Create widget
  var mgisWidget = new MGIS.Widget('widgetContainer',widgetOptions);
```
* Initialize mgis-widget
```javascript
  // Initialize widget
  mgisWidget.init();
```
* Update widget properties at run time
```javascript
  //Change View Mode
  mgisWidget.setWidgetProperties({
    "mapViewMode": viewMode
  });

  //Show Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": true
  });

  //Hide Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": false
  });
```
# 3D Landmark
* Declare widget options
```javascript
// Widget options
  var widgetOptions = {
    "widgetName": "map-widget", //Name Of The Widget
    "widgetKey": "", // Access Token as widget key
    "widgetOptions":{ // Widget Options
      "mapViewMode": "2d", // Default view mode map 2d or 3d
      "defaultBaseMap": "mmi-raster", // Set Default Base Map
      "defaultView": { // Set Default View Of The Map
        "center": [
          28.7041,
          77.1025
        ],
        "zoom": 12
      },
      "mapControls": true, // Show/Hide map controls
      "workViewName": "styleTest", // Load default workview,
      "Landmark3D":["BatchedThe_Clock_Tower","BatchedNew_Academic_Building"], //Show 3d Landmark - Applicable for view mode 3d only
    }
  }
  ```
  * Create Instance of mgis-widget
```javascript
// Create widget
  var mgisWidget = new MGIS.Widget('widgetContainer',widgetOptions);
```
* Initialize mgis-widget
```javascript
  // Initialize widget
  mgisWidget.init();
```
* Update widget properties at run time
```javascript
  //Change View Mode
  mgisWidget.setWidgetProperties({
    "mapViewMode": viewMode
  });

  //Show Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": true
  });

  //Hide Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": false
  });

  //Show 3d Landmark - Applicable for view mode 3d only
  mgisWidget.setWidgetProperties({
    "Landmark3D": ['BatchedMAX_AND_EXPORT_Chunk_02_04']
  });
```
# Real_View
* Declare widget options
```javascript
// Widget options
  var widgetOptions = {
    "widgetName": "map-widget", //Name Of The Widget
    "widgetKey": "", // Access Token as widget key
    "widgetOptions":{ // Widget Options
      "mapViewMode": "2d", // Default view mode map 2d or 3d
      "defaultBaseMap": "mmi-raster", // Set Default Base Map
      "defaultView": { // Set Default View Of The Map
        "center": [
          28.7041,
          77.1025
        ],
        "zoom": 12
      },
      "mapControls": true, // Show/Hide map controls
      "workViewName": "styleTest", // Load default workview,
      "Landmark3D":["BatchedThe_Clock_Tower","BatchedNew_Academic_Building"], //Show 3d Landmark - Applicable for view mode 3d only
      "enableRealView":true, // Show/Hide Real View
    }
  }
  ```
  * Create Instance of mgis-widget
```javascript
// Create widget
  var mgisWidget = new MGIS.Widget('widgetContainer',widgetOptions);
```
* Initialize mgis-widget
```javascript
  // Initialize widget
  mgisWidget.init();
```
* Update widget properties at run time
```javascript
  //Change View Mode
  mgisWidget.setWidgetProperties({
    "mapViewMode": viewMode
  });

  //Show Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": true
  });

  //Hide Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": false
  });

  //Hide Map Controls
  mgisWidget.setWidgetProperties({
    "workViewName": 'ww5'
  });

  //Show 3d Landmark - Applicable for view mode 3d only
  mgisWidget.setWidgetProperties({
    "Landmark3D": ['BatchedMAX_AND_EXPORT_Chunk_02_04']
  });
 ``` 



For any queries and support, please contact:<br> 
  [<img src="https://about.mappls.com/images/mappls-logo.svg" height="40"/> </p>](https://about.mappls.com/api/)
Email us at [apisupport@mappls.com](mailto:apisupport@mappls.com)


![](https://www.mapmyindia.com/api/img/icons/support.png)
[Support](https://about.mappls.com/contact/)
Need support? contact us!

<br></br>
<br></br>

[<p align="center"> <img src="https://www.mapmyindia.com/api/img/icons/stack-overflow.png"/> ](https://stackoverflow.com/questions/tagged/mappls-api)[![](https://www.mapmyindia.com/api/img/icons/blog.png)](https://about.mappls.com/blog/)[![](https://www.mapmyindia.com/api/img/icons/gethub.png)](https://github.com/Mappls-api)[<img src="https://mmi-api-team.s3.ap-south-1.amazonaws.com/API-Team/npm-logo.one-third%5B1%5D.png" height="40"/> </p>](https://www.npmjs.com/org/mapmyindia) 



[<p align="center"> <img src="https://www.mapmyindia.com/june-newsletter/icon4.png"/> ](https://www.facebook.com/Mapplsofficial)[![](https://www.mapmyindia.com/june-newsletter/icon2.png)](https://twitter.com/mappls)[![](https://www.mapmyindia.com/newsletter/2017/aug/llinkedin.png)](https://www.linkedin.com/company/mappls/)[![](https://www.mapmyindia.com/june-newsletter/icon3.png)](https://www.youtube.com/channel/UCAWvWsh-dZLLeUU7_J9HiOA)




<div align="center">@ Copyright 2022 CE Info Systems Ltd. All Rights Reserved.</div>

<div align="center"> <a href="https://about.mappls.com/api/terms-&-conditions">Terms & Conditions</a> | <a href="https://about.mappls.com/about/privacy-policy">Privacy Policy</a> | <a href="https://about.mappls.com/pdf/mapmyIndia-sustainability-policy-healt-labour-rules-supplir-sustainability.pdf">Supplier Sustainability Policy</a> | <a href="https://about.mappls.com/pdf/Health-Safety-Management.pdf">Health & Safety Policy</a> | <a href="https://about.mappls.com/pdf/Environment-Sustainability-Policy-CSR-Report.pdf">Environmental Policy & CSR Report</a>

<div align="center">Customer Care: +91-9999333223</div>
