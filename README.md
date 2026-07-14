# Mercedes-benz-Stock-Prediction
This project aimed to analyze and predict the closing stock prices of Mercedes (MBG.DE) using historical data. The key steps and findings are summarized below:
1. Data Loading and Initial Exploration

The historical stock data for MBG.DE was loaded from a CSV file into a pandas DataFrame.
Initial checks were performed to understand the data's shape, types, and basic statistics using df.info(), df.describe(), df.head(), and df.tail().
Missing values and duplicate rows were checked and confirmed to be absent.
2. Outlier Detection and Handling

Outliers were identified using the Z-score method for numerical columns (Open, High, Low, Close, Adj Close, Volume).
A new DataFrame (df_no_outliers) was created by removing these identified outlier rows, resulting in 1082 rows remaining from an initial 1105.
3. Exploratory Data Analysis (EDA)

Statistical Summaries: Min/Max values for 'Close' and 'Volume' were identified.
Box Plots: Visualizations for 'Close', 'Volume', 'High', 'Low', 'Open', and 'Adj Close' revealed their distributions and potential outliers.
Kernel Density Estimation (KDE) Plots: KDE plots for 'Volume' and 'Close' illustrated the density distribution of these key metrics.
Joint and Regression Plots: A joint plot and a regression plot between 'Volume' and 'Close' (using the outlier-removed data) were generated to understand their relationship.
Time Series Plots: The historical trends of 'Close' price and 'Volume' over time were visualized.
Moving Averages: 30-day and 100-day Moving Averages were calculated and plotted against the 'Close' price to identify trends.
Histograms: Histograms for 'Open', 'Close', and 'Adj Close' provided insights into their frequency distributions.
Correlation Analysis: A heatmap of the correlation matrix for numerical features showed strong positive correlations among 'Open', 'High', 'Low', 'Close', and 'Adj Close', and a negative correlation with 'Volume'.
4. Model Training and Evaluation

The 'Date' column was converted to datetime objects.
Features (Open, High, Low, Adj Close, Volume) and the target variable (Close) were defined.
The data was split into training and testing sets (80/20 split).
StandardScaler was used to standardize the features.
Four regression models were trained and evaluated:
Linear Regression
Decision Tree Regressor
Random Forest Regressor
XGBoost Regressor
Model performance was assessed using Mean Absolute Error (MAE) and R2 Score.
5. Model Performance Comparison

Linear Regression: MAE: 0.3317, R2 Score: 0.9989

Decision Tree Regression: MAE: 0.4553, R2 Score: 0.9976

Random Forest Regression: MAE: 0.3313, R2 Score: 0.9989

XGBoost Regression: MAE: 0.3610, R2 Score: 0.9988

Conclusion: Both Linear Regression and Random Forest Regression models demonstrated excellent performance with very low MAE and high R2 scores, indicating strong predictive accuracy for the stock's closing price. The Random Forest model showed a slightly better MAE.

6. Interactive Prediction Tool

An interactive Gradio application was created, allowing users to input 'Open', 'High', 'Low', 'Adj Close', and 'Volume' prices to get a predicted 'Close' price using the best-performing Random Forest model.
The application also includes tabs for visualizing price trends, distributions, and correlation analysis.
