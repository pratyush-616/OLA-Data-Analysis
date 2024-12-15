
# OLA Data Analysis

### Dashboard Link : https://app.powerbi.com/view?r=eyJrIjoiMDUxMmY3ZWYtMjQ0NC00MDkyLWI4ZjctMmU2ZGVkYzBmNjc5IiwidCI6ImJhZDEyODY0LTkxM2UtNGI5OS04N2Q2LWI4ZDJhZDQ1OWUyNyIsImMiOjEwfQ%3D%3D

## Problem Statement


In a highly competitive ride-hailing industry, Ola Cabs faces challenges in optimizing its operations, enhancing customer satisfaction, and maintaining a competitive edge. The company has a large volume of data, including trip details, customer feedback, driver performance, and operational costs, but this data has not been fully leveraged for strategic decision-making.

The primary problem is identifying actionable insights from Ola Cabs' data to address the following key questions:

- Overall Operations: This analysis will help understand trends in demand and operational efficiency by evaluating ride volumes over time and identifying patterns in booking statuses. This can provide insights into periods of high demand, cancellations, or operational bottlenecks.
- Vehicle Type Analysis : Analyzing the most popular vehicle types used for longer distances can guide fleet management and marketing efforts. Understanding customer preferences for specific vehicle types can also help optimize fleet composition.
- Revenue Insights: These insights focus on understanding revenue streams, customer segmentation, and ride patterns. Identifying preferred payment methods and high-value customers can shape customer retention strategies, while ride distance data can guide pricing and operational policies.
- Cancellation Analysis: Understanding why rides are canceled from both customer and driver perspectives is crucial for reducing cancellation rates. Insights from this analysis can help implement targeted measures, such as better communication, improved service reliability, or incentivizing driver acceptance.
- Ratings and Feedback: Customer and driver ratings can provide valuable feedback on the quality of service and user experience. Analyzing rating trends can uncover areas needing improvement, such as driver training or customer behavior management.

The goal of this project is to analyze Ola Cabs' data to uncover patterns, trends, and anomalies that can help improve customer experience, streamline operations, and increase profitability. This analysis will involve using data visualization, predictive modeling, and statistical analysis techniques to deliver actionable insights for decision-making.


## Data Breakdown

### 1. Date and Time Information
- **Fields**:
  - `Date`
  - `Time`
- **Purpose**:  
  To analyze ride patterns, peak hours, and seasonal trends.



### 2. Booking Details
- **Fields**:
  - `Booking ID`
  - `Booking Status`
  - `Customer ID`
- **Purpose**:  
  To track individual rides, assess booking success rates, and understand customer engagement.



### 3. Vehicle Details
- **Fields**:
  - `Vehicle Type` (e.g., Auto, Prime Plus, Prime Sedan, Mini, Bike, eBike, Prime SUV)
- **Purpose**:  
  To evaluate the popularity and usage patterns of various vehicle types across different rides.



### 4. Location Data
- **Fields**:
  - `Pickup Location` (50 dummy locations from Bangalore)
  - `Drop Location`
- **Purpose**:  
  To analyze ride demand based on geographic areas and optimize route planning.



### 5. Ride Metrics
- **Fields**:
  - `Average Wait Time` (time taken for the vehicle to arrive at the pickup location)
  - `Average Customer Arrival Time` (time taken for the customer to reach the vehicle)
- **Purpose**:  
  To measure service efficiency and identify areas to minimize delays.



### 6. Cancellation Data
- **Fields**:
  - **Canceled Rides by Customer**
    - Reasons:
      - Driver not moving towards pickup location
      - Customer asked to cancel
      - AC not working (for 4-wheelers only)
      - Change of plans
      - Wrong address
  - **Canceled Rides by Driver**
    - Reasons:
      - Personal and car-related issues
      - Customer-related issues
      - Customer was coughing/sick
      - More than permitted passengers in the vehicle
- **Purpose**:  
  To analyze cancellation trends and understand the key reasons behind them for both customers and drivers.



### 7. Incomplete Rides
- **Fields**:
  - `Incomplete Rides`
  - `Incomplete Rides Reason` (e.g., customer demand, vehicle breakdown, other issues)
- **Purpose**:  
  To identify and address factors causing incomplete rides.



### 8. Revenue and Booking Metrics
- **Fields**:
  - `Booking Value`
  - `Ride Distance`
- **Purpose**:  
  To assess financial performance and customer spending patterns.



### 9. Ratings and Feedback
- **Fields**:
  - `Driver Ratings`
  - `Customer Ratings`
- **Purpose**:  
  To evaluate the quality of service from both the customer and driver perspectives.
---


## Objectives and steps used in SQL querying
The dataset in use was converted into a MySql database and using querying statements, the following objectives were analysed by creating seperate view tables in the system for simplicity. All the extracted view tables were then extracted as csv files and formatted in python to be displayed.

### Objective 1: Analyze Booking Success and Ride Trends
- **Tasks Performed**:
   
   **Retrieve all successful bookings**:  
     Query the database to filter rides where the booking status indicates a successful completion.
  
  **Find the average ride distance for each vehicle type**:  
     Calculate the average distance traveled for each vehicle type to understand usage patterns.

### Objective 2: Cancellation Analysis
- **Tasks Performed**:
 
 **Get the total number of canceled rides by customers**:  
     Aggregate and count cancellations initiated by customers to identify key trends.

   **Get the number of rides canceled by drivers due to personal and car-related issues**:  
     Filter and count driver-initiated cancellations with specific reasons.



### Objective 3: Customer Insights and Segmentation
- **Tasks Performed**:
  
  **List the top 5 customers who booked the highest number of rides**:  
     Identify high-frequency customers to analyze loyalty or high-demand users.


### Objective 4: Driver and Vehicle Ratings
- **Tasks Performed**:
  
  **Find the maximum and minimum driver ratings for Prime Sedan bookings**:  
     Extract rating details specific to Prime Sedan rides to evaluate service quality.
  
  **Find the average customer rating per vehicle type**:  
     Compute the average customer ratings for each vehicle type to assess overall satisfaction.


### Objective 5: Payment Analysis
- **Tasks Performed**:
  
   **Retrieve all rides where payment was made using UPI**:  
     Filter rides based on the payment method to understand payment preferences.


### Objective 6: Revenue and Financial Analysis
- **Tasks Performed**:
  
  **Calculate the total booking value of rides completed successfully**:  
     Sum up the booking values of all successfully completed rides to evaluate revenue performance.


### Objective 7: Incomplete Ride Analysis
- **Tasks Performed**:
  
  **List all incomplete rides along with the reason**:  
      Query the database to retrieve all rides marked as incomplete, including associated reasons for better insights.


 
 
# Power BI Questions and Analysis Objectives



### 1. Ride Volume Over Time
- **Objective**:  
  Analyze the total number of rides across different time periods (daily, weekly, monthly) to identify demand patterns and peak periods.


### 2. Booking Status Breakdown
- **Objective**:  
  Visualize the distribution of booking statuses (e.g., completed, canceled, in-progress) to assess operational efficiency and highlight areas for improvement.


### 3. Top 5 Vehicle Types by Ride Distance
- **Objective**:  
  Identify the vehicle types with the highest ride distances to understand customer preferences and optimize fleet allocation.


### 4. Average Customer Ratings by Vehicle Type
- **Objective**:  
  Compare average customer ratings across different vehicle types to evaluate service quality and customer satisfaction.


### 5. Cancelled Rides Reasons
- **Objective**:  
  Break down the reasons for ride cancellations by both customers and drivers to identify common issues and reduce cancellation rates.


### 6. Revenue by Payment Method
- **Objective**:  
  Visualize the revenue contribution of various payment methods (e.g., UPI, credit cards, cash) to understand customer preferences and streamline payment options.


### 7. Top 5 Customers by Total Booking Value
- **Objective**:  
  Identify the top 5 high-value customers based on total bookings to focus on customer retention strategies and personalized offerings.

### 8. Ride Distance Distribution Per Day
- **Objective**:  
  Analyze the distribution of ride distances on a daily basis to detect patterns in short vs. long-distance rides and optimize pricing strategies.


### 9. Driver Ratings Distribution
- **Objective**:  
  Visualize the distribution of driver ratings to evaluate driver performance and identify areas for improvement or rewards.


### 10. Customer vs. Driver Ratings
- **Objective**:  
  Compare customer and driver ratings to understand the overall service experience and identify discrepancies or areas needing attention.


# Dataset used
[BookingsCSV.csv](https://github.com/user-attachments/files/18140638/BookingsCSV.csv)
