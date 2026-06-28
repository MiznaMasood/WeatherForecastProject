# 🌤️ AI Weather Forecasting Project

## Dataset
**Historical Hourly Weather Data 2012-2017**
https://www.kaggle.com/datasets/selfishgene/historical-hourly-weather-data

Download and place these 7 CSV files inside a `data/` folder:
```
data/
  temperature.csv
  humidity.csv
  pressure.csv
  wind_speed.csv
  wind_direction.csv
  weather_description.csv
  city_attributes.csv
```

## Setup

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Train all models (takes ~10-20 min depending on your machine)
python main.py

# 3. Launch the Streamlit dashboard
streamlit run app.py
```

## Project Structure
```
weather_forecasting/
├── data/               ← put the 7 CSV files here
├── artefacts/          ← auto-created: saved models & scalers
├── plots/              ← auto-created: all visualisation PNGs
├── main.py             ← full training pipeline
├── app.py              ← Streamlit web dashboard
├── requirements.txt
└── README.md
```

## Models Trained
| Model | Type |
|---|---|
| Linear Regression | Baseline |
| Random Forest | Ensemble |
| XGBoost | Gradient Boosting |
| ANN | Neural Network |
| LSTM | Recurrent (sequence) |
| GRU | Recurrent (sequence) |

## Metrics Used
- MAE – Mean Absolute Error
- MSE – Mean Squared Error
- RMSE – Root Mean Squared Error
- R² – Coefficient of Determination
- MAPE – Mean Absolute Percentage Error

## Changing the City
In `main.py`, line:
```python
CITY = "Denver"
```
Change to any city in the dataset, e.g.:
`"New York"`, `"Los Angeles"`, `"Chicago"`, `"Houston"`,
`"Philadelphia"`, `"Phoenix"`, `"San Antonio"`, `"San Diego"`,
`"Dallas"`, `"San Jose"`, `"Jacksonville"`, `"Indianapolis"`,
`"San Francisco"`, `"Austin"`, `"Columbus"`, `"Fort Worth"`,
`"Charlotte"`, `"Memphis"`, `"Portland"`, `"Oklahoma City"`,
`"Las Vegas"`, `"Louisville"`, `"Baltimore"`, `"Milwaukee"`,
`"Albuquerque"`, `"Tucson"`, `"Fresno"`, `"Sacramento"`,
`"Kansas City"`, `"Atlanta"`, `"Miami"`, `"Minneapolis"`,
`"Omaha"`, `"Cleveland"`, `"Raleigh"`, `"Colorado Springs"`,
`"Virginia Beach"`, `"Long Beach"`, `"Minneapolis"`

## Dashboard Pages
1. **Overview** – Project summary and pipeline
2. **EDA & Data** – Time-series plots, correlation heatmap
3. **Model Results** – Actual vs Predicted with interactive slider
4. **Live Prediction** – Enter weather params → get temperature prediction
5. **Residual Analysis** – Error distribution per model
6. **Model Comparison** – Side-by-side metrics table + bar chart
