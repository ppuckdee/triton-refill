# Triton Refill

Find nearby water stations at UC San Diego.

**[Open the App](https://experience.arcgis.com/experience/e5cdd600df2146a3a2d6cdd035e79d67)** · [View the Notebook](Triton_Refill.ipynb)

## Author

Created by Nicholas Puckdee.

## What it does

- Finds stations near your location or a place you choose.
- Shows station details and directions.
- Displays nearby Street View images.
- Accepts station reports through forms with optional photos.

Reports appear in a private dashboard for the project owner.

## How it was built

| Tool | Purpose |
| --- | --- |
| Python | Cleans the station list and tests nearby searches. |
| ArcGIS Online | Stores the station data and map. |
| Experience Builder | Builds the app. |
| Survey123 | Collects reports and photos. |
| ArcGIS Dashboards | Displays submitted reports. |
| Google Maps Embed API | Provides Street View. |

The notebook prepares the data. The app runs in ArcGIS without running the notebook each time someone uses it.

## Run the notebook

1. Download `Triton_Refill.ipynb`.
2. Upload it to Google Colab.
3. Run each code block from top to bottom.

The station list and explanations are included. No ArcGIS account or Google Maps key is needed. The final block downloads the cleaned station list.

## Results

| Check | Result |
| --- | --- |
| Station entries | 84 |
| Missing descriptions filled | 31 |
| Exact repeats found | 0 |
| Search checks passed | 6 |

Missing descriptions were replaced with “No details provided.”

## Main problems solved

| Problem | Fix |
| --- | --- |
| Directions asked visitors to sign in. | Authorized the routing service for public use. |
| Street View showed the wrong location. | Fixed the location-number formatting and rebuilt the links. |
| Missing Street View left an unclear or previous image. | Marked affected stations manually and added “Street View is not available at this location.” |

Other checks confirmed that reports and photos could be submitted without signing in. Practice reports were hidden from the dashboard, and report review stayed private.

Main Lesson: Check the actual data and test what happens when information is missing.

## Limitations

- Notebook distances are straight-line measurements. Walking routes may be longer.
- Station conditions and building access have not been confirmed.
- Street View may show a nearby road instead of the exact station.
- Missing Street View must be marked manually.
- The search checks test the code. The campus-visit log is still blank.
- Directions can use the organization’s ArcGIS credits.

## Data source

Station locations came from [UCSD Hydration Locations](https://www.google.com/maps/d/viewer?mid=18OFCg3GFp6wl5mCwioSvU9fdGAA&usp=sharing), linked by UCSD HDH Sustainability.

This project uses a saved copy. The original map’s update date is unknown. Credit belongs to the data owners.
