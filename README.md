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















