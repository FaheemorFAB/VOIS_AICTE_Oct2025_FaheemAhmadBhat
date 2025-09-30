### Airbnb Price Prediction (Project_VOIS)

This project builds a machine learning system to predict Airbnb listing prices. Accurate pricing helps hosts maximize occupancy and revenue while ensuring travelers see fair, competitive rates. Using historical Airbnb data, we explore price drivers and train regression models to estimate prices for new or hypothetical listings.

### Objectives
- Predict listing price from features such as location, room type, host attributes, demand proxies, and ratings.
- Analyze relationships between price, demand (reviews per month), ratings, availability, and booking options.
- Provide data-driven recommendations for pricing and listing configuration.

### Who benefits
- **Airbnb Hosts**: Optimize pricing based on features and guest feedback.
- **Travelers**: Assess whether a listing is fairly priced relative to similar options.
- **Platform Analysts**: Enhance automated pricing guidance and transparency.
- **Researchers/Students**: Study how features and reviews influence rental pricing.

### Repository contents
- `Faheem_Ahmad_Bhat_Source_Code.ipynb`: Main analysis and modeling notebook.
- `DataSetProject.csv`: Primary dataset used in the notebook.
- `DataSetProject.xlsx`: Alternate dataset format (if needed).
- `requirements.txt`: Pinned Python dependencies.

### Tech stack
- Python 3.x, Jupyter Notebook
- NumPy, Pandas
- Matplotlib, Seaborn, Plotly
- Scikit-learn

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

### Usage
1. Launch Jupyter and open the notebook.
   ```bash
   jupyter notebook
   ```
2. Open `Faheem_Ahmad_Bhat_Source_Code.ipynb` and run cells top-to-bottom.
3. Ensure `DataSetProject.csv` is present in the project root (update paths in the notebook if needed).

### Key analyses and models (in the notebook)
- Data cleaning and feature typing for pricing and demand proxies.
- Exploratory analysis of room types, neighborhoods, pricing, host verification, and fees.
- Correlation and regression analyses: price vs. demand (`reviews per month`) and ratings.
- Predictive models:
  - Linear regression to estimate demand from price, location, room type, and booking options.
  - KMeans clustering to segment listings by price, demand, ratings, and availability.

### Data-driven recommendations (from analysis)
- Price competitively by `neighbourhood group` and `room type`; monitor impact on `reviews per month`.
- Enable `instant_bookable` where feasible to lift demand.
- Prefer more flexible `cancellation_policy` to support higher ratings.
- Use seasonality proxies (by last review month) for dynamic pricing and minimum-stay tuning.
- Standardize quality and responsiveness for multi-listing hosts; keep identity verified.
- Apply cluster profiles to tailor pricing and amenity investments per segment.

### Reproducibility notes
- Dependencies are pinned in `requirements.txt`.
- Random seeds are set where applicable, but results may vary slightly by platform and data filtering.

### License
Add your preferred license here (e.g., MIT).
