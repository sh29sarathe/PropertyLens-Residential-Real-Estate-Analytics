\# PropertyLens – Residential Real Estate Market \& Pricing Analytics



\## Project Overview



PropertyLens is a Python-based data analytics project focused on analysing residential real estate listings in Gurugram.



The project started as a basic real estate analysis and was expanded into a broader market and pricing analysis covering data quality, property pricing, locality differences, property configurations, RERA status, construction status, statistical relationships and relative pricing.



The main objective is to understand how property prices and rates vary across different characteristics of the listings and to identify useful market-level patterns from the available data.



\## Dataset



The dataset contains residential real estate listings with information including:



\- Price

\- Status

\- Area

\- Rate per sqft

\- Property Type

\- Locality

\- Builder Name

\- RERA Approval

\- BHK Count

\- Society

\- Company Name

\- Flat Type



The original dataset contains 19,515 records.



After cleaning and removing exact duplicate records, 14,225 listings were retained for analysis.



\## Tools Used



\- Python

\- Pandas

\- NumPy

\- Matplotlib

\- Seaborn

\- SciPy

\- Statsmodels

\- Jupyter Notebook



\## Analysis Performed



\### 1. Data Inspection and Cleaning



\- Checked dataset structure and data types

\- Identified missing values and duplicate records

\- Standardized column names

\- Cleaned text fields

\- Converted price and rate fields into numeric values

\- Checked suspicious numeric values

\- Investigated unusual BHK, area, price and rate values



Extreme values were investigated rather than automatically removed when they appeared to represent legitimate properties or plots.



\### 2. Feature Engineering



Created analytical fields including:



\- Price in lakh

\- Price in crore

\- Area in sqft

\- BHK groups

\- Price bands

\- Area bands



\### 3. Market Overview



Analysed:



\- Overall property prices

\- Property area

\- Rate per sqft

\- Property type distribution

\- Status distribution

\- RERA approval distribution

\- BHK distribution

\- Locality listing volume



\### 4. Locality Analysis



Compared localities using:



\- Listing volume

\- Median price

\- Median rate per sqft

\- Average area

\- Price and rate differences

\- RERA share

\- Ready-to-move share



Localities with very small numbers of listings were treated carefully when making comparisons.



\### 5. Property Configuration Analysis



Analysed differences across:



\- BHK configuration

\- Property type

\- Area bands

\- Price

\- Rate per sqft



\### 6. Company / Listing Source Analysis



The `Builder Name` field was analysed as a company/listing-source field because the dataset contains developers as well as brokers, portals and generic listing-source names.



The analysis includes listing volume, pricing and other available characteristics associated with these names.



\### 7. RERA Analysis



Compared RERA-approved and non-approved listings using:



\- Price

\- Rate per sqft

\- Area

\- Listing volume



The analysis does not interpret the observed difference as a causal RERA price premium because the two groups have different property and status compositions.



\### 8. Ready-to-Move vs Under Construction



Compared the two groups using:



\- Listing volume

\- Median price

\- Median rate per sqft

\- Median area



The differences are interpreted as observed differences within the dataset rather than as causal effects of construction status.



\### 9. Distribution Analysis



Examined the distributions of:



\- Price

\- Area

\- Rate per sqft



Percentiles and median values were used alongside averages because the dataset contains substantial high-value properties.



\### 10. Relationship Analysis



Used Pearson and Spearman correlation to examine relationships among:



\- Price

\- Area

\- Rate per sqft

\- BHK



Both methods were considered because the variables contain skewed distributions and non-linear relationships.



\### 11. Statistical Analysis



Used statistical tests to compare selected groups, including:



\- Ready-to-move vs Under Construction

\- RERA Approved vs Not Approved

\- BHK groups



The results were interpreted as evidence of differences between distributions and not as evidence of causation.



\### 12. Price Driver Analysis



Used an interpretable OLS regression with log-transformed price to examine associations between property price and variables such as:



\- Area

\- BHK

\- Property type

\- Status

\- RERA approval



Rate per sqft was excluded from this model because it is mathematically related to price and area.



\### 13. Market Segmentation



Created project-specific price segments:



\- Budget

\- Mid-Market

\- Premium

\- High-End

\- Luxury



These segments are analytical categories created for this project and are not official market classifications.



\### 14. Locality-Based Relative Pricing



Compared individual listings against the median rate per sqft for comparable listings within the same locality and property type.



Listings with sufficient comparable observations were classified as:



\- Lower-Priced

\- Market-Aligned

\- Premium-Priced



A total of 12,635 listings, or 88.82% of the cleaned dataset, had a valid locality and property-type benchmark.



\## Key Findings



\- The final analysis contains 14,225 listings.

\- The median property price is ₹2.62 crore.

\- The median property area is 2,015 sqft.

\- The median rate is ₹12,379 per sqft.

\- 78.98% of listings are priced between ₹1 crore and ₹10 crore.

\- The ₹2–5 crore price band contains the largest share of listings at 39.21%.

\- Apartments are the dominant property type.

\- 3 BHK is the most common specified BHK configuration.

\- Sector 65 has the highest listing volume.

\- Sector 42 has the highest median price and median rate among localities with at least 20 listings.

\- 88.82% of listings could be compared with a locality and property-type pricing benchmark.

\- Among benchmarked listings, 37.43% were Market-Aligned, 33.10% Lower-Priced and 29.47% Premium-Priced relative to their comparable benchmark.



\## Project Structure



```text

PropertyLens-Residential-Real-Estate-Analytics/

│

├── data/

│   ├── data of gurugram real Estate.csv

│   ├── propertylens\_cleaned.csv

│   └── propertylens\_featured.csv

│

├── notebooks/

│   ├── 01\_propertylens\_real\_estate\_market\_analysis.ipynb

│   ├── 02\_Data Cleaning \& Standardization.ipynb

│   ├── 03\_Feature Engineering.ipynb

│   ├── 04\_Data Quality \& Outlier Investigation.ipynb

│   ├── 05\_Basic Market Overview.ipynb

│   ├── 06\_Locality-Level Market Analysis.ipynb

│   ├── 07\_Property Configuration Analysis.ipynb

│   ├── 08\_Builder-Company Analysis.ipynb

│   ├── 09\_RERA Approval Analysis.ipynb

│   ├── 10\_Ready-to-Move vs Under-Construction.ipynb

│   ├── 11\_Price Distribution \& Outlier Analysis.ipynb

│   ├── 12\_Relationship Analysis.ipynb

│   ├── 13\_Statistical Analysis.ipynb

│   ├── 14\_Price Driver Analysis.ipynb

│   ├── 15\_Market Segmentation.ipynb

│   ├── 16\_Locality-Based Value-for-Money Analysis.ipynb

│   └── 17\_Final Market Insights.ipynb

│

└── README.md

