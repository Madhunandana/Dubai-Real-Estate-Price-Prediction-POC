# Dubai Real Estate Price Prediction POC

This Proof of Concept (POC) project aims to build a machine learning model to predict real estate prices in Dubai. By leveraging historical transaction records, the project explores data patterns, extracts key features, and implements a robust prediction engine using Random Forest Regression.

## 🚀 Project Overview

The objective of this project is to provide accurate property valuation estimates based on historical data. It covers the entire data science lifecycle, from cleaning and exploratory analysis to advanced feature engineering and model deployment via an automated pipeline.

## 📊 Dataset In brief

The model is trained on a dataset containing over **90,000 transaction records** from the Dubai real estate market.

-   **Key Features**: Property type, area name, procedure area, room configuration (`rooms_en`), parking status, and proximity to key infrastructure.
-   **Target Variable**: `meter_sale_price` (Price per square meter).

## 🛠️ Methodology

### 1. Data Preprocessing
-   **Cleaning**: Removal of redundant identifier columns and Arabic-language columns to focus on English analytical features.
-   **Handling Missing Values**: Systematic imputation—categorical missing values were labeled as "Unknown," while numerical gaps were handled using median imputation within the pipeline.
-   **Outlier Removal**: Leveraged the Interquartile Range (IQR) method to filter out extreme price points and reduce model noise.
-   **Temporal Analysis**: Converted transaction dates into `year`, `month`, and `day` features to capture market trends over time.

### 2. Feature Engineering
-   **Proximity Indicators**: Created binary flags (`near_metro`, `near_mall`, `near_landmark`) to quantify the impact of location amenities.
-   **Room Metrics**: Developed `area_per_room` to analyze property density and layout efficiency.

### 3. Machine Learning Pipeline
-   **Model**: Random Forest Regressor.
-   **Pipeline Architecture**: Implemented a `ColumnTransformer` for automated scaling of numerical data and one-hot encoding for categorical variables, ensuring reproducibility and preventing data leakage.
-   **Evaluation**: Models with 100 and 200 trees were compared to optimize the stability-to-performance ratio.

## 📈 Performance Results

The final model (Random Forest with 200 trees) achieved high accuracy on the test set:

| Metric | Value |
| :--- | :--- |
| **Mean Absolute Error (MAE)** | ~115.4 |
| **Root Mean Squared Error (RMSE)** | ~437.4 |
| **R² Score** | **0.9961** |

> [!NOTE]
> The R² score of 0.996 implies that the model explains over 99% of the variance in the price per square meter within this specific dataset.

## 🧠 Key Insights

-   **Location is King**: Area Name and specific Project Names are among the top predictors of price.
-   **Proximity**: Accessibility to Metro stations and landmarks significantly boosts property value.
-   **Density**: The `area_per_room` metric proved to be a significant feature in differentiating between luxury and luxury-budget property segments.

## 💻 Tech Stack

-   **Language**: Python
-   **Libraries**:
    -   Data Handling: `pandas`, `numpy`
    -   Visualization: `matplotlib`, `seaborn`
    -   Machine Learning: `scikit-learn`

## 📂 Project Structure

-   `Real Estate Price Prediction POC (1).ipynb`: The primary research and development environment.
-   `sample_data.csv`: (Dataset) Historical transaction records.
-   `README.md`: Project documentation.

---

