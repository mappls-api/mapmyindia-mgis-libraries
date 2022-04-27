**How to use mgis widget?**

* Add mgis-widget script into html page
```html
  <script src="http://localhost:4200/widgets.js"></script>
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
