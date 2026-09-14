# Triton Refill

Find nearby water stations at UC San Diego.

**[Launch Triton Refill](https://experience.arcgis.com/experience/e5cdd600df2146a3a2d6cdd035e79d67)** · [Read the Code and Explanations](Triton_Refill.ipynb)

## What you can do

- Find stations near your location or a place you choose.
- Read station details and get directions.
- View nearby areas in Street View.
- Submit a station report with an optional photo.

Reports go to a private dashboard for the project owner to review.

## How it works

| Tool | Purpose |
| --- | --- |
| Python | Cleans the station list and tests a nearby search. |
| ArcGIS Online | Stores the station data and map. |
| Experience Builder | Builds the app people use. |
| Survey123 | Collects reports and photos. |
| ArcGIS Dashboards | Displays reports for private review. |
| Google Maps Embed API | Shows Street View inside the app. |

The app runs in ArcGIS. The notebook prepares the data and demonstrates a nearby search; it does not run each time someone uses the app.

## Try the notebook

1. Download `Triton_Refill.ipynb`.
2. Upload it to [Google Colab](https://colab.research.google.com/).
3. Run the code blocks from top to bottom.

The station list and step-by-step explanations are included. No ArcGIS account or Google Maps key is needed for the notebook. It saves tables as CSV files, and the final block downloads the cleaned station list.

For Jupyter, install the tools in `requirements.txt` and skip the final download block. Files are saved in the notebook’s working folder.

## Results

- **84** station entries saved.
- **31** missing descriptions filled with “No details provided.”
- **0** exact repeats found.
- **6** search checks passed.

![Distances to nearby stations](images/triton_refill_example.png)

Shorter bars mean closer stations. This example uses straight-line distances.

## Problems, fixes, and checks

| What we noticed | What we did or learned |
| --- | --- |
| Some descriptions were missing. | Added “No details provided” and kept the stations on the map. |
| Nearby distance could be mistaken for walking distance. | Labeled notebook distances as straight-line measurements and included Directions in the app. |
| Directions asked visitors to sign in. | Connected Route_World and authorized public use under Subscriber contents. Removed an extra unavailable search source. |
| The route-service page showed a 403 error. | Tested Directions in the app. The blocked information page did not mean route requests were unavailable. |
| Two reports appeared in the total, but the status counters showed zero. | Both reports were marked “Other,” so the counts were correct. |
| Practice reports appeared in the dashboard. | Filtered them out so they would not look like real station observations. |
| Reporting needed to be public while review stayed private. | Kept the survey and submission view public, with report data and the review dashboard private. Tested submission without signing in. |
| Photos needed to reach the reviewer. | Submitted a test photo and confirmed it appeared in the dashboard. |
| Different stations showed the same distant Street View. | Increased latitude and longitude—the location numbers—to six decimal places and removed number separators. |
| Street View showed an unfinished link before selection. | Added “Select a station to view Street View.” |
| The Google key included extra URL text. | Used only the key itself and let the code add the rest of the address. |
| A new formula caused black Street View screens. | Changed the Arcade format from `"0.000000"` to `"#.000000"` because the first format removed leading digits. Rebuilt the links from the original locations. |
| A station without usable Street View showed an unclear or previous view. | Left its saved link blank and displayed “Street View is not available at this location.” Confirmed this for Rogers Market. |

The main lesson was to check the saved information and generated links before changing the app. A calculation can run without errors and still produce the wrong location.

## Limits and upkeep

- Walking routes may be longer than the notebook’s straight-line distances.
- Station conditions and building access have not been confirmed. The visit log is blank.
- Street View searches within 50 meters and may show a nearby road instead of the exact water station.
- Missing Street View is marked **manually**. Clear that station’s `streetview_url` field—the “Street View link” column—to show the unavailable message. Keep the station on the map and preserve blank links during later repairs.
- The blank-link message does not automatically detect every Google loading error.
- Directions can use the organization’s ArcGIS credits.

After changes, save and publish the app. Test a station with working Street View, an unavailable station, and another working station to confirm the display changes correctly.

## Project files

| File or folder | Contents |
| --- | --- |
| `Triton_Refill.ipynb` | Code and beginner explanations |
| `requirements.txt` | Python tools needed for local use |
| `data/` | Station list, checks, example results, and blank visit log |
| `images/` | Example chart |
| `docs/app-setup.md` | App setup notes |
| `docs/github-upload-guide.md` | GitHub upload instructions |

## Data source

Station locations came from [UCSD Hydration Locations](https://www.google.com/maps/d/viewer?mid=18OFCg3GFp6wl5mCwioSvU9fdGAA&usp=sharing), linked by [UCSD HDH Sustainability](https://hdhsustainability.ucsd.edu/).

This project uses a saved copy; the original map’s update date is unknown. Credit belongs to the data owners. More sources are listed in the notebook.
