# Triton Refill

Find nearby water stations at UC San Diego.

**[Launch Triton Refill](https://experience.arcgis.com/experience/e5cdd600df2146a3a2d6cdd035e79d67)** · [Read the Code and Explanations](Triton_Refill.ipynb)

![Triton Refill map with station details and a Street View availability message](images/triton_refill_app.png)

*Experience Builder preview showing station details and the message for unavailable Street View.*

## What you can do

- Find stations near your location or a place you choose.
- Read station details and get directions.
- Look around nearby areas using Street View.
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

The station list and explanations are included. No ArcGIS account or Google Maps key is needed for the notebook. The final block downloads the cleaned station list.

For Jupyter, install the tools in `requirements.txt` and skip the final download block. Files are saved in the notebook’s working folder.

## Notebook results

| Check | Result |
| --- | --- |
| Station entries saved | 84 |
| Missing descriptions filled with “No details provided” | 31 |
| Exact repeats found | 0 |
| Search checks passed | 6 |

![Distances to nearby stations](images/triton_refill_example.png)

Shorter bars mean closer stations. This example uses straight-line distances, not walking routes.

## Main problems solved

| Problem | Fix |
| --- | --- |
| Directions asked visitors to sign in. | Connected the routing service and authorized its use in the public app. |
| Street View showed the wrong place. | Kept complete location numbers with six decimal places and repaired incorrectly built links. |
| Stations without usable Street View showed an unclear or previous view. | Left their saved links blank so the app displays “Street View is not available at this location.” These stations are marked manually. |

The main lesson: check the actual information sent to each tool and test what happens when information is missing.

[Read the full issue history, fixes, and testing steps](docs/troubleshooting.md).

## Limits

- Station conditions and building access have not been confirmed. The campus-visit log is blank.
- Walking routes may be longer than the notebook’s straight-line distances.
- Street View searches within 50 meters and may show a nearby road instead of the exact water station.
- Missing Street View is marked manually. The message does not automatically detect every Google loading error.
- Directions can use the organization’s ArcGIS credits.

## Project files

| File or folder | Contents |
| --- | --- |
| `Triton_Refill.ipynb` | Code and beginner explanations |
| `requirements.txt` | Python tools needed for local use |
| `data/` | Station list, check results, and blank visit log |
| `images/` | App preview and example chart |
| [App setup](docs/app-setup.md) | Notes about building the app |
| [Troubleshooting](docs/troubleshooting.md) | All 13 issues, fixes, and upkeep steps |
| [GitHub upload guide](docs/github-upload-guide.md) | Upload instructions |

## Data source

Station locations came from [UCSD Hydration Locations](https://www.google.com/maps/d/viewer?mid=18OFCg3GFp6wl5mCwioSvU9fdGAA&usp=sharing), linked by [UCSD HDH Sustainability](https://hdhsustainability.ucsd.edu/).

This project uses a saved copy; the original map’s update date is unknown. Credit belongs to the data owners. More sources are listed in the notebook.
