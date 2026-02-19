
<h1 align="center">Final Project Machine Learning                            
</h1>
<p align="center">Climate Impact on Agriculture</p>


# Exploratory Data Analysis (EDA) 

The exploratory data analysis was conducted to understand the structure, distributions, and relationships within the Global Agriculture Climate Impact dataset. The data were obtained from Kaggle, a public data science platform.  This data source combines agricultural productivity information with climate, environmental, and regional variables collected across multiple countries, regions, crop types, and years.

## 📊 Dataset Source

[Kaggle – Global Agriculture Climate Impact Dataset](https://link-aqui.com)
[https://www.kaggle.com/datasets/talhachoudary/global-agriculture-climate-impact-dataset](https://www.kaggle.com/datasets/talhachoudary/global-agriculture-climate-impact-dataset). 

The data analysis included data profiling to evaluate the dataset structure, variable types, and data completeness. The project aims to determine whether climate and agricultural factors can predict crop productivity, using Crop_Yield_MT_per_HA as the target variable in a supervised regression problem. Distribution analysis showed significant variability in crop yield and climate conditions, supporting the suitability of the dataset for modeling. Relationship and pattern analysis revealed that moderate temperature ranges and economic impact are positively associated with crop yield, while precipitation shows a more dispersed and non-linear influence. Overall, the findings suggest that agricultural productivity is influenced by multiple interacting factors.

**Data Profiling Report**

The dataset contains 10,000 rows  and 15 variables or columns, combining climate, agricultural, environmental, and regional information.The variables include 11 numerical features and 4 categorical features, providing sufficient complexity for exploratory analysis and machine learning modeling.

No missing values or duplicate rows were detected, indicating high data quality and reducing the need for extensive data cleaning.The dataset occupies approximately 3.1 MB in memory, making it efficient to process while still offering a rich representation of global agricultural and climate patterns.

**Data Statistics**
|  |  |
|---|:---:|
| Number of variables | 15  |
| Number of observations | 0 |
| Missing cells | 0 |
| Missing cells (%) |  0.0%  |
|Duplicate rows  | 0  |
| Duplicates rows |  0.0% |
|Total size in memory  |3.1 MiB |
| Average record size in memory | 323.5 B |

**Variable types**
|  |  |
|---|:---:|
| Numeric | 11 |
| Categorical | 4 |

**Problem Definition & Modeling Objective**

Based on the previous analysis of the dataset structure, this final project for the machine learning course aims to address the following research question:

**“Can climate, agricultural, and economic factors be used to predict agricultural productivity across different regions and years?”**

**Target variable**

The variable **Crop_Yield_MT_per_HA** was selected as the target variable because it directly represents agricultural productivity, measured in metric tons per hectare, the standard metric used in farming and environmental research. This metric enables consistent comparisons across regions, crop types, and years. 

The observed variability in crop yields is wide, suggesting that agricultural productivity is influenced by multiple interrelated factors rather than a single dominant variable. Furthermore, this supports the use of supervised machine learning regression models, which can capture complex, nonlinear relationships among climate conditions, regions, agricultural practices, and productivity.

**Type of model**

This project applies a supervised learning approach because the dataset includes a known target variable, Crop_Yield_MT_per_HA, which the model aims to predict. Since the model is trained on labeled data with an explicitly defined outcome, it is a supervised learning model. Furthermore, the target variable is numerical and continuous rather than categorical, meaning the task involves predicting a quantity rather than assigning a class label. Therefore, the model is a regression rather than a classification

**Features**
**Climate and environmental (numerical)**
|  |
|:---:|
| Average_Temperature_C |
| Total_Precipitation_nm |
| CO2_Emissions_MT |
| Extreme_Weather_Events |
| Soil_Health_Index |

**Agricultural practices (numerical)**
|  |
|:---:|
| Irrigation_Access_% |
| Fertilizer_Use_KG_per_HA|
|Pesticide_Use_per_HA|

**Temporal Feature (numerical)**
|  |
|:---:|
| Year|
 
 **Geographic and contextual features (categorical)**
|  |
|:---:|
| Region |
| Crop_Type|
|Adaptation_Strategies |

## Initial visualizations to explore patterns, distributions, and relationships 

In exploratory data analysis, a subset of key variables was selected to facilitate clear, interpretable visualizations. These variables were chosen because they represent the most direct climate and agricultural factors influencing crop yield, such as temperature, precipitation, extreme weather events, irrigation access, and fertilizer use.
Focusing on these representative features provides an initial understanding of patterns, distributions, and relationships within the data while avoiding visual complexity. The insights gained from this exploratory step help guide feature selection and modeling decisions in later stages of the machine learning workflow.

**Target variable distribution**

![Crop Yield Distribution](https://raw.githubusercontent.com/marcelarodriguez182/Machine_learning_Final_Project/main/Visualizations/Crop_yield_distribution_target.png)

The histogram of _Crop_Yield_MT_per_HA_ shows a broad range of values, indicating low to high agricultural productivity. The distribution shows considerable dispersion and slight right skewness, suggesting that higher yields are less frequent. No extreme outliers are observed, confirming that the target variable is appropriate for supervised regression modeling.

**Scatter plot: Crop_Yield_MT_per_HA vs Average_Temperature_C**

![Crop Yield per Ha vs Temperature](https://raw.githubusercontent.com/marcelarodriguez182/Machine_learning_Final_Project/main/Visualizations/Crop_yield_per_Ha_VS_Temperature.png)

The scatter plot between Average_Temperature_C and Crop_Yield_MT_per_HA indicates that crop yield varies across different temperature ranges rather than following a strictly linear trend. Higher yield values are more frequently observed at moderate temperatures, suggesting an optimal temperature range for agricultural productivity. The wide dispersion of points highlights the influence of additional factors beyond temperature, supporting the use of multivariate supervised learning models.

**Bar plot: Average Crop Yiel vs Cro Type**

![Average Crop Yield vs Crop Type](https://raw.githubusercontent.com/marcelarodriguez182/Machine_learning_Final_Project/main/Visualizations/Average_Crop_Yield_VS_Crop_Type.png)

The bar plot comparing average crop yield across crop types shows moderate differences in productivity.  
While all crops exhibit similar average yield levels, fruits, wheat, and sugarcane display slightly higher productivity, whereas cotton and vegetables show marginally lower values.  
These results suggest that crop type contributes to yield variation but is not a dominant factor on its own, reinforcing the importance of combining categorical and numerical features in modeling.

**Scatter plot: Crop_Yield_MT_per_HA vs Total_Precipitation_mm**

![Crop Yield vs Total Precipitation](https://raw.githubusercontent.com/marcelarodriguez182/Machine_learning_Final_Project/main/Visualizations/Crop_Yield_VS_Total_Precipitation.png)

The scatter plot between Total_Precipitation_mm and Crop_Yield_MT_per_HA shows high dispersion and no clear linear relationship between rainfall and crop yield. Crop productivity appears to vary widely across all precipitation levels, suggesting that precipitation alone does not determine yield outcomes. This pattern indicates a possible saturation effect and highlights the influence of additional climatic, environmental, and management factors.

**Scatter plot: Crop_Yield_MT_per_HA vs Economic_Impact_Million_USD**

![Crop Yield vs Economic Impact](https://raw.githubusercontent.com/marcelarodriguez182/Machine_learning_Final_Project/main/Visualizations/Crop_Yield_VS_Economic_Impact.png)

Economic_Impact_Million_USD represents the overall economic effect of agricultural activity, expressed in millions of U.S. dollars. It reflects the combined influence of crop productivity, market value, climate conditions, and agricultural investment within a given region and year. While higher crop yields generally contribute to greater economic impact, this variable captures broader economic dynamics beyond yield alone.

**Patterns**
The analysis of relationships between crop yield and key climatic, economic, and agricultural variables reveals several meaningful patterns. Crop yield tends to be higher within moderate temperature ranges, indicating a non-linear temperature–productivity relationship. Precipitation shows a highly dispersed pattern, suggesting that rainfall alone does not determine yield and may present a saturation effect at higher levels. Economic impact displays a clear positive association with crop yield, where higher economic context supports increased productivity while still allowing variability. Differences across crop types are present but moderate, highlighting that agricultural productivity is driven by the interaction of multiple factors rather than a single dominant variable.

**Distributions**
The distribution analysis of the dataset reveals significant variability across key numerical variables, particularly in crop yield and climate-related features. The target variable, _Crop_Yield_MT_per_HA_, shows a wide range of values, indicating the presence of low, medium, and high agricultural productivity levels. The distribution presents slight right skewness, suggesting that higher yield values occur less frequently. Climate variables such as temperature and precipitation also display broad distributions, reflecting diverse environmental conditions across regions and time periods. Overall, the distributions indicate that the dataset captures realistic variability, supporting the suitability of the data for supervised machine learning modeling.EDA.

## Preprocessing

**Data normalization or standard scaling**

After applying Standard Scaling, the numerical features were transformed to have a mean approximately 0 and a standard deviation approximately 1. This confirms that the scaling process was successfully applied and ensures that numerical variables contribute comparably during model training.

**Encoding categorical variables (if any)**

The increase from 14 to 69 features is due to one-hot encoding of categorical variables. Each unique category within Country, Region, Crop_Type, and Adaptation_Strategies was transformed into a binary indicator column. The final feature count equals the sum of the numerical variables plus the number of unique categorical levels, ensuring that categorical information is preserved without imposing artificial order.

**Handle missing values or outliers**

The data profiling report indicated that the dataset is relatively clean and well-structured. No significant missing values were detected, and the numerical variables exhibited reasonable ranges without extreme anomalies. The distributions appeared consistent with realistic agricultural and climatic conditions, suggesting that the data does not require extensive cleaning or corrective preprocessing. This overall data quality supports reliable model development and analysis.


**Perform feature engineering**

Feature engineering was applied to capture meaningful interactions within the agricultural system. The interaction between temperature and precipitation was created to reflect the combined climatic influence on crop yield, as productivity depends on their balance rather than individual effects alone. An agricultural input intensity variable was formed by combining fertilizer and pesticide use to represent overall management effort. Additionally, an interaction between fertilizer use and soil health was introduced to model how soil quality affects the efficiency of nutrient application. These engineered features aim to represent real-world agricultural dynamics better and improve model performance.


## Models Implementation

Linear Regression was used as a baseline model due to its simplicity and interpretability in capturing linear relationships between predictors and crop yield. The Decision Tree Regressor was included to model potential non-linear patterns and complex interactions. Comparing both approaches allowed us to evaluate whether agricultural productivity follows a linear structure or requires a more flexible model.

**Linear Reression**

• R² = 0.56. It is the percentage of variability in agricultural performance that the model explains; that is, it accounts for approximately 56% of the target's variability. An R² between 0.5 and 0.7 is considered reasonably good, given that we are working with climatic, agricultural, and economic data. However, the remaining 44% indicates inherent noise, unobserved variables, and uncaptured linear relationships.

• RMSE = 0.68 MT/HA (it is in the same units as the target). On average, the model errs by around 0.68 MT/HA. If performance is between 0.5 and 5, an error less than 1 is quite acceptable.

• MAE= 0.55 is the average absolute error, that is, the model fails 0.55 MT/HA. That MAE is 0.55, and RMSE is 0.68, indicates that no strong outliers are inflating the quadratic error; in this case, the error distribution is relatively homogeneous.

The model results indicate that climate, agricultural management, and economic variables can meaningfully predict agricultural productivity across regions and years. With an R² of 0.56, the model explains more than half of the variance in crop yield, demonstrating substantial predictive capability. Although prediction errors remain, the results confirm that these factors have significant explanatory and predictive power, supporting the original research hypothesis.

**Decision Tree Regressor**

•The model explains approximately 25.7% of the variability in agricultural yield (R² = 0.2569). This means the decision tree has limited capacity to capture patterns in the data.

•The RMSE (0.8856) is higher than in the linear regression model, indicating that the tree makes larger prediction errors. Since the RMSE penalizes large errors more, this suggests that the model is generating predictions with greater variability.

•The MAE (0.6736) is also higher than in the linear regression, confirming that, on average, the tree's absolute error is higher.

These results suggest that the Decision Tree did not generalize well to unseen data and may have suffered from high variance or overfitting. Therefore, based on both explanatory power and prediction error, Linear Regression remains the more suitable model for this problem.


**Advanced Techniques (Random Forest)**

The Random Forest model achieved an R² of 0.62, indicating that it explains approximately 62% of the variance in crop yield. The RMSE of 0.63 and MAE of 0.51 suggest relatively low prediction error compared to the overall yield range. The small gap between RMSE and MAE indicates stable predictions without extreme residual errors. Overall, the Random Forest model demonstrates strong predictive performance and effectively captures non-linear relationships within the dataset.


**Comparison linear regression model, decision tree regressor and random forest**

| Column 1 | Linear Regression | Decision Tree regressor |Random Forest |
|----------|----------|----------|----------|----------|
| R²  | 0.56  | 0.26   | 0.62   | Row 1E   | 
| RMSE  | 0.68  | 0.89   | 0.63   | Row 2E   |
| MAE   | 0.55   | 0.67   | 0.51   | Row 3E   |

• R².  Only 26% of the variability is explained, which is considerably worse than the linear model.
•RMSE. More large errors and higher model variance
•MAE. Worst average precision and less stable predictions.

Among the evaluated models, Random Forest achieved the highest predictive performance, with an R² of 0.62 and lower RMSE and MAE values compared to Linear Regression and Decision Tree. These results indicate that ensemble methods are better suited to capture the complex, non-linear relationships present in agricultural productivity data. Therefore, Random Forest was selected as the final model for this analysis.


## Conclusion

• The three models used in this project each present distinct strengths and weaknesses. Linear Regression offers simplicity, interpretability, and stable performance, making it a strong baseline model; however, it is limited in capturing complex nonlinear relationships. The Decision Tree Regressor is capable of modeling non-linear patterns and feature interactions, but it showed lower generalization performance and higher prediction error, likely due to high variance. Random Forest demonstrated the best overall performance by reducing overfitting through ensemble learning and capturing complex relationships more effectively, although it is less interpretable and computationally more intensive than Linear Regression.

•  The results demonstrate that agricultural productivity is influenced by a combination of climate, agricultural practices, and economic factors, confirming that it is a multifactorial problem rather than being driven by a single variable.

•  Future work would include incorporating additional variables, such as soil type, water quality, and machine type, and testing more advanced models to improve predictive performance further.

• Overall, this project demonstrates that machine learning is a powerful tool for analyzing agricultural productivity, enabling the identification of key influencing factors and improving the ability to make data-driven predictions across regions and time






*I used ChatGPT for some parts of this project





