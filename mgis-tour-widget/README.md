[<img src="https://about.mappls.com/images/mappls-logo.svg" height="60"/> </p>](https://about.mappls.com/api/)


# mGIS Tour Widget

The mGIS Tour Widget enhances your app with immersive 3D terrain drive through. This powerful widget allows users to explore and simulate navigation on a three-dimensional Earth model. With customizable parameters, you can fine-tune the tour experience to suit your specific needs.

</br>

<div align="center">
<img src="../docs/images/mgis-widget-tour.gif" alt="mGIS Tour Widget Intro GIF"/>
</div>

</br>

This is a comprehensive guide to the mGIS Tour widget and its implementation. It's structured to help you quickly understand, set up, and use our widget effectively. Use this table of contents to navigate directly to the information you need:

* [Getting Started](#getting-started)
  * [Usage Example](#follow-these-steps-to-get-started-with-mgis-tour-widget)
  * [Sample Code](#sample-code)
* [Userguide](#userguide)
  * [Widget Usage Guide](#how-to-use-the-mgis-tour-widget)
  * [Widget Controls](#controls-on-the-mgis-tour-widget)
* [Config](#config)



## Getting Started

### Follow these steps to get started with mGIS Tour Widget

* Add mGIS widget script into html page
```javascript
<script src="https://mgis.mappls.com/mGIS_3d_widget/widgets.js">
</script>
```


* Declare widget container where widget has to be initialized
```javascript
<div id="widgetContainer" style="height:95vh; width: 1555px;"></div>
```

* Declare widget options
```javascript
var widgetOptions = {
  "widgetName": "map-widget", //Name Of The Widget
  "widgetKey": "YOUR_ACCESS_TOKEN", // Access Token as widget key
  "widgetOptions":{ // Widget Options
    "mapViewMode": "3d", // Default view mode map 2d or 3d
    "defaultBaseMap": "BSMP4ST", // Set Default Base Map
    "defaultView": { // Set Default View Of The Map
      "center": [
        28.7041,
        77.1025
      ],
      "zoom": 5
    },
    "mapControls": true, // Show/Hide map controls
    "basemapControls": true, // Show/Hide basemap controls
    "scene":{
      "scenetoolbarControls":{
        "routing" : {
            "tourFlag" : false,
            "tourPathFlag" : true
        }
      },
    }
  }
}
```

* Create Instance of mGIS widget
```javascript
var mgisWidget = new MGIS.Widget("widgetContainer",widgetOptions);
```

* Initialize mGIS widget
```javascript
mgisWidget.init();
```

* Update widget properties
```javascript
//Show Map Controls
mgisWidget.setWidgetProperties({
  "mapControls": true
});

//Hide Map Controls
mgisWidget.setWidgetProperties({
  "mapControls": false
});
```

### Sample Code

To quickly get started with our widget, copy and paste the following code snippet into your project. Replace "YOUR_ACCESS_TOKEN" in the "widgetKey" field with your actual access token.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta http-equiv="Content-Security-Policy" content="upgrade-insecure-requests">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>mGIS Widget</title>
  <script src="https://mgis.mappls.com/mGIS_3d_widget/widgets.js"></script>
</head>
<body>
  <div id="widgetContainer" style="height:95vh; width: 1555px;"></div>
  <script>
    // Widget options
    var widgetOptions = {
      "widgetName": "map-widget", //Name Of The Widget
      "widgetKey": "YOUR_ACCESS_TOKEN", // Access Token as widget key
      "widgetOptions":{ // Widget Options
        "mapViewMode": "3d", // Default view mode map 2d or 3d
        "defaultBaseMap": "BSMP4ST", // Set Default Base Map
        "defaultView": { // Set Default View Of The Map
          "center": [
            28.7041,
            77.1025
          ],
          "zoom": 5
        },
        "mapControls": false, // Show/Hide map controls
        "basemapControls": true, // Show/Hide basemap controls
        "scene":{        
          "scenetoolbarControls":{
            "routing" : {
                "tourFlag" : false,
                "tourPathFlag" : true
            }
          },
        }
      }
    }
    // Create widget object
    var mgisWidget = new MGIS.Widget("widgetContainer",widgetOptions);
    // Initialize widget
    mgisWidget.init().then((response)=>{
        //Widget Loaded Successfully
        console.log(response);
    }).catch((error)=>{
        //Widget Loading Failed
        console.log(error);
    });
  </script>
</body>
</html>
```

This code initializes the widget with default settings. You can customize the options as needed. Don't forget to replace "YOUR_ACCESS_TOKEN" with the unique access token provided to you.

## Userguide

#### How to use the mGIS Tour widget?
1. Upload File
    * Upload a GeoJSON or KML file containing single or multiple, LineString or Point type data.
2. Select Route
    * If the file contains more than one data entry, a table will pop up to select one of them to route.
3. Select map controls (Optional)
    * Auto control (Handles map control automatically)
    * Manual control (User are able to control the maps)
4. Start Route
    * Click on any uploaded route to start the tour.

#### Controls on the mGIS Tour widget
* Play/Pause
    * Press "space" to play/pause the tour.
* Speed Up
    * Press "Shift + Up Arrow" to speed up.
* Speed Down
    * Press "Shift + Down Arrow" to slow down.
* Upload new tour route icon
    * To  upload new icon from the details and instruction section
* Reset/Start
    * Reset/Start button are also available in the details and instructions section

## Config

* #### Widget

    | Option                          | Type   | Default Value | Description                    |
    |---------------------------------|--------|---------------|--------------------------------|
    | widgetName                      | String |               | Name of the widget             |
    | widgetKey                       | String |               | Use Access Token as widget key |
    | [widgetOptions](#widgetoptions) | Object |               | Widget options                 |

* #### widgetOptions

    | Option                      | Type    | Value     | Description                                                                                                           |
    |-----------------------------|---------|-------------------|-----------------------------------------------------------------------------------------------------------------------|
    | mapViewMode                 | String  | 2d                | 2d View mode of the map                                                                                               |
    |                             |         | 3d                | 3d View mode of the map                                                                                               |
    | defaultBaseMap              | String  | mmi-raster        | MMI Raster                                                                                                            |
    |                             |         | mmi-vector        | MMI Vector                                                                                                            |
    |                             |         | hr-imagery        | HR Imagery                                                                                                            |
    |                             |         | hr-imagery-hybrid | HR Imagery Hybrid                                                                                                     |
    |                             |         | bhuvan-satellite  | Bhuvan Satellite                                                                                                      |
    |                             |         | bhuvan-hybrid     | Bhuvan Hybrid                                                                                                         |
    |                             |         | no-basemap        | No Basemap                                                                                                            |
    |                             |         | BSMP1             | OpenStreetMap                                                                                                         |
    |                             |         | BSMP2H            | Google Hybrid                                                                                                         |
    |                             |         | BSMP3RD           | Google Road                                                                                                           |
    |                             |         | BSMP4ST           | Satellite                                                                                                             |
    |                             |         | BSMP5             | Here Map                                                                                                              |
    | [defaultView](#defaultview) | Object  |                   | Set the default view of the map                                                                                       |
    | mapControls                 | Boolean | true/false              | Whether to show map controls (true/false)                                                                             |
    | basemapControls             | Boolean | true/false              | Whether to show map controls (true/false)                                                                             |
    | workViewName                | String  |                   | Name of the workview to load workview data                                                                            |
    | Landmark3D                  | Array   | []                | Set the 3d Landmark Names to show 3d landmark on cesium, This option work for view mode 3d only                       |
    | enableRealView              | Boolean | true/false             | Show/Hide Real View                                                                                                   |
    | [scene](#scene)             | Object  |                   | Set the scene controls to show 3d simulation with different 3d models. This option work for view mode 3d only. |


* #### defaultView

    | Option | Type   | Default Value | Description                                     |
    |--------|--------|---------------|-------------------------------------------------|
    | center | Array  |               | Set the Center of the map [latitude, longitude] |
    | zoom   | Number |               | Set the Zoom level of the map                   |

* #### scene

    | Option                                        | Type   | Default Value | Description                                                                                                                    |
    |-----------------------------------------------|--------|---------------|--------------------------------------------------------------------------------------------------------------------------------|
    | [sceneToolbarControls](#scenetoolbarcontrols) | Object |               | Set the sceneToolbarControls controls to show 3d simulation with different 3d models. This option works for view mode 3d only. |



* #### sceneToolbarControls

    | Option              | Type   | Default Value | Description                       |
    |---------------------|--------|---------------|-----------------------------------|
    | [routing](#routing) | Object |               | Set the routing controls for tour |



* #### routing

    | Option   | Type    | Default Value | Description        |
    |----------|---------|---------------|--------------------|
    | tour     | Boolean | false         | Show/Hide tour     |
    | tourPath | Boolean | false         | Show/Hide tourPath |                  |


<hr/>

For any queries and support, please contact:
<br></br>
  [<img src="https://about.mappls.com/images/mappls-logo.svg" height="40"/> </p>](https://about.mappls.com/api/)
Email us at [apisupport@mappls.com](mailto:apisupport@mappls.com)


![](https://www.mapmyindia.com/api/img/icons/support.png)
[Support](https://about.mappls.com/contact/)
Need support? contact us!

<br></br>
<br></br>

[<p align="center"> <img src="https://www.mapmyindia.com/api/img/icons/stack-overflow.png"/> ](https://stackoverflow.com/questions/tagged/mappls-api)[![](https://www.mapmyindia.com/api/img/icons/blog.png)](https://about.mappls.com/blog/)[![](https://www.mapmyindia.com/api/img/icons/gethub.png)](https://github.com/Mappls-api)[<img src="https://mmi-api-team.s3.ap-south-1.amazonaws.com/API-Team/npm-logo.one-third%5B1%5D.png" height="40"/> </p>](https://www.npmjs.com/org/mapmyindia)



[<p align="center"> <img src="https://www.mapmyindia.com/june-newsletter/icon4.png"/> ](https://www.facebook.com/Mapplsofficial)[![](https://www.mapmyindia.com/june-newsletter/icon2.png)](https://twitter.com/mappls)[![](https://www.mapmyindia.com/newsletter/2017/aug/llinkedin.png)](https://www.linkedin.com/company/mappls/)[![](https://www.mapmyindia.com/june-newsletter/icon3.png)](https://www.youtube.com/channel/UCAWvWsh-dZLLeUU7_J9HiOA)




<div align="center">@ Copyright 2024 CE Info Systems Ltd. All Rights Reserved.</div>

<div align="center"> <a href="https://about.mappls.com/api/terms-&-conditions">Terms & Conditions</a> | <a href="https://about.mappls.com/about/privacy-policy">Privacy Policy</a> | <a href="https://about.mappls.com/pdf/mapmyIndia-sustainability-policy-healt-labour-rules-supplir-sustainability.pdf">Supplier Sustainability Policy</a> | <a href="https://about.mappls.com/pdf/Health-Safety-Management.pdf">Health & Safety Policy</a> | <a href="https://about.mappls.com/pdf/Environment-Sustainability-Policy-CSR-Report.pdf">Environmental Policy & CSR Report</a>

<div align="center">Customer Care: +91-9999333223</div>
