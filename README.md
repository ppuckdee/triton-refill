# Triton Refill

Find a nearby water station at UC San Diego.

**[Launch Triton Refill](https://experience.arcgis.com/experience/e5cdd600df2146a3a2d6cdd035e79d67)** · [Explore the Python Notebook](Triton_Refill.ipynb)

## What you can do

- Find water stations near you or a place you select.
- Read station details and get directions.
- Look around nearby areas using Street View.
- Send a station report and add a photo.

Reports appear in a private dashboard for the project owner to review.

## How it works

| Tool | What it does |
| --- | --- |
| Python | Tidies the station list and tests a nearby search. |
| ArcGIS Online | Stores the station information and map. |
| Experience Builder | Creates the app people use. |
| Survey123 | Collects station reports and photos. |
| ArcGIS Dashboards | Shows the submitted reports. |
| Google Maps | Provides Street View. |

The app runs in ArcGIS. This GitHub page holds the project’s code, files, and instructions.

## Try the code

The notebook contains code with explanations of each step.

1. Download `Triton_Refill.ipynb`.
2. Open [Google Colab](https://colab.research.google.com/) and upload the notebook.
3. Run each code block in order, starting at the top.

The station list is already included. You do not need an ArcGIS account or Google Maps key to run the notebook. The last block downloads the cleaned station list.

**Using Jupyter instead?** Install the tools listed in `requirements.txt` and skip the last download block.

## What the notebook found

| Item | Result |
| --- | --- |
| Entries in the station list | 84 |
| Missing descriptions | 31 |
| Repeated entries removed | 0 |
| Search checks passed | 6 |

Missing descriptions were filled with **“No details provided.”**

![Distances to nearby stations](images/triton_refill_example.png)

Shorter bars mean closer stations.

## Things to know

- Distances are measured directly between map points. Walking routes may be longer.
- Current station conditions and building access have not been confirmed.
- Street View is available only where Google has images.
- The search checks test the code. The visit log is still blank.

## Where to find things

| File or folder | What is inside |
| --- | --- |
| `Triton_Refill.ipynb` | The code and explanations |
| `data/` | Station list, check results, and blank visit log |
| `images/` | The example chart |
| `docs/app-setup.md` | Notes about building the app |
| `docs/github-upload-guide.md` | Steps for uploading this project to GitHub |

## Where the station list came from

The locations came from [UCSD Hydration Locations](https://www.google.com/maps/d/viewer?mid=18OFCg3GFp6wl5mCwioSvU9fdGAA&usp=sharing), linked by [UCSD HDH Sustainability](https://hdhsustainability.ucsd.edu/).

This project uses a saved copy. The original map’s last update date is unknown. Credit for the source data belongs to its owners. More sources are listed in the notebook.
