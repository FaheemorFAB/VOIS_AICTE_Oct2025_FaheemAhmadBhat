### Airbnb Price Prediction (Project_VOIS)

This project builds a comprehensive machine learning system to analyze Airbnb listing data and predict demand patterns. Using historical Airbnb data, we explore relationships between pricing, location, host attributes, booking options, and guest behavior proxies. The analysis includes exploratory data analysis, correlation studies, seasonality analysis, and predictive modeling to provide actionable insights for hosts and platform analysts.

### Objectives
- Analyze relationships between price, demand proxies (`reviews per month`), ratings (`review rate number`), availability, and booking options.
- Explore seasonality patterns using review activity as a proxy for demand.
- Build predictive models to estimate demand from listing features.
- Segment listings using clustering to identify distinct market segments.
- Provide data-driven recommendations for pricing and listing configuration.

### Who benefits
- **Airbnb Hosts**: Optimize pricing and listing configuration based on data-driven insights.
- **Travelers**: Understand pricing patterns and guest preferences across neighborhoods and room types.
- **Platform Analysts**: Enhance automated pricing guidance and understand market dynamics.
- **Researchers/Students**: Study how features, reviews, and booking options influence rental demand and satisfaction.

### Repository contents
- `Faheem_Ahmad_Bhat_Source_Code.ipynb`: Main analysis and modeling notebook with comprehensive EDA and ML models.
- `Airbnb.csv`: Primary dataset containing 102,599 Airbnb listings (83,411 after cleaning).
- `requirements.txt`: Pinned Python dependencies with specific versions.

### Tech stack
- **Python 3.x** with **Jupyter Notebook**
- **Data Processing**: NumPy, Pandas
- **Visualization**: Matplotlib, Seaborn, Plotly
- **Machine Learning**: Scikit-learn (Linear Regression, KMeans Clustering)

### Setup
1. Create and activate a virtual environment (recommended).
   ```bash
   # Windows PowerShell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```
2. Install dependencies.
   ```bash
   pip install -r requirements.txt
   ```
3. Install Jupyter Notebook (if not already installed).
   ```bash
   pip install jupyter
   ```

### Usage
1. Launch Jupyter and open the notebook.
   ```bash
   jupyter notebook
   ```
2. Open `Faheem_Ahmad_Bhat_Source_Code.ipynb` and run cells sequentially from top to bottom.
3. Ensure `Airbnb.csv` is present in the project root directory.

### Key analyses (in the notebook)

#### Data Cleaning and Preprocessing
- Removal of duplicate records and columns with insufficient data (`house_rules`, `license`)
- Conversion of price and service fee from string format (with $ and commas) to numeric
- Handling missing values and data type corrections
- Outlier removal for `availability 365` (removed values > 500)
- Correction of data inconsistencies (e.g., 'brookln' → 'Brooklyn')

#### Exploratory Data Analysis
- **Room Type Distribution**: Analysis of property types and their counts
- **Neighborhood Analysis**: Distribution of listings across neighborhood groups
- **Pricing Analysis**: Average prices by neighborhood group and construction year
- **Host Analysis**: Top hosts by listing count, verification status impact on ratings
- **Fee Analysis**: Correlation between price and service fees
- **Review Analysis**: Average review rates by neighborhood group and room type
- **Availability Analysis**: Relationship between host listing count and availability

#### Advanced Analyses
- **Seasonality Analysis**: Demand proxies using `reviews per month` by month of last review, stratified by neighborhood group
- **Pricing Impact Analysis**: Correlations and visualizations of price vs. demand and price vs. satisfaction, stratified by room type and neighborhood
- **Guest Preference Analysis**: Demand and ratings by room type, instant bookable status, and cancellation policy
- **Host Performance Analysis**: Performance metrics by verification status, listing count buckets, and booking options

#### Predictive Models
1. **Linear Regression Model**: Predicts `reviews per month` (demand proxy) from:
   - Price (`price_$`)
   - Neighborhood group
   - Room type
   - Instant bookable status
   - Cancellation policy
   - Availability 365
   - Uses StandardScaler for numeric features and OneHotEncoder for categorical features
   - Evaluated with R² and MAE metrics

2. **KMeans Clustering Model**: Segments listings into 4 clusters based on:
   - Price
   - Reviews per month
   - Review rate number
   - Availability 365
   - Creates distinct market segments for targeted strategies

### Data-driven recommendations (from analysis)
- **Pricing Strategy**: Price competitively within your `neighbourhood group` and `room type` bands; monitor how price changes affect `reviews per month` (demand proxy).
- **Booking Options**: Enable `instant_bookable` where feasible; it correlates with higher demand in the analysis.
- **Cancellation Policy**: Prefer more flexible `cancellation_policy` options to potentially improve `review rate number`.
- **Seasonality**: Use seasonality patterns (from last review month analysis) for dynamic pricing and minimum-stay adjustments during high-demand periods.
- **Host Management**: For hosts with multiple listings, standardize listing quality and responsiveness; verified identity associates with higher ratings.
- **Market Segmentation**: Apply cluster profiles to tailor pricing strategies and amenity investments per segment.

### Dataset Information
- **Original Size**: 102,599 listings with 26 columns
- **After Cleaning**: 83,411 listings with 24 columns
- **Key Features**: Location (neighborhood, coordinates), pricing (price, service fee), host attributes (verification, listing count), booking options (instant bookable, cancellation policy), demand proxies (reviews per month, number of reviews), ratings, and availability

### Reproducibility notes
- Dependencies are pinned with specific versions in `requirements.txt`.
- Random seeds are set where applicable (e.g., `random_state=42` for train-test split and KMeans).
- Results may vary slightly by platform and data filtering, but the overall patterns should be consistent.

### License
Add your preferred license here (e.g., MIT).
