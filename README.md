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







