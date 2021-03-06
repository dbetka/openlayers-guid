# Line

Example how to draw single line by vectors.

<!-- tabs:start -->

#### **Global OL**

```js
const source = new ol.source.Vector()

const linePath = [
  [53.2341, 18.2352], // lon, lat
  [55.22351, 17.2352],
  [56.351, 16.2352],
  [58.2645, 6.2352]
]
const polyline = new ol.geom.LineString(linePath)
// Coordinates need to be in the view's projection, which is
// 'EPSG:3857' if nothing else is configured for your ol.View instance
polyline.transform('EPSG:4326', 'EPSG:3857')

source.addFeature(new ol.Feature(polyline))
const layer = new ol.layer.Vector({ source })
// Here should be map definition
map.addLayer(layer) // Explanation how create map is below in "Related pages"
```

#### **ES6 modules**

```js
import VectorSource from 'ol/source/Vector'
import LineString from 'ol/Feature'
import Feature from 'ol/Feature'

const source = new VectorSource()

const linePath = [
  [53.2341, 18.2352], // lon, lat
  [55.22351, 17.2352],
  [56.351, 16.2352],
  [58.2645, 6.2352]
]
const polyline = new LineString(linePath)
// Coordinates need to be in the view's projection, which is
// 'EPSG:3857' if nothing else is configured for your ol.View instance
polyline.transform('EPSG:4326', 'EPSG:3857')

source.addFeature(new Feature(polyline))
const layer = new VectorLayer({ source })
// Here should be map definition
map.addLayer(layer) // Explanation how create map is below in "Related pages"
```

<!-- tabs:end -->

#### Related pages:
* [How to create map](beginner/first-run.md)
* [How to use VectorSource](sources/vector.md)
* [How to use VectorLayer](layers/vector.md)
