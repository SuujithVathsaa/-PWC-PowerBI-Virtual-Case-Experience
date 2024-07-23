#PWC PowerBI Virtual Case Experience

📋 Introduction

This repository displays the process and outcomes of the tasks completed during the PwC Switzerland PowerBI Virtual Case Experience developed by Forage. The virtual internship is created to simulate work in the Digital Accelerator team at PwC Switzerland and leverages Power BI.

All of these .pbix files and insights were my submissions for this program, except for the data files which were assigned by PwC Switzerland.

📌 Scenario

At PwC, we work with global organizations, upskilling our 276,000 employees. Our goal is to provide everyone with the opportunity to learn, work, and participate in the digital world. Our employees have the chance to become "Digital Accelerators" by rapidly deepening their skills in digital specialties such as data, automation, AI, and digital storytelling. They do this by learning self-service tools and coding languages and applying these skills across our business. Your manager, Giulia, will guide you through your upskilling journey in PowerBI. You'll become a data Jedi and Digital Accelerator. An important client has reached out to you for help visualizing their data.

This virtual experience program consists of 3 tasks:

    Task 1: Create Call Centre Dashboard - visualizing customer and agent behavior.
    Task 2: Create Customer Retention and predict churn customers - visualizing customer demographics and insights.
    Task 3: Create Diversity and Inclusion in HR - visualizing gender balance in the executive suite.

⚙️ Technical Stack

Visualization:

    Microsoft PowerBI
   

Predictive analysis:

    Language: Python 3.11
    Package: Pandas, Numpy, scikit-learn, XGBoost

Task Two: Call Center Analysis | Pwc Switzerland Power BI Virtual Case Experience

Table of contents

    Problem Statement
    Data Preparation
    Data Modeling
    Data Visualization
    Analysis and Insights
    Shareable Link

Problem Statement

    Problem: The manager at PhoneNow (a big telecom company) is seeking transparency and insight into the Call Center dataset to gain an accurate overview of long-term customer and agent behavior trends.
    Objective: The purpose of this analysis is to create a dashboard in Power BI for the Call Center Manager that reflects all relevant Key Performance Indicators (KPIs) and metrics to:
        Self-exploratory call trends
        Overview of the agent’s performance and behaviors
        Overview of customer satisfaction
        Contain many metrics and plots related to a single area of business for discussing with higher managers and generating further analysis.
        Allows for minimal interaction
    Possible KPIs include (but are not limited to):
        Overall customer satisfaction
        Overall calls answered/abandoned
        Calls by time
        Average speed of answer
        Agents performance quadrant -> average handle time(talk duration) vs calls answered

Data Sourcing

The dataset used for this analysis was provided by PwC Switzerland and is available here: Call Center Dataset
Data Preparation

The dataset was loaded into Microsoft Power BI Desktop for transformation in Power Query and modeling.
Metadata
File name	Format	Size	Fields	Entities
01 Call-Center-Dataset	.xlsx	249KB	10	5000
Fields Description
Field Name	Description	Data Type
Call Id	Represents every unique observation in the dataset	Text
Agent	Describes the name of the agent	Text
Date	Describes the date of the call	Date
Time	Represents the time of the call	Date/Time
Topic	Describes the topic of the caller	Text
Answered (Y/N)	Describes if the call was answered or not	Text
Resolved	Describes if the problem was Resolved or not	Text
Speed of answer in seconds	Represents the speed of answer in seconds	Decimal number
AvgTalkDuration	Represents the average talk duration of a call	Time
Satisfaction rating	Represents the satisfaction rating of the agent during the call	Decimal number
Data Cleaning

Data Cleaning for the dataset was done in Power Query as follows:

    Unnecessary columns were removed
    Each of the columns in the table was validated to have the correct data type
    Unnecessary rows were removed

Data Transformation

To ensure the comprehensive satisfaction of customers, an additional column named Satisfaction Likert was created for referencing using the M-formula:

m

Table.AddColumn(#"Added Custom", "Satisfaction Likert", each if [Satisfaction rating] = 1 then "Very poor" else if [Satisfaction rating] = 2 then "Poor" else if [Satisfaction rating] = 3 then "Average" else if [Satisfaction rating] = 4 then "Good" else "Very good")

Here is a breakdown of what the formula does:

    For the dataset, we want to transform the satisfaction rating from number to text based on the Likert scale with the condition if Satisfaction rating = 1, it will display the rating as “Very poor”, respectively for each value of Satisfaction rating.

Data Modeling

After the dataset was cleaned and transformed, it was ready to be modeled, but the dataset just included one table, so the Data Modeling is nothing much to modify.
Data Visualization
![image](https://github.com/user-attachments/assets/45264748-dfa9-4ff8-958e-102b44f89cf4)

Analysis and Insights

The purpose of this dashboard is to serve as self-exploratory for managers, but I still note some highlighted points that I recognize below:
About Call trends:

    Customers tend to call more between 5:00 pm - 5:30 pm at 250 calls received with an abandoned rate is 18.40% (approximately to the average abandoned rate) and distributed mainly in the middle of the month
    The highest abandoned rate is 28.03% between 1:00 pm - 1:30 pm
    Customers have more problems with Streaming service
    The resolved rate is at a high rate (89,94%)

About performance of agents:

    The agent who satisfies customers most is Becky with a 12.02% of “Very good” rating
    The agent who has the highest resolved rate is Jim and he is effective with solving problems related to “Contract related” and “Admin Support”

About customer satisfaction:

    The average customer satisfaction is at an acceptable rate with 3.40, mainly comes from “Average” (30.04%) and “Good” (29.11%) rating
    The correlation between call answered and call resolved is strongly positive which resulted in an increase in the customer satisfaction rate
