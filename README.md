# Swiggy Case Study Using SQL

## Project Overview
This project involves analyzing Swiggy's restaurant dataset to extract meaningful insights. Various SQL queries have been utilized to answer business-related questions, ranging from identifying highly-rated restaurants to finding the most expensive cities for dining. The analysis includes data cleaning, aggregation, and advanced SQL techniques to address the objectives effectively.

## Objectives
1. **How many restaurants have a rating greater than 4.5?**
2. **Which city has the highest number of restaurants?**
3. **How many restaurants have "Pizza" in their name?**
4. **What is the most common cuisine among the restaurants?**
5. **What is the average rating of restaurants in each city?**
6. **What is the highest price of an item under the 'Recommended' menu category for each restaurant?**
7. **Find the top 5 most expensive restaurants that offer cuisine other than Indian.**
8. **Identify restaurants with an average cost higher than the total average cost.**
9. **Retrieve details of restaurants with the same name but located in different cities.**
10. **Which restaurant offers the most items in the 'Main Course' category?**
11. **List names of 100% vegetarian restaurants in alphabetical order.**
12. **Which restaurant provides the lowest average price for all items?**
13. **Identify the top 5 restaurants offering the highest number of categories.**
14. **Which restaurant provides the highest percentage of non-vegetarian food?**
15. **Determine the most and least expensive cities for dining.**
16. **Calculate the rating rank for each restaurant within its city.**

## Dataset
The dataset used is structured with columns such as:
- `restaurant_name`
- `city`
- `rating`
- `cost_per_person`
- `cuisine`
- `menu_category`
- `item`
- `veg_or_nonveg`
- `price`

## SQL Queries
The SQL queries used for each objective are written in detail. Below are some key highlights:

- **Query to find high-rated restaurants:**
  ```sql
  SELECT COUNT(DISTINCT restaurant_name) AS high_rated_restaurants
  FROM swiggy
  WHERE rating > 4.5;
  ```

- **Query to find the city with the highest number of restaurants:**
  ```sql
  SELECT city, COUNT(DISTINCT restaurant_name) AS restaurant_count
  FROM swiggy
  GROUP BY city
  ORDER BY restaurant_count DESC
  LIMIT 1;
  ```

- **Query to find restaurants with "Pizza" in their name:**
  ```sql
  SELECT COUNT(DISTINCT restaurant_name) AS pizza_restaurants
  FROM swiggy
  WHERE restaurant_name LIKE '%pizza%';
  ```

- **Query for most common cuisine:**
  ```sql
  SELECT cuisine, COUNT(*) AS cuisine_count
  FROM swiggy
  GROUP BY cuisine
  ORDER BY cuisine_count DESC
  LIMIT 1;
  ```

- **Query to calculate average rating by city:**
  ```sql
  SELECT city, AVG(rating) AS average_rating
  FROM swiggy
  GROUP BY city;
  ```

## Tools and Techniques
- **SQL:** Core tool used for querying and analysis.
- **Techniques:** Data filtering, aggregation, joins, window functions, and ranking.

## Outcomes
- Identified top-rated restaurants and cities with the most dining options.
- Determined the most popular cuisines and cost-effective options.
- Extracted insights on vegetarian and non-vegetarian food trends.

## How to Use
1. Load the `swiggy` dataset into a database.
2. Run the SQL queries provided for each objective.
3. Review the results to gain actionable insights.

## Future Scope
- Integrate with visualization tools like Power BI or Tableau for dynamic dashboards.
- Automate analysis with Python for real-time updates.
- Explore machine learning models for predictive analytics, such as rating prediction or cost optimization.
