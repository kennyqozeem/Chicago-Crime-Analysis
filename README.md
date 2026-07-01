# Chicago Crime Data Analysis

Exploratory data analysis of reported crime incidents in Chicago, covering arrest outcomes, domestic crime patterns, time-based trends, and geographic distribution.

## 📊 Dataset

The dataset (`ChicagoCrimeData.csv`) contains **533 reported crime incidents** spanning **2001–2018**, with 21 fields including crime type, location, arrest status, domestic flag, district, beat, and geographic coordinates.

| Field | Description |
|---|---|
| `PRIMARY_TYPE` | Category of crime (e.g. Theft, Battery, Narcotics) |
| `ARREST` | Whether an arrest was made (True/False) |
| `DOMESTIC` | Whether the incident was domestic-related (True/False) |
| `DATE` | Date and time of incident |
| `DISTRICT` / `BEAT` | Police district and beat |
| `LOCATION_DESCRIPTION` | Type of location (street, residence, etc.) |
| `LATITUDE` / `LONGITUDE` | Geographic coordinates |

## 🛠️ Tools Used

- **pandas** — data loading, cleaning, aggregation
- **numpy** — numerical operations
- **matplotlib** — charting
- **seaborn** — statistical visualizations

## 📁 Notebook Structure

The analysis in `Chicago_Crime_Analysis.ipynb` is organized into the following sections:

1. **Summary Statistics Table** — high-level overview metrics
2. **Arrest & Domestic Crosstab** — count table of True/False values for arrest and domestic flags
3. **Crimes by Year** — yearly trend line
4. **Top 10 Crime Types** — most frequent offenses
5. **Arrest Rate Analysis** — overall and by crime type
6. **Domestic Crime Analysis** — domestic rate and cross-tabulation with arrests
7. **Time-Based Patterns** — crimes by hour of day and day of week
8. **Geographic Analysis** — top crime locations and a lat/long scatter plot of incidents
9. **District / Beat Analysis** — crime volume and arrest rate by police district

## 🚀 How to Run

```bash
pip install pandas numpy matplotlib seaborn
```

Update the file path in the notebook to point to your local copy of `ChicagoCrimeData.csv`, then run all cells sequentially.

```python
df = pd.read_csv('ChicagoCrimeData.csv')
```

> **Note:** The `DATE` column must be converted to a datetime type before running the time-based analysis:
> ```python
> df['DATE'] = pd.to_datetime(df['DATE'])
> ```

## 🔍 Key Insights

- 533 incidents recorded, spanning 2001–2018
- Theft, Battery, and Criminal Damage account for nearly half of all cases
- Only 30.6% of crimes resulted in an arrest
- 14.8% of cases are domestic-related
- Crime likely peaks during evening/night hours and weekends
- Crime is concentrated in specific districts and location types
- Comparing yearly crime counts vs. arrest rates helps distinguish real improvement from underreporting
- Small sample size (~30 records/year) — trends should be treated as illustrative, not statistically conclusive

## ⚠️ Limitations

This dataset is a relatively small sample (533 records over 18 years). It should not be treated as a complete or statistically representative record of crime in Chicago. Conclusions drawn here are exploratory and intended to demonstrate analysis technique rather than serve as a definitive crime report.

