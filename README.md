# Impact of the Exam Weeks on Regular Physical Activity and Calories Burned

## Motivation and Aim
As an university student, life during exam weeks makes us feel fatigue and inactive with long hours of studying and limited time for physical activity. In this project we aim to explore whether my daily step count and calorie expenditure are significantly impacted during exam periods compared to regular days. By analyzing this data, we hope to gain insights into how exams influence my physical mobility and identify ways to better balance academics and well-being activities. 

## Null Hypothesis
Regardless of weather conditions or precipitation, my step count and calorie expenditure significantly decrease during exam periods compared to non-exam periods.

## Methods and Implementation
### Data Collection:
I allocate the daily step count and calorie data from the Health application on my iPhone for the past three years since I started university. Addition to that, I provide a detailed exam calendar for the analysis.
####
Determined exam periods: [29 May - 11 June 2023 , 6 January - 19 January 2024 , 28 May - 9 June 2024 , 5 November - 12 November 2024 , 30 December 2024 - 13 January 2025] 
Data provided by Apple is an export zip file including xml files of data. First, I extract only the relevant data, namely calorie expenditure and step count, from the XML files by manipulating it into daily, weekly, and monthly formats. In order to start analysis by drawing the outlayers and stating the huge picture I need to aggregate step_counts for each day rather than keeping the timestamps. 
![image](https://github.com/user-attachments/assets/0a4bf051-5ecb-44aa-b607-ef1b16936443)
When examining the distribution of step counts,I observed a left-shifted, right-tailed skewness resembling a normal distribution. To remove outliers from the data, I used boxplotting to identify outliers in the daily step count data. I replaced the outliers with the nearest boundaries within the dataset. Then, I performed boxplotting again to obtain the cleaned version of the data, free from outliers.
![image](https://github.com/user-attachments/assets/1853e09c-207e-421b-b38c-718974c73212)




### Data Processing:
The data will be set apart into two categories: Exam Week and Regular Time. Steps and calorie data during exam weeks will be isolated for comparison with the rest of the dataset.
### Analyzing by Python language:
Exploratory Data Analysis (EDA) will be conducted to identify patterns and trends. Statistical methods and visualizations will be used to compare physical activity and calorie expenditure between the two periods.
### Visualization:
Time-series plots, bar charts, and comparative visuals will be used to outline differences and draw comprehensive conclusions.

## Expected Output
A clear and compelling comparison of physical activity and calorie expenditure during exam weeks versus regular days. Statistics to validate the hypothesis that physical activity decreases during exam periods. Insightful visualizations that represents the findings effectively and clearly.

## Data Allocation
Steps and Calories: Daily step count and calorie data sourced from the Health application on my personal iPhone.
Exam Calendar: A detailed schedule of exam dates to identify and mark the exam weeks in the dataset.
