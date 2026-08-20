# Crop_Recommendation_Analysis

1. Environment Setup & Data Loading
Libraries Used: Imported core Python libraries for data manipulation (pandas, numpy) and data visualization (matplotlib.pyplot, seaborn).
* Dataset Ingestion: Loaded Crop_recommendation.csv into a Pandas DataFrame.

2. Dataset Overview & Structural Inspection
Dataset Dimensions: verified that the dataset contains 2,200 rows and 8 columns.
* Feature Schema:
 Numerical Features: N (Nitrogen), P (Phosphorus), K (Potassium).
 Environmental Features: temperature, humidity, ph (soil pH), rainfall.
* Target Variable: label (Categorical variable representing crop types).
* Data Integrity Checks:
 Ran statistical summaries (df.describe()) to observe mean, standard deviation, quartiles, minimum, and maximum values across all numerical features.
 Checked for missing data using df.isnull().sum(), confirming 0 missing/null values across all attributes.

3. Outlier Analysis & Data CleaningOutlier Detection: Utilized seaborn.boxplot() to visually detect outliers in key features such as temperature, humidity, ph, and K.Outlier Handling:Defined a custom IQR-based function (remove_outliers) to calculate lower and upper range bounds ($Q1 - 1.5 \times IQR$ and $Q3 + 1.5 \times IQR$).Applied Capping/Winsorization using np.where() on the Phosphorus (P) column to clip extreme values exceeding boundary thresholds without discarding rows.

4. Exploratory Data Analysis & Visualizations
*  Distribution Analysis: Generated histograms (df.hist()) to observe the skewness and distribution spread of numerical variables.
* Feature Interactions: Humidity vs. Temperature: Plotted a scatter plot hue-mapped by crop label to understand how crops cluster based on climate conditions.
* Soil pH Distribution by Crop: Created a Violin Plot mapping ph across crop labels to analyze soil acidity/alkalinity tolerance ranges across different crops.
* Nitrogen Demands: Built a bar plot showing average Nitrogen (N) requirements for each crop label.

* Potassium Aggregation: Computed and ranked mean Potassium (K) values grouped by crop label, highlighting that crops like grapes (~200.11) and apples (~199.89) require significantly higher potassium content compared to citrus fruits like oranges (~10.01).
