# Rat Complaints in High-Poverty Blocks

EDK is a research lab focused on understanding the physical world at planetary scale. We build systems that organize the world's physical information and make it accessible and usable. Our belief is simple: the physical world should be as searchable and understandable as the digital world. [edk.earth](https://edk.earth)

**Cincinnati takes 10 times longer than New York to close rat complaints**

Compare where rodent complaints arise in high-poverty blocks and how long cities take to close them.

> 30,000 rows, built with EDK-1. The full dataset, with every region and live updates, is on EDK: **[edk.earth/datasets/rat-complaints-high-poverty](https://edk.earth/datasets/rat-complaints-high-poverty)**

![Rats Don't Wait](visualization.png)

## Key findings

- Cincinnati's median closure time was 28 days, nearly 10 times New York's 3 days.
- Kansas City's median was 20 days, compared with 3 days in New York.
- Chicago's median was about 5 days, while New York's was about 3.

![Rats Have A Season](visualization-2.png)

## Get the full data on EDK

The complete dataset, kept up to date for every region, lives on EDK. Download it there or query it through the API.

### This dataset on EDK

The full version of this dataset, with every region and the latest records. Download CSV or Parquet directly once you are signed in.
[edk.earth/datasets/rat-complaints-high-poverty](https://edk.earth/datasets/rat-complaints-high-poverty)

### Signals

See where things are happening right now and how they are changing, place by place.
[edk.earth/signals](https://edk.earth/signals)

### The EDK API

Ask for any place in plain language and get back locations, conditions and context as GeoJSON.
[edk.earth/docs](https://edk.earth/docs)

### More datasets

Every dataset EDK has published, from civic records to climate risk.
[edk.earth/datasets](https://edk.earth/datasets)

## About this dataset

Each entry is a rodent complaint from a block where at least 30% of residents live below the poverty line, with its filing date, location and status. Together, they map where complaints occur and how closure times vary across places with different poverty and renter shares.

## Inside the data

- **One row** is one rat complaint.
- **Filtered to** high poverty or very high poverty.
- **Covers** 2007 to 2025.

## At a glance

|  |  |
|---|---|
| Rows | 30,000 |
| Columns | 13 |
| Coverage | 54 cities |
| Time span | 2007 to 2025 |
| Built with | EDK-1 and 12 public sources |
| Format | Parquet and CSV |
| License | CC BY-SA 4.0 (Attribution-ShareAlike) |

## Use it for

- **City officials**: Compare complaint closure times across neighborhoods and cities.
- **Housing researchers**: Examine how complaint patterns relate to poverty and renter shares.
- **Public health teams**: Map rodent complaints in high-poverty neighborhoods.
- **Data journalists**: Report on differences in complaint response times across places.

## Questions to explore

1. Where do rodent complaints take longest to close?
2. How do closure times vary with neighborhood poverty and renter shares?
3. How have complaint locations and closure times changed over time?

## Columns

Every column, in plain words.

| Column | What it means |
|---|---|
| `id` | Entry number in this extract; unitless. |
| `reported_at` | Date and time the complaint was recorded. |
| `days_to_close` | Elapsed time from filing to city closure, in days. |
| `closed_at` | Date and time the request was closed. |
| `status` | Status as published by the source. |
| `poverty_level` | Plain-language poverty level for the block group; US only. |
| `poverty_rate_pct` | Share of residents below the poverty line, in percent; US only. |
| `renters_pct` | Share of homes that are renter-occupied, in percent; US only. |
| `city` | City or EDK-matched region name. |
| `latitude` | North-south position in decimal degrees, WGS84. |
| `longitude` | East-west position in decimal degrees, WGS84. |
| `source` | Name of the public dataset containing the complaint. |
| `month` | Calendar month of filing, from 1 to 12. |

## Sources

| Source | Provider | Contributes | License |
|---|---|---|---|
| **EDK-1** | EDK | EDK's spatial model: matches every record to its place and joins the context around it | — |
| 311 Service Requests 2010 to 2019 | New York City | Rodent complaint records | See source |
| [NYC 311 Service Requests from 2020 to Present](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2020-to-Present/erm2-nwe9) | New York | Rodent complaint records | See source |
| 311 Service Requests | Chicago, IL | Rodent complaint records | See source |
| [311 Cases](https://data.sfgov.org/City-Infrastructure/311-Cases/vw6y-z8j6) | San Francisco, CA | Rodent complaint records | See source |
| [Customer Service Requests](https://data.seattle.gov/City-Administration/Customer-Service-Requests/5ngg-rpne) | Seattle, WA | Rodent complaint records | See source |
| [New Orleans 311](https://data.nola.gov/d/2jgv-pqrq) | New Orleans | Rodent complaint records | See source |
| [Cincinnati 311](https://data.cincinnati-oh.gov/d/gcej-gmiw) | Cincinnati | Rodent complaint records | See source |
| [Pittsburgh 311](https://data.wprdc.org/dataset/pittsburgh-311-data) | Pittsburgh | Rodent complaint records | See source |
| [311 Service Requests May 2024 - Present](https://data.buffalony.gov/Quality-of-Life/311-Service-Requests-May-2024-Present-/3tj7-3tdz) | Buffalo, NY | Rodent complaint records | See source |
| [Kansas City 311](https://data.kcmo.org/d/d4px-6rwg) | Kansas City | Rodent complaint records | See source |
| [311 Service Requests July 2008 - May 2024](https://data.buffalony.gov/Quality-of-Life/311-Service-Requests-July-2008-May-2024-/whkc-e5vr) | Buffalo, NY | Rodent complaint records | See source |
| [Austin 311 Public Data](https://data.austintexas.gov/Utilities-and-City-Services/Austin-311-Public-Data/xwdj-i9he) | Austin, TX | Rodent complaint records | See source |
| [Commonwealth Connect Service Requests](https://data.cambridgema.gov/Public-Works/Commonwealth-Connect-Service-Requests/2z9k-mv9g) | Cambridge, MA | 17 rows in this sample | See source |
| [Get It Done Closed 2026 Cases](https://data.sandiego.gov/datasets/get-it-done-reports/) | San Diego, CA | 9 rows in this sample | See source |
| [Charlotte 311](https://data.charlottenc.gov/datasets/charlotte::service-requests-311) | Charlotte | 1 rows in this sample | See source |

Released under **CC BY-SA 4.0 (Attribution-ShareAlike)**. You may share and adapt it, including commercially, as long as you credit "EDK (edk.earth)" and the sources above, and share anything you build from it under the same license.

## Quick start

```python
import pandas as pd

df = pd.read_csv("/kaggle/input/rat-complaints-high-poverty/rat-complaints-high-poverty.csv")

# median days to close by city
df.groupby("city")["days_to_close"].median().sort_values(ascending=False).head(10)

# as a GeoDataFrame
import geopandas as gpd
gdf = gpd.GeoDataFrame(df, geometry=gpd.points_from_xy(df.longitude, df.latitude), crs="EPSG:4326")
```

## Get an API key

1. Sign up at [edk.earth/sign-up](https://edk.earth/sign-up).
2. Create a secret key in [Console → API Keys](https://edk.earth/console/keys).
3. Set it in your shell as `EDK_API_KEY`.

## Call the API

Ask for data like this, for any place, in plain language. Results come back as GeoJSON with coordinates and context.

```bash
curl -X POST https://api.edk.earth/v1/discover \
  -H "Authorization: Bearer $EDK_API_KEY" \
  -H "content-type: application/json" \
  -d '{"query": "rat complaints in Cincinnati", "limit": 100}'
```

```python
import os, requests
import pandas as pd

res = requests.post("https://api.edk.earth/v1/discover",
    headers={"Authorization": f"Bearer {os.environ['EDK_API_KEY']}"},
    json={"query": "rat complaints in Cincinnati", "limit": 100})
df = pd.json_normalize(res.json()["data"]["geojson"]["features"])
```

```ts
import { EDK } from "@edks/sdk"; // npm install @edks/sdk

const edk = new EDK(); // reads EDK_API_KEY
const { data } = await edk.discover("rat complaints in Cincinnati", { limit: 100 });
```

Full reference: [edk.earth/docs](https://edk.earth/docs).

## Use EDK in Claude Code

Connect once, then ask Claude Code for any place, permit, hazard or street in plain language. Guide: [edk.earth/claude-code](https://edk.earth/claude-code).

```bash
claude mcp add edk --env EDK_API_KEY=edk_sk_... -- npx -y @edks/mcp
```

## Use EDK in Codex

Add EDK to `~/.codex/config.toml`, then ask Codex the same way. Guide: [edk.earth/codex](https://edk.earth/codex).

```toml
[mcp_servers.edk]
command = "npx"
args = ["-y", "@edks/mcp"]
env = { EDK_API_KEY = "edk_sk_..." }
```

Other agents: [edk.earth/agents](https://edk.earth/agents).

## Good to know

- Some complaints have no recorded closure time.
- Complaint categories and closure practices may differ by city, limiting direct comparisons.

[edk.earth](https://edk.earth) · [Datasets](https://edk.earth/datasets) · [Signals](https://edk.earth/signals) · [Docs](https://edk.earth/docs) · [Claude Code](https://edk.earth/claude-code) · [Codex](https://edk.earth/codex)

## Citation

```bibtex
@misc{edk_rat_complaints_high_poverty,
  title  = {Rats Have A Season},
  author = {EDK},
  year   = {2026},
  url    = {https://edk.earth/datasets/rat-complaints-high-poverty}
}
```
