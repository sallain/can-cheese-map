# Canadian Artisanal Cheese Map

## Google Refine Template

Data from the [Canadian Cheese Directory](http://cheese-fromage.agr.gc.ca/).
Geolocated using [Google Places API](https://developers.google.com/places/) and mapped using [leaflet.js](http://leafletjs.com/).

A [#code4lib2015](http://wiki.code4lib.org/index.php/North#Code4Lib_North:_the_Sixth._St._Catharines_Public_Library.2C_June_4_.26_5.2C_2015) hackfest project by Thomas Guignard and Sara Allain.

Data cleanup was done using Open Refine. The cleaned-up data was exported from Open Refine into leaflet-happy geojson using the custom export feature found under *Export* > *Templating...*.

**Prefix**

`var cheese =
{
  "type": "FeatureCollection",
  "features": [`

**Row Template**

    `{
      "geometry": {
        "type": "Point", 
        "coordinates": [
          {{cells["Long"].value}},
          {{cells["Lat"].value}}
        ]
      }, 
      "type": "Feature", 
      "properties": {
        "name": "{{cells["CheeseName"].value}}", 
        "url": "{{cells["Website"].value}}", 
        "created_at": "{{cells["ManufacturerName"].value}}, {{cells["Province"].value}}",         
        "flavour": "{{cells["FlavourEn"].value}}",
        "characteristics": "{{cells["CharacteristicsEn"].value}}",
        "type": "{{cells["CategoryTypeEn"].value}} {{cells["MilkTypeEn"].value}} {{cells["MilkTreatmentType"].value}} {{cells["RindTypeEn"].value}}"
      }
    }`

**Row Separator**

`,`

**Suffix**

`], "type": "FeatureCollection"}`
