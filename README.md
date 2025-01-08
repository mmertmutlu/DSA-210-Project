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

Data provided by Apple is an export zip file including xml files of data. First, I extract only the relevant data, namely calorie expenditure and step count, from the XML files by manipulating it into daily, weekly, and monthly formats. In order to start analysis by drawing the outlayers and stating the huge picture ,I need to aggregate step_counts for each day rather than keeping the timestamps.

![image](https://github.com/user-attachments/assets/0a4bf051-5ecb-44aa-b607-ef1b16936443)

When examining the distribution of step counts,I observed a left-shifted, right-tailed skewness resembling a normal distribution. To remove outliers from the data, I used boxplotting to identify outliers in the daily step count data. I replaced the outliers with the nearest boundaries within the dataset. Then, I performed boxplotting again to obtain the cleaned version of the data, free from outliers.

![image](https://github.com/user-attachments/assets/1853e09c-207e-421b-b38c-718974c73212)
                     ![image](https://github.com/user-attachments/assets/0863129b-27f9-4b3a-a386-9fb4ed267aa9)

To explore the data more periodically, I analyzed its weekly, monthly, and yearly trends. I continued the analysis using bar charts, as they made the data easier to interpret.

First, I looked at the average step counts for each day of the week.

![image](https://github.com/user-attachments/assets/84577e38-6b49-4ef8-bf13-39b872deaaee)

It caught my attention that weekdays had higher step counts compared to weekends.

Next, I created a table to compare the average step counts for all days within a month.

![image](https://github.com/user-attachments/assets/97d70bc6-5e42-4ec3-bb7f-30f15c775d8c)


Finally, I extended the analysis to include the average step counts for each month in a year, allowing for a comprehensive comparison across these periodic trends.

![image](https://github.com/user-attachments/assets/ca8ea31f-3945-4070-9693-b51887ee4f6a)

In this bar chart, it is noticeable that my average step count is higher during the summer months, which are typically periods when I don’t have school. At first glance, this suggests that my hypothesis is on the right track. At the very least, I can observe that having school appears to contribute to a decrease in my step count.

Next, I compared the seven days moving averages for the seven days of the week with the daily step counts using a scatter plot.

![image](https://github.com/user-attachments/assets/8cab1944-354e-4325-b22d-c4e040d6b3da)

However, since this made statistical interpretation more challenging, I decided to focus on means and medians. I calculated the mean and median step counts for each day of the week and visualized them using scatter plotting.

![image](https://github.com/user-attachments/assets/c3bc89e5-7ce9-46aa-bf4e-cf17e047b959)

It is time to analyze the data by categorizing it into exam periods and non-exam periods as stated above. To start with , I create normalized histograms with KDE plots.

![image](https://github.com/user-attachments/assets/b60facbe-ce45-4600-899e-7697198161a6)

However, this approach is somewhat confusing for interpretation.

Subsequently I transition data to boxplotting and violin plotting, as I believed these methods would better highlight the differences. Using these two methods, the variations in step counts between exam periods and non-exam periods become much more accurated and differentiable.

![image](https://github.com/user-attachments/assets/7561ade2-3867-49cc-a4e4-6a009c23e20f)

The clear differences observed in the box plot make me feel closer to validating my hypothesis. During non-exam periods, the scale of step counts is noticeably higher, and the average is significantly elevated compared to exam periods.








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
