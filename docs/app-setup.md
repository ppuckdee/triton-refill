# App setup

This records the completed project's setup. Rebuilding the ArcGIS app requires your own accounts and configuration.

| Part | Setup |
| --- | --- |
| Station data | Publish the cleaned CSV to ArcGIS Online using latitude and longitude. |
| Map | Show station points, names, descriptions, and status notes. |
| Nearby search | Connect Map and Near Me; use a 500-meter search, ordered by distance. |
| Directions | Connect a routing utility; authorize public use and set request limits. Routing uses organization credits. |
| Street View | Connect an Embed widget to selected station features; insert latitude and longitude in the URL below. |
| Reports | Use Survey123 for status, notes, and optional photos. |
| Permissions | Keep the report source private; let the public submission view add reports without reading, updating, or deleting existing reports. |
| Dashboard | Keep report results, report map, and dashboard private. Exclude the known test records from results. |

## Street View URL

```text
https://www.google.com/maps/embed/v1/streetview?key=YOUR_API_KEY&location=LATITUDE,LONGITUDE
```

Insert the selected station's fields through Experience Builder's data picker. Use your own key, restricted to Maps Embed API and the actual website hosting your app. This project uses `https://experience.arcgis.com/*`. The notebook needs no key.

## Verification

The project owner confirmed app use, report submission with a photo, directions, and Street View without signing in. Desktop/mobile behavior and report permissions were checked during setup. The package's notebook checks cover the saved data and example search. No campus visits are recorded here.

## References

- [Esri: publish station data](https://doc.arcgis.com/en/arcgis-online/manage-data/publish-features.htm)
- [Esri: Near Me](https://doc.arcgis.com/en/experience-builder/latest/configure-widgets/near-me-widget.htm)
- [Esri: Embed widget](https://doc.arcgis.com/en/experience-builder/latest/configure-widgets/embed-widget.htm)
- [Google: Street View embeds](https://developers.google.com/maps/documentation/embed/embedding-map)
- [Google: API key restrictions](https://developers.google.com/maps/api-security-best-practices)
