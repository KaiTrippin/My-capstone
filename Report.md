Titanic Data Analysis Report
1. Introduction
In this project, we analyzed the Titanic dataset to understand the key factors that influenced passenger survival. The dataset contains information about passengers such as age, gender, ticket class, fare, and family relations. The main objective was to clean the data, create meaningful features, explore patterns, and derive insights that explain survival outcomes.
The target variable used in this analysis is Survived, where 1 indicates the passenger survived and 0 indicates they did not. The project follows a structured pipeline including data cleaning, feature engineering, exploratory data analysis (EDA), and basic mathematical validation.
2. Cleaning Summary
The dataset initially contained several issues that required cleaning before analysis. The first step was inspecting the dataset structure using .info() and .isnull() to identify missing values and incorrect data types.
One of the main problems was missing values in the Age column. Since age is an important numerical feature, we filled missing values using the median, which is more robust to outliers than the mean. The Embarked column had a few missing values, which were filled using the mode because it is a categorical feature.
The Cabin column contained a large number of missing values, making it unreliable for analysis. Therefore, it was removed. Similarly, columns such as Ticket and Name were dropped because they either contained too many unique values or did not directly contribute to the analysis.
We also checked for duplicate rows and removed them to avoid bias in the analysis. Data types were corrected where necessary, converting categorical variables such as Sex and Pclass into appropriate formats.
Outliers were handled in the Fare column using the 99th percentile capping method. This ensured that extreme values did not distort the analysis while still preserving the majority of the data distribution.
Finally, validation checks were applied to ensure data quality. These included verifying that there were no remaining missing values, ensuring all fare values were non-negative, and confirming that the dataset retained a valid structure after cleaning.
3. Feature Engineering Summary
After cleaning the data, new features were created to improve the quality of analysis. Feature engineering plays a crucial role in uncovering hidden patterns that are not directly visible in raw data.
One important feature created was FamilySize, which combines the number of siblings/spouses (SibSp) and parents/children (Parch) along with the passenger themselves. This feature helps capture the effect of traveling alone versus with family.
Another useful feature was FarePerPerson, calculated by dividing the fare by the family size. This gives a more accurate representation of the cost per individual rather than the total ticket cost.
An interaction feature called Age_Class was also created by multiplying age and passenger class. This helps capture how age and socio-economic status interact in influencing survival.
To address skewness in the data, the Fare column was log-transformed using log1p. This transformation made the distribution more normal and easier to analyze.
Categorical variables such as Sex and Embarked were converted into numerical form using one-hot encoding. This step is essential for mathematical operations and further analysis.
The Age column was also grouped into categories (Child, Adult, Senior) to simplify analysis and highlight patterns across age groups.
Finally, highly correlated features were identified using a correlation matrix. Redundant features were removed to avoid duplication of information and improve clarity.
4. Key Findings
The exploratory data analysis revealed several important insights about survival patterns on the Titanic.
First, gender was the strongest predictor of survival. Female passengers had a significantly higher survival rate compared to males. This suggests that evacuation priority may have been given to women.
Second, passenger class had a major impact on survival. Passengers in first class had the highest survival rates, while those in third class had the lowest. This reflects differences in cabin location, access to lifeboats, and overall socio-economic status.
Third, family size influenced survival probability. Passengers traveling alone or in small families had better survival rates compared to those in large families. Large groups may have faced difficulties coordinating during evacuation.
Additionally, the Fare variable showed that passengers who paid higher fares were more likely to survive. This is consistent with the effect of passenger class and wealth.
Visualizations such as histograms, boxplots, and heatmaps supported these findings by clearly showing distributions and relationships between variables. For example, the correlation heatmap highlighted strong relationships between survival and features like sex and class.
5. Mathematical Validation
Basic mathematical techniques were used to validate the analysis. The mean and standard deviation of the target variable were computed manually using NumPy to ensure understanding of the underlying calculations.
Standardization was also applied manually to a numerical column and compared with the output from StandardScaler. This confirmed that both methods produced consistent results.
Cosine similarity was calculated between feature vectors of passengers with different survival outcomes. This provided a measure of how similar or different their characteristics were.
Finally, probability estimation was used to compute the likelihood of survival given certain conditions. For example, the probability of survival among female passengers was significantly higher than the overall average.
6. Next Steps
If more time were available, several improvements could be made. A predictive model such as logistic regression or decision trees could be built to quantify the importance of each feature.
More advanced feature engineering could also be explored, such as extracting titles from passenger names or grouping ticket information. Additionally, hyperparameter tuning and model evaluation techniques could be applied to improve prediction accuracy.
Another potential extension would be to create a dashboard that visually summarizes key findings in a single view, making it easier for stakeholders to interpret the results.
Conclusion
This project demonstrated the full data analysis pipeline, from cleaning raw data to extracting meaningful insights. By transforming messy data into a structured format and applying thoughtful analysis, we were able to uncover clear patterns that explain survival on the Titanic.
The results highlight the importance of data preparation, feature engineering, and visualization in making informed conclusions from real-world datasets.
