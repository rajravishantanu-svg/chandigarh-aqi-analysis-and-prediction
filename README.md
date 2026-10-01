# chandigarh-aqi-analysis
Machine learning-based air quality analysis and AQI prediction using CPCB monitoring data from Chandigarh.
Exploratory analysis of hourly air-quality data for Sector 25, Chandigarh, collected from the CPCB website. The dataset covers 7 Aug 2019 to 1 Jan 2026 and includes seven pollutants (PM2.5, PM10, NO2, NH3, SO2, CO, Ozone), four weather variables (RH, WS, WD, AT) and AQI with its sub-indices.
Data
Sector 25 Collected data.xlsx: raw data (56,122 rows)
Sector_25_cleaned final.xlsx: cleaned data (47,441 rows)
Cleaning: AQI was converted to numeric, rows with any missing value were dropped, and the data was sorted by timestamp. No outliers were removed and no values were altered.
Analysis: done in Google Colab to find pollution trends, seasonal patterns and the main drivers of AQI.
