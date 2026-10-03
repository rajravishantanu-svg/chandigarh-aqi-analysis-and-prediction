# Air Quality (AQI) Analysis — Sector 25

Exploratory analysis of hourly air-quality readings from a Sector 25 monitoring dataset.

## Dataset

`Sector_25_cleaned github.xlsx`: 47,441 hourly records, 27 columns, 29 Aug 2019 to 1 Jan 2026. No missing values, no duplicate rows.

| Group | Columns |
|---|---|
| Time | Timestamp |
| Pollutants | PM2.5, PM10, NO2, NH3, SO2 (µg/m³), CO (mg/m³), Ozone (µg/m³) |
| Weather | RH (%), WS (m/s), WD (deg), AT (°C) |
| Sub-indices | Sub Index PM 2.5, PM 10, SO2, NO2, CO, O3, NH3 |
| Validity checks | Check PM2.5, PM10, NO2, NH3, SO2, CO, O3 (1 = valid) |
| Target | AQI |

## Notebook contents

1. Load and inspect: shape, `head`, `tail`, `describe`, duplicate and null checks.
2. AQI distribution (histogram with KDE).
3. AQI summary statistics by year.
4. Daily average AQI over time.
5. Monthly averages of AQI, PM2.5 and PM10.
6. Correlation heatmap of core pollutants and AQI.

## Results

- AQI: mean 110.9, median 97, range 13 to 1,081.
- Highest monthly mean AQI: January (175.1), December (152.6), November (143.4).
- Lowest monthly mean AQI: August (58.6), July (62.6), September (68.7).
- Yearly mean AQI rose from 77.7 (2020) to 143.5 (2024) and was 121.0 in 2025.

| Year | Records | Mean AQI | Max AQI |
|---|---|---|---|
| 2019* | 1,772 | 132.2 | 854 |
| 2020 | 8,071 | 77.7 | 784 |
| 2021 | 8,061 | 93.6 | 848 |
| 2022 | 7,504 | 101.7 | 556 |
| 2023 | 7,195 | 126.3 | 1,057 |
| 2024 | 7,881 | 143.5 | 1,081 |
| 2025 | 6,940 | 121.0 | 820 |
| 2026* | 17 | 275.2 | 309 |

\*Partial years. 2019 starts in late August; 2026 has 17 records from 1 Jan.

## Requirements

Python 3.8+, pandas, numpy, matplotlib, seaborn, openpyxl.

```bash
pip install pandas numpy matplotlib seaborn openpyxl
```

## Usage

1. Place `Sector_25_cleaned github.xlsx` where the notebook can read it.
2. Set the file path in the notebook (default `/content/Sector_25_cleaned github.xlsx`).
3. Run the cells in order.

## Notes

- The `Sub Index` columns are used to compute AQI. Exclude them as features if AQI is used as a model target.
- Hourly coverage varies by year (see record counts above).
