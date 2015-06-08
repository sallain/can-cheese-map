# Canadian Artisanal Cheese Map

## Google Refine Template

Used to export tabular data from Open Refine into geojson.

**Prefix**

var cheese =

`{
  "type": "FeatureCollection",
  "features": [`

** Row Template **
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

** Row Separator **
`,`

** Suffix **
`], "type": "FeatureCollection"}`
