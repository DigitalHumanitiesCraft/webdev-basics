# Natural Sciences Coding Examples

## **Dataset 1: Global Temperature Data (NOAA)**
**Source:** [NOAA Climate Data](https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/global/time-series) / [Sample on GitHub](https://github.com/datasets/global-temp)

### 🌡️ **Scenario 1: Climate Data Dashboard "Warming Stripes"**
```
Create a dashboard for global temperature data.
Use this CSV with year, temperature anomaly, moving average.
Show: Time series with trend, comparison of different periods
Features: Slider for time range, heatmap of decades
Bonus: "Warming Stripes" visualization (blue/red bars)
```

**Sample CSV (simplified):**
```csv
Year,Temperature_Anomaly_C,Smoothed_Anomaly,Hemisphere
1880,-0.16,-0.08,Global
1881,-0.08,-0.11,Global
1882,-0.10,-0.15,Global
2020,1.02,0.98,Global
2021,0.85,0.97,Global
2022,0.89,0.96,Global
2023,1.17,1.01,Global
```

---

## **Dataset 2: GBIF Species Occurrences**
**Source:** [Sample Butterfly Data](https://zenodo.org/records/7749600)

### 🦋 **Scenario 2: Biodiversity Explorer "Where Lives What?"**
```
Build a dashboard for butterfly population trends in UK gardens.
Data: Species, Year, Abundance Index, Trends
Features: Time series visualization, species comparison
Show: Which species are increasing/declining? Seasonal patterns?
Interactive: Select species, zoom into time periods, compare multiple species
```

---

## **Dataset 3: Scientific Publications Metadata**
**Source:** [PubMed Sample](https://www.kaggle.com/datasets/bonhart/pubmed-abstracts)

### 📄 **Scenario 3: Research Trend Analyzer "What's Hot Right Now?"**
```
Create a tool for publication analysis.
Data: Title, Authors, Year, Journal, Keywords, Citations, Abstract
Features: Search by keywords, time trends (papers per year)
Visualizations: Keyword cloud, top journals, citation distribution
Bonus: Co-authorship network
```

**Sample CSV:**
```csv
Paper_ID,Title,Authors,Year,Journal,Keywords,Citations,Open_Access
P001,CRISPR-Cas9 genome editing in plants,"Smith J, Lee K",2023,Nature Plants,"CRISPR;plants;genome",145,Yes
P002,Machine learning for protein structure,"Mueller M, Chen L, Patel R",2023,Science,"AI;proteins;structure",203,No
P003,Microplastic pollution in oceans,"Garcia A, Schmidt H",2022,Nat Geosci,"ocean;pollution;plastic",167,Yes
P004,Quantum computing algorithms,"Zhang W, Brown T",2023,Nature,"quantum;algorithms;computing",98,No
```

---

## **Dataset 4: Earthquake Data (USGS)**
**Source:** [USGS Earthquake Catalog](https://earthquake.usgs.gov/earthquakes/feed/v1.0/csv.php)

### 🌍 **Scenario 4: Seismic Activity Monitor "Shake Map"**
```
Build a dashboard for earthquake data from the last 30 days.
Data: Magnitude, Depth, Coordinates, Time, Location, Tsunami Alert
Show: World map with pins (size = magnitude), filter by strength
Statistics: Most frequent regions, depth vs. magnitude
Timeline: Activity over time
```

**Sample CSV:**
```csv
Time,Latitude,Longitude,Depth_km,Magnitude,Location,Tsunami_Alert
2024-01-15T08:23:45Z,35.6762,139.6503,10,4.2,Near Tokyo Japan,No
2024-01-15T12:45:21Z,-20.5789,-178.1234,580,5.8,Fiji Region,No
2024-01-16T03:12:09Z,37.7749,-122.4194,8,3.1,San Francisco Bay,No
2024-01-16T18:56:33Z,-15.7833,-173.9833,25,6.3,Tonga,Yes
```

---

## **Scenario 5: WITHOUT Input Data - Chemical Compound Lookup**
### 🧪 **"ChemFinder" - Molecule Info via API**
```
Build a tool where I enter a compound name or SMILES string
and automatically get information.
Use the free PubChem API.
Input: Compound name (e.g., "Caffeine", "Aspirin") or SMILES
Output: Molecular formula, molecular weight, structure image, properties
Make it clean with tabs or cards.
```

**No CSV needed** - uses PubChem REST API:
- `https://pubchem.ncbi.nlm.nih.gov/rest/pug/compound/name/{compound}/JSON`
- `https://pubchem.ncbi.nlm.nih.gov/rest/pug/compound/name/{compound}/PNG` (structure image)

**Test compounds for practice:**
- `Caffeine`
- `Aspirin` (Acetylsalicylic acid)
- `Glucose`
- `Ethanol`

**Alternative:** OpenFDA API for drugs or Protein Data Bank (PDB) API for protein structures

---

## **Bonus Ideas Without Prepared Data:**

### 🔬 **More API-based Projects:**
1. **Weather Dashboard**: OpenWeatherMap API - current weather data for research locations
2. **Protein Viewer**: UniProt API - retrieve protein sequences and annotations
3. **Astronomy Tonight**: NASA API - space images and data
4. **CrossRef Lookup**: DOI → paper metadata (perfect for literature reviews)

---
