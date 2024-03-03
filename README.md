# Alpine-Blossom
M ML/AI projects bloom from curiosity, aiming to merge tech with humanity. Inspired by alpine resilience, each project includes thoughtful analyses of their implications for business and society.

# Case Study: Will a Driver Accept a Coupon?

Feburary, 2024  
Shan Gao, PhD
Berkeley Engineering & Haas ML/AI Program Student

LinkedIn profile: https://www.linkedin.com/in/sgaoaggie/  
GitHub: Alpine Blossom: https://github.com/Sandysmile  
Google Slide Outline: https://docs.google.com/presentation/d/1adcba3vTWLqV02LNXXaj0TSc9al2WBp54QyLO7MhBOI/edit?usp=sharing  


# Data Mining Report: Analyzing Coupon Acceptance Among Drivers 

## Introducatin
This report presents an in-depth analysis of factors influencing coupon acceptance among drivers, employing data visualization and probabilistic analysis to uncover multifaceted determinants. Utilizing the CRISP-DM methodology, the aim is to prepare and explore coupon data thoroughly, segmenting the drivers to understand their preferences and behaviors, and establishing hypotheses for predictive modeling to predict coupon acceptance outcome. 

This work sets the foundation for understanding data quality, gaps, forming hypotheses, and developing a predictive classification model.


## 1.Business Understanding and Implications
The investigation begins by addressing the core business question: What influences a driver's decision to accept a coupon? Understanding these variables is essential for crafting targeted promotional strategies that resonate with potential customers, thereby enhancing marketing campaign effectiveness.

## 2.Data Understanding

### 2.1 Conceptual Framework
A comprehensive set of factors are examined in the analysis:
•	Demographics: Includes age, gender, marital status, education, occupation, and income.  
•	Behavioral Patterns: Analyzes frequency of visits to dining establishments, bars, coffee houses, and takeaway habits.  
•	Situational Context: Considers destination, weather, time of day, and passenger presence.  
•	Coupon Characteristics: Investigates coupon type, expiration, and offering time.  

### 2.2 Data Description

The dataset is presented in tabular /CSV formats, encapsulating past data on coupon acceptance, including cases where coupons were both accepted and not. It comprehensively covers four conceptual elements essential to our analysis:  

User Attributes  
•	Gender: Categories include male and female.  
•	Age: Ranges from below 21 to various brackets up to thirty and beyond.  
•	Marital Status: Includes single, married, unmarried partner, and widowed.  
•	Number of Children: Specifies if the individual has 0, 1, or more than one child.  
•	Education: Varies from high school to graduate degrees.  
•	Occupation: Encompasses a range from architecture & engineering to business & financial sectors.  
•	Annual Income: Classified from less than $12500 to various brackets up to $37499 and beyond.  
•	Lifestyle Patterns: Includes frequency of visits to bars, coffee houses, and both less expensive and mid-range restaurants, along with takeaway food purchases.

Contextual Attributes  
•	Driving Destination: Options are home, work, or no urgent destination.  
•	Geographical Location: Includes user, coupon, and destination locations, with maps indicating distances and driving times.  
•	Weather: Conditions noted as sunny, rainy, or snowy.  
•	Temperature: Measured as 30F, 55F, or 80F.  
•	Time: Specific times noted as 10AM, 2PM, or 6PM.  
•	Passenger Presence: Identifies if the user is alone, with a partner, kid(s), or friend(s).

Coupon Attributes  
•	Expiration Time: Noted as 2 hours or one day.  


### 2.3 Data Structure and Quality Understanding


An initial assessment using the panda’s methods (describe, head, etc.) to reveal the dataset's structure, highlighting:  

•	Number of Rows: Each row corresponds to individual driver data. The data quality assessment prioritizes the identification and remediation of duplicates and missing values to ensure data integrity.

•	Number of Columns: Encompasses the column names, data types, and the range of unique values. The evaluation of data quality and transformation examines the distribution of values within each column, assessing the prevalence of missing values and the appropriateness of data types. This process also considers the necessity of generating new columns to enhance visualization or analytical clarity.

The dataset comprises 12,684 coupon records across twenty-six variables, providing a rich source for analysis.
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/910e0bf8-44ca-4546-997e-395bc635b073)

#### 2.3.2 Column Summary I
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/baefc3d6-3b44-4cad-ba56-323cc65e418a)
#### 2.3.3 Column Summary II
provides the unique values details for each column.
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/a61e0eaf-884a-4a66-a59a-9b1922519555)

This Panda’s profiling package generates a comprehensive data quality report that facilitated my visual understanding of the dataset's integrity, particularly in identifying missing values and duplicates.
#### 2.3.4 Report Profile Examples
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/b92282f7-f8c9-4dfa-9d24-cd043cf8d102)

### 2.4 Summary of Data Cleaning and Preparation Actions Taken:

1.	Column Exclusion: The 'car' column was eliminated due to its minimal non-missing data, with only 108 entries out of 12,684 records, rendering it non-representative for analysis.  
2.	Missing Value Treatment: Cleared missing entries from critical columns, including 'CoffeeHouse', 'CarryAway', 'RestaurantLessThan20', and 'Restaurant20to50', to ensure the integrity of the dataset.  
3.	Duplicate Records: Identified and deleted duplicate entries to maintain dataset uniqueness and reliability.  
4.	Column Creation: Introduced a new 'Object' type column named 'coupon accepted'. This facilitates clearer visualization and aids in subsequent plotting and analysis tasks by distinctly marking coupon acceptance statuses.

## 3 Coupon Data Visualization and Probability Analysis
### 3.1 Visualization of Coupon Offers

![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/8ab6579d-3aeb-4b9b-a6d0-7d36e90a8f7e)

Insights #1:   
Coffee House coupons were offered most to the drivers, followed by budgeted restaurants, carryout options, bars, and lastly, upscale restaurants.   
Question:
Did the coupon promotion marketing assume coffee house coupons are the most acceptable coupon type among the others? The questions led me to explore the coupon acceptance rates for different coupon types for more insights.   


### 3.2 Bar Chart of Coupon Acceptance Rates by Type
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/eda43d66-2000-4852-b649-0c53b8ea0e24)

### 3.3 What are the Coupon Acceptance Rates for the Coupon Dataset and distinct types of coupons separately in statistics and visual?

The Average Coupon Acceptance Rate for All Coupons: 0.5675654242664552.  
Coupon Acceptance Rates by coupon type:

![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/b291c6af-afdd-4330-847d-e6fe24db6db7)

Insights #2
Carry-out coupons are the most acceptable coupons, followed by budget restaurants. On average, coffee houses, upscale restaurants, and bar coupons have significantly lower acceptance rates, in the 0.4 range. Compared to conduct and budget restaurant.

Question: should we promote more conduct coupons instead?

Let us look at a bar chart of coupon rates comparing to the overall average.
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/3d4d611b-cf3a-4782-be68-921421abb2b5)
Action #1: Data Analysis Approach Taken:
1.	Coupon Subset Focus: Concentrated on analyzing 'Bar' (identified as the least popular) and 'Carry-Out' (the most favored) coupon types for detailed scrutiny.  
2.	Coupon Attributes Analysis: Examined how unique features of coupons impact their acceptance among customers.  
3.	Environmental Impact Assessment: Evaluated how universal factors like weather and temperature influence the likelihood of coupon acceptance

### 3.4 Coupon Attributes (Expiration and Time) and Coupon Acceptance Rate
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/b6d58830-8a16-453e-9b6b-3e0db64cf7e1)
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/861c6ff4-48fb-41c0-9d8f-ce0c3ec1740b)

Insights #3 on Coupon Expiration and Timing:  

•	Coupon Expiration Preference: Analysis reveals drivers display a stronger preference for coupons with a one-day expiration than those requiring immediate action within two hours consistently across different coupon types.    
This suggests the need to reevaluate the strategy behind short-term promotions, acknowledging that drivers value the flexibility to plan their redemption, despite the convenience of instant access via their phones.

•	Coupon Timing Relevance: The analysis indicates that drivers' acceptance of coupons varies significantly across different coupon types and times, aligning with their lifestyle, commuting patterns, or daily routines.   
This observation underscores the importance of further investigating the timing aspect to refine our approach to coupon promotions, ensuring they resonate more effectively with the intended recipients' schedules.

Analytics Action taken:  
Consider coupon time as the only coupon attribute for further analysis.

### 3.5 Temperature Histograms and Coupon Acceptance Rates
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/5b8a59ac-33f5-4eb3-bf46-7dd64bd1b018)
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/ab57b090-16b4-4fb3-bb1c-b75b144bc34d)
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/100d3e65-5373-4bf3-9de8-6103dc475b13)

### 3.6 Summarized Coupon Attributes and Temperature related variables Analysis

Insights:
1)	Coupon Offer Distribution: Coffee House coupons were the most frequently offered, followed by budget restaurants, carryout options, bars, and upscale restaurants.   
2)	Coupon Acceptance Rates: Carryout coupons emerged as the most accepted coupon type, with budget restaurants also showing high acceptance. In contrast, coffee houses (the most frequently offered), upscale restaurants, and bars had notably lower acceptance rates, averaging in the 0.4 range. This indicates a clear preference among drivers for conducting coupons over others.  
3)	Expiration and Timing Preferences: Drivers prefer coupons with a one-day expiration, valuing the flexibility to plan over the immediacy of two-hour offers. Additionally, it suggests a need to align coupon offers with drivers' lifestyles and schedules for more effective promotion strategies for all coupon types.  
4)	Environmental Influences: The analysis, primarily conducted on sunny days across three temperature ranges, reveals a positive correlation between coupon acceptance and comfortable, sunny weather conditions. This finding suggests that favorable environmental conditions play a role in increasing coupon engagement, pointing towards the importance of considering weather factors in coupon distribution plans.

Analytics Actions:

1)	Focused on 'Bar' and 'Carryout' coupons, identifying them respectively as the least and most popular among drivers for in-depth analysis.  
2)	Expiration Attribute/Temperature Exclusion: Opted to remove expiration time from in-depth analysis due to its uniform application across coupon types across coupon types.  
3)	Coupon Timing: Identified coupon timing as a critical variable for further analysis, especially for 'CarryOut' coupons, to align promotional efforts with drivers' preferences and routines.  
4)	Weather Variable Exclusion: This decision acknowledges the dataset's sunny condition bias, aiming for a more representative understanding of factors driving coupon acceptance without the skewed influence of incomplete weather data.

## 4 Bar Coupon Acceptance
This analysis, delineated by factors such as bar visit frequency, age, income, occupation, marital status, and passenger presence, offers detailed insights into bar coupon redemption patterns.

### 4.1	Bar Coupon Data Segmentation

•	Establish a focused subset for bar coupons for targeted analysis.

### 4.2	Data Integrity and Structure Review

•	Follow previously outlined steps to review the dataset structure and quality. I did notice duplicates and removed them from the subset.

### 4.3 Calculate Bar Coupon Acceptance Rate: 0.4118572927597062 as the benchmark.

### 4.4 Compare the Acceptance Rate between Those Who Went to a Bar Three or Fewer Times a Month to Those Who Went More.

•	Rate Analysis and Visualization: Utilized grouping and mean methods to calculate acceptance rates for drivers based on their frequency of bar visits. Drivers meeting the specified criteria were labeled/flagged 'in' within the dataset.  
•	The resulting statistics are listed below, followed by a bar chart for visual representation.  

![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/435a82c8-a083-4ca5-a200-b7ccfc4c6b6b)
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/dd7b5e72-1e72-414c-8a98-5b78d7baa882)

### 4.5 Compare the acceptance rate between drivers who go to a bar more than once a month and are over the age of twenty-five to all others. Is there a difference?
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/66ada06e-f695-40af-8217-bea89b2bd1a9)
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/29595231-1594-460e-8590-dec6aa5903de)

### 4.6 Use the same process to compare the acceptance rate between drivers who go to bars more than once a month and had passengers that were not kids and had occupations other than farming, fishing, or forestry.
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/66e92803-baee-4da4-9948-8ab54c6accdd)
![image](https://github.com/Sandysmile/Alpine-Blossom/assets/20648423/b32eebaf-a43c-4491-9f2d-e9fcfa1b385f)






























