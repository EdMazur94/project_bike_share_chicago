# How to Turn Casual Riders into Members: A Data Analysis of Chicago’s Bike Sharing System

*This project was developed as part of the Google Data Analytics Certificate program. The goal is to apply data analysis skills to solve a real-world problem.*

## 1. Context

A fictional bike-sharing company operates 24 hours a day in the city of Chicago. The company offers different types of bikes and service plans. To better understand how people use the system, they provided trip data from **April 2024 to April 2025**.

This project aims to generate insights to help the marketing team understand the behavior differences between casual riders and annual members. Based on this, we propose marketing strategies to encourage more casual riders to become members.

## 2. Project Goal

Based on data analysis, the following business questions need to be answered:

- How do annual members and casual riders use the bikes?
- Why would casual riders buy annual memberships?
- How can digital media be used to influence casual riders to become members?

## 3. Dataset

**Source:** https://divvy-tripdata.s3.amazonaws.com/index.html  
**Period analyzed:** April 2024 to April 2025  
**Total records:** 6,150,909 trips  
**Format:** Monthly CSV files  

**Main columns used in this project:**

```
- rideable_type: type of bike used
- started_at: date and time when the trip started
- ended_at: date and time when the trip ended
- start_lat: start latitude
- start_lng: start longitude
- end_lat: end latitude
- end_lng: end longitude
- member_casual: type of user (casual or member)
```

## 4. Methodology

### 4.1 Analytical Approach

Following the process learned in the *Google Data Analytics Certificate*, this project was organized into six steps:

- **Ask:** Understand the questions that need to be answered. Also, bring new questions based on stakeholder needs.
- **Prepare:** Collect the data, explore the structure, and choose the best tool for the analysis.
- **Process:** Clean, transform, and organize the data to ensure quality and consistency.
- **Analyze:** Use SQL queries to explore the data and answer the business questions.
- **Share:** Communicate the results using visualizations and a clear narrative.
- **Act:** Give practical recommendations based on the insights found.

### 4.2 Tools Used

- SQL (PostgreSQL PgAdmin4)  
- Excel  
- Google Sheets  

### 4.3 SQL Queries

All SQL queries used in this analysis are available in this [complementary file](./sql_eng.md)

## 5. Exploratory Analysis & Results

### 5.1 Overview

- Around 63.5% of users are members, while 36.5% are casual riders  
- Average trip time is 12 minutes for members and 24 minutes for casual riders  
- Members usually ride during weekdays and rush hours; casuals ride more on weekends and in the late afternoon  
- The electric bike is the most used model by both groups  
- Seasonality affects both user types  

### 5.2 Behavior Comparison Between Users

- **User distribution by type:**

![image](https://github.com/user-attachments/assets/1c01cf5b-459b-46d6-9619-6668eb9e4a2d)

- **Trip time and bike type:**

![image](https://github.com/user-attachments/assets/3d47641a-c460-4a26-9ef1-e5359fd9be55)

- **Frequent usage times**

![image](https://github.com/user-attachments/assets/69b021bc-058d-4d8b-870a-41da4eb53586)


- **Weekly usage behavior between members and casuals:** 

![image](https://github.com/user-attachments/assets/33464e76-1ec9-442f-a473-b4448075d297)


- **Impact of seasonality on both groups:**

![image](https://github.com/user-attachments/assets/053f7960-f34a-471c-ba08-aa8039a34a00)



## 6. Strategic Recommendations

Based on the results, the following ideas could help convert casual riders into members:

- **Weekend promotions:** Create a *free 3-day plan* or *weekend unlimited ride plans* to let casual users experience the benefits of being a member.
- **Tourist plans:** Offer short-term plans for visitors and tourists.
- **App notifications:** Use in-app messages to show potential savings with a membership plan.
- **Rush hour incentives:** Offer rewards for casual users who ride during peak hours. This may increase regular usage and membership interest.
- **Seasonal strategies:** Bike use drops during colder months. Use challenges, discounts, or point systems to maintain user engagement.

## 7. Analysis Limitations

- **No user profile data:** We don't have data like age, gender, or job. That limits the ability to create personalized campaigns.
- **No travel purpose info:** We don’t know the reason for each trip. Some insights are based on assumptions (like time of day or weekend use).
- **No detailed weather data:** We don’t have accurate data on rain or snow, which can strongly impact usage.

## 8. Conclusion

This analysis helped identify clear behavior patterns between members and casual users.  

Members mostly use the bikes on weekdays and during peak hours, showing they rely on the system for commuting. Casual users ride more on weekends and afternoons, which suggests leisure or tourism.  

These differences show good opportunities for marketing strategies focused on converting casual users into members. Weekend plans, flexible options, and smart messaging in the app can be key actions to increase memberships.

