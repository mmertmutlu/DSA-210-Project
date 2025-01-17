# Impact of the Exam Weeks on Regular Physical Activity and Calories Burned

## Motivation and Aim
As an university student, life during exam weeks makes us feel fatigue and inactive with long hours of studying and limited time for physical activity. However we try our best to take care of our health and stay active even during these intense periods. The motivation is to conduct an analysis to understand how successful we have been in achieving this. In this project's scope we aim to explore whether my daily step count and calorie expenditure are significantly impacted during exam periods compared to regular days. By analyzing this data, we hope to gain insights into how exams influence my physical mobility and identify ways to better balance academics and well-being activities. 

## Expected Output
A clear and compelling comparison of physical activity and calorie expenditure during exam weeks versus regular days. Statistics to validate the main purpose of the project that physical activity decreases during exam periods. Insightful visualizations that represents the findings effectively and clearly.
To eliminate the weather effects, I also analyze weather conditions and precipitation levels to ensure that the reason for being inactive during exam periods is not influenced by weather-related factors.

## Hypotheses
### Null Hypothesis:
Regardless of weather conditions or precipitation, my step count and calorie expenditure do not change during exam periods compared to non-exam periods.

### Alternative Hypothesis:
Regardless of weather conditions or precipitation, my step count and calorie expenditure significantly decrease during exam periods compared to non-exam periods.

## Methods and Implementation
### Data Collection:
I allocate the daily step count and calorie data from the Health application on my iPhone for the past three years since I started university. Apple provides a zip file including everything which correlates with Health application. 
#### Determined a detailed exam periods:
Exam periods: 5 days before final week starts through end of the last final exam date. Midterms are not calculated.
[29 May - 11 June 2023 , 6 January - 19 January 2024 , 28 May - 9 June 2024 , 5 November - 12 November 2024 , 30 December 2024 - 13 January 2025] 

### Visualization:
Time-series plots, bar charts, box-plotting, violin-plotting, scattered-plotting, histograms and comparative visuals are used to outline differences and draw comprehensive conclusions.

### Data Processing and Analyzing by Python language:
Exploratory Data Analysis (EDA) will be conducted to identify patterns and trends. Statistical methods and visualizations will be used to compare physical activity and calorie expenditure between the two periods.

Data provided by Apple is an export zip file including xml files of data. First, I extract only the relevant data, namely calorie expenditure and step count, from the XML files by manipulating it into daily, weekly, and monthly formats. In order to start analysis by drawing the outlayers and stating the huge picture ,I need to aggregate step_counts for each day rather than keeping the timestamps.
##
![image](https://github.com/user-attachments/assets/0a4bf051-5ecb-44aa-b607-ef1b16936443)
##
![image](https://github.com/user-attachments/assets/d4338a1b-591d-4382-bd4a-ec5e9e436c0f)
##

When examining the distribution of step counts,I observed a left-shifted, right-tailed skewness resembling a normal distribution. To remove outliers from the data, I used boxplotting to identify outliers in the daily step count data. 

##
![image](https://github.com/user-attachments/assets/90caa37e-5cde-42ab-9c2a-307428f8538f)
##

I replaced the outliers with the nearest boundaries within the dataset. Then, I performed boxplotting again to obtain the cleaned version of the data, free from outliers.
##
![image](https://github.com/user-attachments/assets/1853e09c-207e-421b-b38c-718974c73212)
##                    
To explore the data more periodically, I analyzed its weekly, monthly, and yearly trends. I continued the analysis using bar charts, as they made the data easier to interpret.

First, I looked at the average step counts for each day of the week.
##
![image](https://github.com/user-attachments/assets/84577e38-6b49-4ef8-bf13-39b872deaaee)
##
It caught my attention that weekdays had higher step counts compared to weekends.

Next, I created a table to compare the average step counts for all days within a month.
##
![image](https://github.com/user-attachments/assets/97d70bc6-5e42-4ec3-bb7f-30f15c775d8c)
##

Finally, I extended the analysis to include the average step counts for each month in a year, allowing for a comprehensive comparison across these periodic trends.
##
![image](https://github.com/user-attachments/assets/ca8ea31f-3945-4070-9693-b51887ee4f6a)
##
In this bar chart, it is noticeable that my average step count is higher during the summer months, which are typically periods when I don’t have school. At first glance, this suggests that my hypothesis is on the right track. At the very least, I can observe that having school appears to contribute to a decrease in my step count.

Next, I compared the seven days moving averages for the seven days of the week with the daily step counts using a scatter plot.
##
![image](https://github.com/user-attachments/assets/8cab1944-354e-4325-b22d-c4e040d6b3da)
##
However, since this made statistical interpretation more challenging, I decided to focus on means and medians. I calculated the mean and median step counts for each day of the week and visualized them using scatter plotting.
##
![image](https://github.com/user-attachments/assets/c3bc89e5-7ce9-46aa-bf4e-cf17e047b959)
##
It is time to analyze the data by categorizing it into exam periods and non-exam periods as stated above. To start with , I create normalized histograms with KDE plots.
##
![image](https://github.com/user-attachments/assets/b60facbe-ce45-4600-899e-7697198161a6)
##
However, this approach is somewhat confusing for interpretation.

Subsequently I convert data to boxplotting and violin plotting, as I believed these methods would better highlight the differences. Using these two methods, the variations in step counts between exam periods and non-exam periods become much more accurated and differentiable.

## Box-Plotting
![image](https://github.com/user-attachments/assets/7561ade2-3867-49cc-a4e4-6a009c23e20f)
##
## Violin-Plotting
![image](https://github.com/user-attachments/assets/c9af29cf-116e-46f6-9c28-d587c0670d89)
##

The clear differences observed especially in the box plot make me feel closer to validating my hypothesis. During non-exam periods, the scale of step counts is noticeably higher, and the average is significantly elevated compared to exam periods.

I augmented the dataset with weather data to control for external factors might be caused by weather. Using an API, I extracted and processed data for the Istanbul region, including average temperature and precipitation levels, to establish a correlation with the non-exam period. 
##
![image](https://github.com/user-attachments/assets/8d5ba080-1a61-4dc4-946d-e40326b7b431)
##
The average temperature data is distributed in a pattern resembling a bimodal normal distribution. On the other hand, the precipitation levels typically remain below 10 mm, as observed during the analysis.

To demonstrate the relationship between step counts and weather or precipitation, I utilize scatter plots. I separate the data into exam periods and non-exam periods and identify, observe the overlapping cases.
##
![image](https://github.com/user-attachments/assets/904ff85b-3650-473d-828a-acf29fb41dff)
##
##
![image](https://github.com/user-attachments/assets/beb085f3-3f46-4a70-b683-480b8c008415)
##

## Machine Learning Concepts

Last but not least, I try to train with some machine learning concepts. As a ML I assign a NAIVE BAYES Classifier to predict whether the step count for the day is "healthy" (above or equal to 10,000) and how this variable relates to the data for in the exam period.

In this project, I leveraged tools from the pgmpy library to model and analyze the relationship between exam periods/non exam periods and step counts:

### Used Models from pgmpy library:

Bayesian Network: Defined a probabilistic graphical model to represent dependencies between ExamPeriod and Healthy.

Maximum Likelihood Estimation: Learned the Conditional Probability Distributions (CPDs) from the dataset, ensuring the model accurately reflected the observed data.

Variable Elimination: Used this inference method to calculate the probabilities of achieving a healthy step count during exam and non-exam periods.

This approach provided a clear and systematic way to analyze how exam periods affect physical activity levels, confirming the hypothesis that step counts tend to decrease during exam weeks.

More formally, the purpose is to find probabilities:
P(healthy|is_in_exam_period)P(healthy|¬is_in_exam_period)

First, the Gaussian hypothesis should be verified, that is that these variables are independent.
##
![image](https://github.com/user-attachments/assets/0c52929d-58db-4a30-9add-b993fc77578a)
##

Clearly there is no significant linear correlation between these variables. Furthermore, the mutual information score close to 0 suggests that these variables are independent. Thus the Gaussian hypothesis is true in this case.



I define the structure of the Bayesian Network and utilize Maximum Likelihood Estimation to learn the Conditional Probability Distributions (CPDs). An inference object is created to facilitate querying probabilities. 
##
![image](https://github.com/user-attachments/assets/c5dfa3a6-fa5b-48d6-90ee-d25ff592bb05)
##


## Conclusion and Findings

In this project, the threshold for determining the transition between being active and inactive was set at 10,000 steps. Following the analysis, it became evident that the likelihood of achieving a healthy step count (above 10,000 steps) increases by approximately 2% during non-exam weeks compared to exam weeks. As a result, the null hypothesis is rejected, and our expected hypothesis is validated.

The analysis clearly demonstrates the extent to which school, and particularly exam periods, impacts my physical activity levels. It highlights the challenges in maintaining a calorie deficit during these times, as reflected by the noticeable drop in my step counts. This project provides valuable insights into how academic demands influence daily physical activity.

## Limitations and Future Work

While conducting this project, I tried to eliminate external factors as much as possible; however, there are undoubtedly other side or external factors beyond weather that could influence my step count. Their inconsistency and the lack of sufficient data prevented me from including them in the analysis. I could have deepened my analysis by leveraging additional machine learning concepts. However, after validating my data—which I had isolated from external influences—using the reliable Naive Bayes method, I found no need to employ another machine learning tool within the limited timeframe of this project.

Through this project, I have become much more aware of the inactivity problem I have always approached with suspicion but never taken seriously during exam periods. To protect both my mental and physical health, as well as my self-confidence, I am determined to make a special effort to maintain my step count above an average of 10,000. I have also decided to start scheduling my study and project workloads well in advance of exam periods. This way, I will ensure that I do not succumb to the intensity and compromise my physical activities under any circumstances











