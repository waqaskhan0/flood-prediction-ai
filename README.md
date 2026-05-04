# AI-Based Flood Prediction and Early Warning Dashboard

An end-to-end machine learning and geospatial visualization project for classifying flood risk levels across Pakistan. The project uses historical flood disaster records to predict risk categories and display them through an interactive dashboard and map.

## Overview

Floods are one of the most damaging natural disasters in Pakistan, affecting lives, homes, agriculture, and infrastructure. This project explores how machine learning can support flood risk monitoring by combining disaster impact data with geospatial coordinates.

The system classifies flood records into three risk levels:

- Low
- Medium
- High

It also provides an interactive dashboard for exploring flood risk by location, year, and risk category.

## Key Features

- Machine learning-based flood risk classification
- Damage-based feature engineering from flood impact records
- Interactive Pakistan flood risk dashboard
- Geospatial visualization using latitude and longitude
- Risk-level filtering for Low, Medium, and High flood events
- Year-based filtering and trend visualization
- Flood risk distribution charts
- JSON export for browser-based dashboard rendering

## Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Folium
- Plotly
- HTML
- CSS
- JavaScript

## Dataset

The dataset contains Pakistan flood disaster records from 2010, 2011, 2022, and 2025 across multiple provinces and districts.

Main fields include:

- Year
- Province and district
- Flood event name
- Deaths
- Houses destroyed
- Houses damaged
- People affected
- Cropland affected
- Flood severity
- Flood type
- Latitude and longitude

Current dataset summary:

- 30 flood records
- 5 provinces
- 21 districts
- 3 flood risk classes

## Machine Learning Workflow

1. Loaded and cleaned flood disaster data.
2. Processed numeric and categorical columns.
3. Engineered a `damage` feature using destroyed and damaged houses.
4. Created balanced flood risk labels using damage distribution.
5. Selected model features such as location, year, affected population, and cropland damage.
6. Trained and compared multiple classification models.
7. Exported predicted flood risk data to `flood_data.json`.
8. Visualized the results in an interactive dashboard and geospatial map.

## Models Tested

- Logistic Regression
- Random Forest Classifier
- Gradient Boosting Classifier

Best-performing model:

**Random Forest Classifier**

- Test accuracy: 83.33%
- Mean cross-validation accuracy: 70%

Note: This is a prototype built on a small dataset, so the performance metrics should be interpreted as experimental rather than production-ready.

## Project Structure

```text
.
+-- Dataset/
|   +-- test1.csv
+-- dashboard.html
+-- flood_data.json
+-- flood_risk_map.html
+-- model.ipynb
+-- README.md
+-- requirement.txt
```

## How to Run

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <your-project-folder>
```

### 2. Install Dependencies

```bash
pip install -r requirement.txt
```

### 3. Run the Notebook

Open `model.ipynb` in Jupyter Notebook or VS Code and run the cells to:

- Load the dataset
- Train and evaluate the models
- Generate flood risk labels
- Export dashboard data
- Create the Folium map

### 4. Open the Dashboard

Because `dashboard.html` loads `flood_data.json`, run a local server from the project folder:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/dashboard.html
```

You can also open `flood_risk_map.html` directly in a browser to view the generated Folium map.

## Dashboard Preview

The dashboard includes:

- Total flood record count
- Low, Medium, and High risk totals
- Interactive geospatial flood risk map
- Flood risk distribution chart
- Flood records over time chart
- Filters by risk level and year

## Use Cases

- Disaster risk monitoring
- Flood impact analysis
- Geospatial data visualization
- Machine learning portfolio project
- Early warning system prototype

## Limitations

- The dataset is small and should be expanded for real-world use.
- The model does not currently use live rainfall, river flow, satellite, or weather forecast data.
- The dashboard is a static frontend prototype.
- Accuracy may change significantly with a larger and more diverse dataset.

## Future Improvements

- Add real-time rainfall and weather API integration
- Include river water level and satellite imagery data
- Build a Streamlit or Flask web application
- Add model persistence with Joblib
- Improve validation using a larger dataset
- Add district-level search and alerts
- Deploy the dashboard online

## Author

Developed as a machine learning and data visualization project for flood risk prediction and early warning analysis.
