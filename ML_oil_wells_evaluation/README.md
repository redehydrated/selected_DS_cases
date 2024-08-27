
# Oil Well Location Selection Project

## STACK
Used Libraries: pandas, numpy, matplotlib, scikit-learn, scipy.
Data Manipulation Techniques: Data splitting, data sampling, data cleaning, normalization, feature selection, outlier removal.
Approaches: Linear regression, Bootstrap method, Confidence intervals, Exploratory Data Analysis (EDA), cross-validation, mean squared error (MSE) calculation, risk assessment.

## 1. Brief Description of the Task
The task involves selecting an optimal location for drilling a new oil well based on geological survey data. The goal is to build a machine learning model that predicts oil reserves in various regions and determine which region offers the highest potential profit. The project includes risk analysis using the Bootstrap method to ensure profitability.

## 2. Description of the Dataset
The dataset contains geological exploration data from three different regions, each in a separate CSV file:
- **geo_data_0.csv**: Data from Region 0
- **geo_data_1.csv**: Data from Region 1
- **geo_data_2.csv**: Data from Region 2

Each dataset includes the following columns:
- **id**: Unique identifier for the well
- **f0, f1, f2**: Features representing geological characteristics (the exact meaning of these features is not disclosed, but they are significant for the model)
- **product**: The volume of oil reserves in the well (measured in thousands of barrels)

## 3. Formulate Business Task
The business objective is to maximize profit by selecting the most promising region for new oil well development. The specific tasks are:
1. Build a predictive model to estimate oil reserves in each well.
2. Use the model to select the top 200 wells in each region for potential development.
3. Analyze the predicted oil reserves to identify the region with the highest expected profit.
4. Evaluate the risks associated with oil well development in each region using the Bootstrap technique.

## 4. Summarizing Project Results in Table Form

| Item                           | Project Objective                                                               | Results                                                                                                    |
|-------------------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| Data Preparation              | Load and prepare geological data for analysis                                    | Successfully loaded data from three regions. Summary statistics calculated for each dataset.               |
| Model Training                | Train a linear regression model for each region to predict oil reserves          | Region 0: RMSE = 37.60, Mean = 92.34; Region 1: RMSE = 0.88, Mean = 69.10; Region 2: RMSE = 40.18, Mean = 94.98 |
| Profit Calculation            | Calculate potential profit for the selected wells in each region                 | Minimum required volume for breakeven: 111.11 thousand barrels; Average predicted volumes: Region 0 = 92.5, Region 1 = 68.83, Region 2 = 95.0 thousand barrels |
| Risk Analysis                 | Assess financial risk using the Bootstrap method                                 | Region 0: Mean = 398,825,357 RUB, 95% CI = (-139,807,476, 849,029,914) RUB, Risk = 7.7%; Region 1: Mean = 469,546,077 RUB, 95% CI = (102,417,595, 884,365,908) RUB, Risk = 0.2%; Region 2: Mean = 429,326,070 RUB, 95% CI = (-59,110,390, 956,737,599) RUB, Risk = 5.4% |
| Region Selection              | Recommend the best region for drilling based on profit and risk analysis         | Region 1 is recommended due to the highest expected profit and the lowest risk level (0.2% risk of loss). |

## 5. Detailed Methodology

**Income Calculation**: 
The potential income for each region was calculated by selecting the top 200 wells with the highest predicted reserves. The income for these wells was calculated based on the current price per thousand barrels of oil. The profit was then determined by subtracting the total development budget from the total income.

**Bootstrap Method**:
The Bootstrap method was used to assess the financial risk for each region. This involved generating 1,000 bootstrap samples of predicted reserves for each region, calculating the total income for each sample, and then determining the 95% confidence interval and the probability of a negative profit (loss).

## 6. Conclusions and Recommendations
- **Region 1**: With the highest mean income and the lowest risk of loss (0.2%), Region 1 is the most favorable location for new drilling.
- **Region 2**: This region has a higher risk level but still shows a high potential profit, making it a secondary option.
- **Region 0**: With the highest risk and a lower mean income, this region is less favorable for investment.

### Further Recommendations:
1. **Focus on Region 1**: Given its high profitability and low risk, Region 1 should be prioritized for drilling operations.
2. **Continuous Monitoring**: Update models regularly with new geological data to refine predictions and maintain profitability.
3. **Advanced Modeling**: Explore using more advanced machine learning models to improve prediction accuracy and further reduce financial risks.
