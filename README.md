# Yield Curve Construction for U.S. Interest Rates

## 1. Introduction

This project involves constructing the yield curve for U.S. Treasury rates using historical data. The yield curve is a graphical representation showing the relationship between the interest rate (or cost of borrowing) and the time to maturity of debt securities for a given borrower in U.S. Treasury bonds. The project uses the historical U.S. Treasury rates for various maturities from 1 month to 30 years. The goal is to construct the yield curve using the **Nelson-Siegel** and **Nelson-Siegel-Svensson** models, visualize the yield curves over time, and analyze the principal components of the data using **PCA** (Principal Component Analysis).

## 2. Dataset Source

The dataset used in this project can be found at:

- [Yield Curve Data - JPMorgan Chase GitHub](https://github.com/jpmorganchase/python-training/blob/main/data/yield_curve.csv)

## 3. Methodology

1. **Data Preprocessing**:
   - Load the dataset and clean any missing or null values.
   - Drop irrelevant columns and retain the ones necessary for the yield curve construction.

2. **Modeling**:
   - Use the **Nelson-Siegel** model to fit the yield curve.
   - Apply the **Nelson-Siegel-Svensson** model for a more refined curve fitting.

3. **Principal Component Analysis (PCA)**:
   - Perform PCA to analyze the main components that explain the variance in the yield curve.
   - Plot the explained variance ratios and cumulative explained variance.

4. **Visualization**:
   - Generate 3D surface plots to visualize the yield curve for various maturities over time.
   - Plot the yield curves over different time periods for a comparative analysis.

## 4. Approach

### 4.1 Data Cleaning and Preprocessing
We start by loading the dataset and performing the following steps:
- Drop irrelevant columns.
- Check for and handle missing values using linear interpolation.
- Set the date column as the index for time series analysis.

### 4.2 Yield Curve Construction
We use the **Nelson-Siegel** and **Nelson-Siegel-Svensson** models to fit the yield curve:
- **Nelson-Siegel** Model: Used to estimate the yield curve based on maturity, with parameters including level, slope, and curvature.
- **Nelson-Siegel-Svensson** Model: An extension of the Nelson-Siegel model, adding a second curvature term for more flexibility in fitting the curve.

### 4.3 Principal Component Analysis (PCA)
PCA is applied to analyze the variance in the data and extract the most important features:
- Standardize the data.
- Perform PCA and plot the explained variance for each principal component.
- Reconstruct the dataset using the top components.

## 5. Results

### 5.1 Yield Curve Plots
- **Nelson-Siegel Yield Curve**: Visualized for different maturities, from 1-month to 30-years.
- Inference: The curve appears to be upward sloping, indicating that longer-term yields are higher than shorter-term yields
  ![Nelson-Siegel](https://github.com/1Aditya7/Yield-Curve-Construction-for-US-Interest-Rates/blob/main/yieldcurve_media/nelsonSiegel.png)  
- **Nelson-Siegel-Svensson Yield Curve**: Provides a refined curve with additional curvature terms.
- Inference: This additional parameter in the NSS model allows for more flexibility in fitting the yield curve
  ![Nelson-Siegel-Svensson](https://github.com/1Aditya7/Yield-Curve-Construction-for-US-Interest-Rates/blob/main/yieldcurve_media/nelsonSiegelSvensson.png)  

### 5.2 Principal Component Analysis
- Bar plots of the explained variance ratio by the top principal components.
- Inference: The plot shows the weights of different maturities in the top portfolios for three principal components. The first component captures the overall level of the yield curve, the second component captures the slope, and the third component captures the curvature.
  ![PCA](https://github.com/1Aditya7/Yield-Curve-Construction-for-US-Interest-Rates/blob/main/yieldcurve_media/pca.png)

### 5.3 3D Surface Plot
- A 3D surface plot was generated to visualize how the yield curve changes over time with varying maturities.
- Inference: The x-axis represents time, the y-axis represents bond maturity, and the z-axis represents the yield. 
  ![3D-Plot](https://github.com/1Aditya7/Yield-Curve-Construction-for-US-Interest-Rates/blob/main/yieldcurve_media/3d.png)

### 5.4 Reconstructed Dataset
- The plot visualizes the reconstructed Treasury yield curve over time, showing the evolution of yields across different maturities.
- Inference: The plot shows the evolution of the Treasury yield curve over time. Each line represents a different maturity, from 1-month to 30-year bonds. The plot shows how the shape and level of the yield curve have changed over time, reflecting changes in interest rates and economic conditions.
  ![Reconstructed Dataset](https://github.com/1Aditya7/Yield-Curve-Construction-for-US-Interest-Rates/blob/main/yieldcurve_media/reconstructed.png)

## 6. Limitations and Future Scope

### Limitations:
- The models used (Nelson-Siegel and Nelson-Siegel-Svensson) are parametric and may not capture all the complexities of the yield curve.
- Missing data was handled by linear interpolation, which may not be ideal for all cases.
  
### Future Scope:
- Explore machine learning models for yield curve fitting, such as regression models, to see if more complex models can improve accuracy.
- Investigate the impact of macroeconomic factors on the yield curve and extend the analysis to different countries' yield curves.

## 7. Conclusions

The project successfully constructs the yield curve using the **Nelson-Siegel** and **Nelson-Siegel-Svensson** models and visualizes it for different maturities. The PCA analysis provides valuable insights into the main components driving the variability in the yield curve. Further enhancements can be made by exploring more advanced models and incorporating external factors affecting the yield curve.
