# kickstarter-analysis
Performing analysis on Kickstarter data to uncover trends
# Kickstarting with Excel

## Overview of Project
This project analyzes how different Kickstarter campaigns fared based on their goals and launch dates.  The data is isolated to those with the parent category “theater” and subcategory “plays”.

### Purpose
The purpose of this project was to look for correlations between initial goals and their various outcomes, in addition to variances in the outcomes based on launch date.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/88443672/130395738-41fba801-9780-4232-8d03-d59f5f406d16.png)


### Analysis of Outcomes Based on Goals
![Outcomes_vs_Goals](https://user-images.githubusercontent.com/88443672/130395701-43ab5471-5adf-44c5-8acd-059710f448bf.png)

### Challenges and Difficulties Encountered
Writing out multiple SUMIFS or COUNTIFS statements can be time consuming.  Nesting equations can help speed that process up, allowing you to replicate the COUNTIFS or SUMIFS statements quickly.  For example, in cell C6, instead of using ">="&10000 and "<"&(15000), I opted to create a column with values to reference and nest formulas within the statements.  You can then easily copy those equations and use a find/replace excel feature to turn replicate # of successful for # of Failed.  

EG, =COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,">="&B6,Kickstarter!$D:$D,"<"&(B6+5000),Kickstarter!R:R,"plays")

![formula](https://user-images.githubusercontent.com/88443672/130397649-2c31ff5a-4e94-4909-a3e4-825ecedd188a.png)


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
Variance in failed outcomes per month is far lower than that of successful outcomes.  May, June, and July appear to have higher success rates vs the average, while Nov, Dec, and Jan appear to have lower success rates than the average.  A May-July launch date is preferred versus a launch date between Nov-Jan.  May and June successful outcomes are over one standard deviation higher than the median success rate.  Although canceled outcomes appear to be slightly higher at the start of the year, the month by month change in cancelled outcomes is insignificant to the overall data (2.7%).

- What can you conclude about the Outcomes based on Goals?
Projects with lower goals are more likely to be successful than those with higher goals.  Although projects with goals between 35,000-44,999 display success rates of over 60%, the sample size of data in these groupings is extremely small.  Projects with goals 15,000 and higher account for 8.21% of the dataset, while projects with goals of 25,000+ account for only 4.01% of the dataset.  If we group the 86 projects with goals at 15,000 or higher, the anomaly shown when categorizing in the prior groupings disappears, and the trend is very clear.    
![Outcomes_vs_Goals2](https://user-images.githubusercontent.com/88443672/130396497-5dbc64bf-85e9-4a8e-8b79-58e6b607ca69.png)

- What are some limitations of this dataset?
This dataset doesn’t include foreign exchange rates to normalize all goals and total pledges.  Ideally, we would need a much deeper set of data, including every donation and the corresponding time it was made to each project.  From there we could reference a historical foreign exchange time series table and covert each donation into a common currency as of the time it was made.

This dataset is fairly limited for referencing seasonality, as there are only 3 years of data included with any significant quantity.

This dataset is also skewed towards staff picks (10.89% of the dataset).  While only 66.28% of total projects are successful, 90.35% of staff picks are successful.  Additionally, while all pledges total 52.8% of the total goals (goals under 15k average to 72.5% funded), staff picks average at 97.1% funded.
 ![SP_Successful_Comparison_%_Funded](https://user-images.githubusercontent.com/88443672/130395782-d52e2a2e-cdb9-4fd3-bda7-9defa075b8b4.png)
![SP_Successful_Comparison_%_Successful](https://user-images.githubusercontent.com/88443672/130395810-1a04babd-c5ab-454c-988a-25ec0c760bd4.png)



- What are some other possible tables and/or graphs that we could create?
Average Donation by Goal
![Avg_Donation_vs_Goal](https://user-images.githubusercontent.com/88443672/130395893-cc331316-a791-4c68-9a28-27661d62f485.png)

Percent of Goal Pledged vs Sum of Total Projects
![Pct_Pledged_vs_Goal_AND_Total_Projects_Sum](https://user-images.githubusercontent.com/88443672/130443968-c5858174-4d0d-447d-aaeb-e2b3b5562f9a.png)

Total Pledged vs Goal by Goal Category
![Pledged_vs_Goal](https://user-images.githubusercontent.com/88443672/130396180-3378b25b-d3f7-465a-b39b-1c127e3f1162.png)

Total Projects vs Sum of Pledged by Goal Category Comparison
![Total Projects and Money Pledged by Goal](https://user-images.githubusercontent.com/88443672/130395988-f02e851d-55f8-416b-b88a-4c6c7cc64592.png)

Total Projects and Money Pledged by Goal
![Total_Projects_vs_Goal_AND_Total_Pledged_vs_Goal](https://user-images.githubusercontent.com/88443672/130395861-18d1d98c-368b-4ecf-aef7-81dd367c2709.png)

Total Donations by Goal
![Total Donations by Goal](https://user-images.githubusercontent.com/88443672/130396669-361aef2e-1bfd-40ce-9bbc-db21b30f628b.png)

Percent Funded by Goal
![Pct_Funded_vs_Goal](https://user-images.githubusercontent.com/88443672/130444148-c5a099bb-9167-4a18-b63a-d07d37956e5c.png)




