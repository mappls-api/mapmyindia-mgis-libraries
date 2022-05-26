[<img src="https://about.mappls.com/images/mappls-b-logo.svg" height="60"/> </p>](https://www.mapmyindia.com/api)


mGIS Widgets
============

# Introduction #

mGIS Widget wrapper includes many out-of-the-box widgets.These widgets provide standard functions to easily create GIS web portals. 

This wrapper has all of the parameters that allow configuration and customization.

These widgets are categorized as integrated In-panel widgets which can be added to your app.

# List of Available mGIS Widgets #
1.Map View- 2D and 3D  
2.Workview  
3.Basemap Option  
4.Basic Map Tools  

# Demo #


![mGIS-widget](https://user-images.githubusercontent.com/103164131/165482651-8440ab8a-fccb-454d-9be7-c4b5ffa06d9b.gif)




**How to use mgis widget?**

* Add mgis-widget script into html page
```html
  <script src="./widgets.js"></script>
```
* Declare widget container where widget to be initialized
```javascript
  <div id="widgetContainer" style="height: 600px; width: 800px;"></div>
```
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
      "workViewName": "styleTest", // Load default workview
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
* Update widget properties
```javascript
  //Change View Mode
  mgisWidget.setWidgetProperties({
    "mapViewMode": viewMode
  });

  //Show Map Controls
  mgisWidget.setWidgetProperties({
    "mapControls": true
```
* Available Otions

  | Option        | Type | Default Value | Description |
  | ------------- | ------------- | ------------- |------------- |
  | widgetName    | String |  | Name of the widget |
  | widgetKey     | String |  | Use Access Token as widget key |
  | widgetOptions | Object |[widgetOptions](#widgetoptions)  | Widget options |

  * widgetOptions

  | **Option**     | **Type** | **Default Value** | **Description**                                 |
  |----------------|----------|-------------------|-------------------------------------------------|
  | mapViewMode    | String   | 2d                | 2d View mode of the map                         |
  |                |          | 3d                | 3d View mode of the map                         |
  | defaultBaseMap | String   | mmi-raster        | MMI Raster                                      |
  |                |          | mmi-vector        | MMI Vector                                      |
  |                |          | hr-imagery        | HR Imagery                                      |
  |                |          | hr-imagery-hybrid | HR Imagery Hybrid                               |
  |                |          | bhuvan-satellite  | Bhuvan Satellite                                |
  |                |          | bhuvan-hybrid     | Bhuvan Hybrid                                   |
  |                |          | no-basemap        | No Basemap                                      |
  |                |          | BSMP1             | OpenStreetMap                                   |
  |                |          | BSMP2H            | Google Hybrid                                   |
  |                |          | BSMP3RD           | Google Road                                     |
  |                |          | BSMP4ST           | Satellite                                       |
  |                |          | BSMP5             | Here Map                                        |
  | defaultView    | Object   |                   | Set the default view of the map                 |
  | mapControls    | Boolean  |  true             | Show the map controls                           |
  |                |          |  false            | Hide the map controls                           |
  | workViewName   | String   |                   | Set the workview name to load the workview data |

  * defaultView

  | Option | Type   | Default Value | Description                           |
  |--------|--------|---------------|---------------------------------------|
  | center | Array  |               | Set the center of the map. [lat,long] |
  | zoom   | Number |               | Set the zoom level of the map         |
  
  <br><br>
  <br><br>
  
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
