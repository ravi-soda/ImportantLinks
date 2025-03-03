 
 
const [region, setRegion] = useState<Region>(null)
return (
    <MapView
      onRegionChange={setRegion}>
      <Marker 
        coordinate={{ latitude: region ? region.latitude : 0, longitude: region ? region.longitude : 0 }}
      />
    </MapView>
)


 
Additional UI Suggestions:
Seeing Property reviews and directions
Marker Clustering
Custom Marker Clustering https://visgl.github.io/react-google-maps/examples/custom-marker-clustering 
 
To 
Drwaing on Map
 
Circle overlay in market with radius info
 
https://visgl.github.io/react-google-maps/examples/geometry 
Heat Map: https://visgl.github.io/react-google-maps/examples/heatmap
 
Ref: 
Map overlay smooth transition: https://jsfiddle.net/javigbas/3zx5xa2u/ 
React Map example: https://codesandbox.io/p/sandbox/react-google-maps-overlay-view-issue-oyc6b?file=%2Fnode_modules%2F.store%2F%40react-google-maps%2Fapi%401.3.0%2Fnode_modules%2F%40react-google-maps%2Fapi%2Fdist%2Fcomponents%2Fdom%2FOverlayView.d.ts%3A22%2C1-23%2C1
Show start icons on map for selected/favourte properties
Show Filters as pills 
https://stackoverflow.com/questions/47527675/react-google-map-how-to-add-click-listener-to-the-overlay-element-to-stoppropo 
https://stackoverflow.com/questions/78110260/google-maps-ground-overlay-malfunctioning-when-zooming-moving-or-panning 
https://alizahid.dev/blog/keep-marker-in-center-and-move-map-around-it 
https://github.com/alizahid/location-picker-demo

https://mungfali.com/explore/ArcGIS-Power-BI-Heat-Map
https://www.radix.com/solutions-for-multifamily-renters-and-residents/
https://siliconangle.com/2012/10/11/project-hestia-maps-carbon-emissions-at-street-level/
Important ! https://www.qikmaps.com.au/qikmaps-property.html
https://www.geospatialworld.net/news/esri-ubermedia-announce-partnership-provide-retailers-location-specific-data/
