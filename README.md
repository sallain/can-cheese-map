# Canadian Artisanal Cheese Map

## Google Refine Template

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
        "url": "{{cells["WebSiteEn"].value}}",
        "text": "{{cells["FlavourEn"].value}}. {{cells["CharacteristicsEn"].value}} {{cells["CategoryTypeEn"].value}}, {{cells["MilkTypeEn"].value}}, {{cells["MilkTreatmentType"].value}}, {{cells["RindTypeEn"].value}}",
        "created_at": "{{cells["ManufacturerName"].value}}",
      }
    }`

**Row Separator**

`,`

**Suffix**

`], "type": "FeatureCollection"}`
