# Triton Refill

Find nearby water stations at UC San Diego.

**[Launch Triton Refill](https://experience.arcgis.com/experience/e5cdd600df2146a3a2d6cdd035e79d67)** · [Explore the Python Notebook](Triton_Refill.ipynb)

## What it does

- Finds stations near your location or a point you choose.
- Shows station details and directions.
- Opens nearby Street View imagery.
- Accepts station reports with optional photos.
- Keeps a private dashboard for reviewing reports.

## How it was built

Python cleans the station list and demonstrates a nearby search. ArcGIS Online stores the map data. Experience Builder runs the app. Survey123 collects reports, and ArcGIS Dashboards displays them. Google Maps Embed API supplies Street View.

The app runs in ArcGIS. This repository contains the notebook, example files, and setup notes.

## Try the notebook

1. Download `Triton_Refill.ipynb`.
2. Upload it to [Google Colab](https://colab.research.google.com/).
3. Run the blocks from top to bottom.

The station list is already inside. No ArcGIS account or Google API key is needed to run the notebook. The final code block downloads the cleaned list. See [Colab's guide](https://research.google.com/colaboratory/faq.html).

For local Jupyter use, install `requirements.txt` and skip the last, Colab-only download block. Files are saved in the notebook's working folder.

## Results

| Check | Result |
| --- | --- |
| Saved station entries | 84 |
| Missing descriptions | 31, labeled “No details provided” |
| Exact repeats removed | 0 |
| Search checks | 6 passed |

![Example station distances](images/triton_refill_example.png)

These are direct map distances from an example location. Walking paths, building access, and current station conditions require separate checks. Street View coverage also varies. The blank visit log contains no campus observations.

## Files

| File or folder | Purpose |
| --- | --- |
| `Triton_Refill.ipynb` | Original notebook with beginner explanations |
| `data/` | Cleaned list, checks, example results, and blank visit log |
| `images/` | Example distance chart |
| `docs/app-setup.md` | ArcGIS setup notes |
| `docs/github-upload-guide.md` | First GitHub upload steps |

## Data credit

Station locations come from [UCSD Hydration Locations](https://www.google.com/maps/d/viewer?mid=18OFCg3GFp6wl5mCwioSvU9fdGAA&usp=sharing), linked by [UCSD HDH Sustainability](https://hdhsustainability.ucsd.edu/). This project uses a saved map export; the source update date is unknown. Data belongs to its respective owners. The notebook includes further references.
