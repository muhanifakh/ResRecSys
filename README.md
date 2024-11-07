# ARTIFICIAL INTELLIGENCE CONCEPT  
## Restaurant Recommendation System  

**Arranged by:**  
1. Reino Yuris Kusumanegara / 5025231075  
2. Muhammad Hanif Fakhriansyah / 5025231082  
3. Muhammad Rizqy Hidayat / 5025231161  
4. Fazle Robby Pratama / 5025231011  

[Github repository link]

---

### Introduction

In today's fast-paced world, deciding where to eat can often be a time-consuming process. Whether it's choosing between different types of cuisine, balancing budget constraints, or finding a location that's convenient for everyone, the challenge of picking a restaurant that satisfies all criteria can become overwhelming. To address this issue, we propose a Restaurant Recommendation System that utilizes advanced search algorithms to provide personalized, optimal restaurant suggestions based on user preferences, location, and other key factors. By leveraging methods such as informed search, local search, and constraint satisfaction, this system aims to simplify the decision-making process, delivering recommendations that are both efficient and tailored to individual or group needs.

---

### Background and Problem Statement

When individuals or groups plan to eat out, there will always be debates in choosing where they want to eat due to the varying preferences of each individual. They must also consider constraints such as budget, approximate cost, travel distance, operational hours, and more. The abundance of restaurant options combined with limited time and varying preferences creates this problem.

Hence, we developed a Restaurant Recommendation System to assist people who are undecided and want to choose a restaurant based on their preferences quickly. The system uses search methodologies, such as Uninformed and Informed search.

Generally, when an individual or group wants to eat out, they often face difficulty choosing a restaurant that matches their preferences, budget, and location. This problem becomes more complex when there are multiple people with different preferences, such as:

- Available budget  
- Restaurant location  
- Ratings or reviews from previous customers  

This recommendation system aims to solve this problem by offering restaurant options that meet the preferences of multiple users in a single search.

---

### Uniqueness

1. **Distance and Time Efficiency**  
   By leveraging search algorithms like A* search, the system can prioritize nearby restaurants that minimize travel time, which is crucial for users with limited time, such as lunch breaks. It ensures that the recommendation not only fits the food preferences but also accounts for time efficiency.

2. **Quick Decision-making**  
   This recommendation system uses a combination of uninformed, informed, and local search algorithms to find optimal solutions. Algorithms like A* help find the best routes to nearby restaurants and can be used to refine restaurant choices based on the users' preferences, adjusting for cost, location, and group size. By using multiple algorithms, the system ensures both speed and accuracy in producing recommendations.

3. **Multiple User Preferences**  
   When several people are involved, each with their own food preferences, budget, and location, the system can combine and balance these multiple preferences to provide a recommendation that satisfies the majority of users. This is particularly useful for situations like family outings, group lunches, or meetings where diverse preferences must be considered. Individuals can also benefit from this system, making it adaptable for both single users and groups.


# Methodology

In this project, we implement a restaurant recommendation system using two popular search algorithms:

- **A-Star (A*) Search**
- **Breadth-First Search (BFS)**

The purpose is to recommend restaurants based on user-defined criteria, including distance, rating, and budget. We also provide visualizations of the routes and restaurants on an interactive map to enhance user experience and understanding.

### Objectives

The key objectives of our methodology are:

1. **Algorithmic Prioritization Based on User Input**
   - A* Search prioritizes **rating** and **budget** while also considering **distance**.
   - BFS prioritizes **distance only**, providing the closest restaurants without filtering by rating or budget.

2. **Performance Comparison in Terms of Execution Time**
   - We measure the execution time of A* and BFS to analyze the trade-offs between accuracy (in terms of rating and budget) and speed.

3. **Route Visualization on Interactive Map**
   - Using **Folium** and the **OSRM API**, we visualize the user's location, restaurants, and selected routes on an interactive map.

---

## 1. Algorithmic Prioritization Based on User Input

We use two search algorithms to prioritize different aspects of the user’s preferences:

- **A* Search**: This algorithm uses both rating and budget filters, in addition to distance, to recommend restaurants. It calculates the heuristic based on rating (penalizing restaurants below the preferred rating) and filters out restaurants that exceed the user-defined budget.
  
  - **Heuristic Calculation**: The A* search calculates a heuristic score based on the difference between each restaurant's rating and the user’s preferred rating, prioritizing restaurants that meet or exceed the preferred rating.
  - **Distance and Budget Filtering**: It excludes any restaurant beyond the maximum distance or above the specified budget.

- **BFS Search**: This algorithm focuses only on finding the closest restaurants to the user’s location, without filtering for rating or budget.
  
  - **Distance Sorting**: Restaurants are sorted by proximity to the user’s location, and BFS stops after finding five restaurants within the maximum distance threshold.

  ![Screenshot 2024-11-07 205305](https://github.com/user-attachments/assets/eabff204-a5b0-4080-a8d9-7b5a1c5584d1)
  ![Screenshot 2024-11-07 205401](https://github.com/user-attachments/assets/2bab137f-e7ab-4157-aea7-a186f35af3ad)


The difference in these approaches allows us to cater to both general proximity-based recommendations (using BFS) and refined, preference-driven recommendations (using A*).

---

## 2. Search Execution Time Comparison

To understand the efficiency of each algorithm, we measure the execution time for both A* and BFS during each search:

- **A* Search Execution Time**: This measures the time taken to find restaurants that meet rating, budget, and distance criteria. Each restaurant’s search time is recorded, allowing us to analyze the computational cost of adding rating and budget filters to distance-based searches.

- **BFS Execution Time**: This measures the time taken to find the five closest restaurants without considering rating or budget constraints. Since BFS only considers distance, it generally performs faster, which makes it a suitable choice for users seeking quick recommendations based solely on proximity.

The collected data allows us to compare A* and BFS performance, particularly when users prioritize specific restaurant qualities (e.g., rating and budget) versus proximity.

---

## 3. Route Visualization on Interactive Map

To help users visualize their recommended restaurants and routes, we use **Folium** for interactive mapping and the **OSRM API** to draw driving routes:

- **User Location**: Displayed as a blue marker to represent the starting point.
- **Restaurant Locations**: Displayed as markers with color coding:
  - **Green** for restaurants with a rating of 4.5 or above.
  - **Red** for restaurants with a rating below 4.5.
- **Routes**: Using the OSRM API, we display driving routes from the user’s location to each recommended restaurant, giving users a clear view of the travel paths.

This visualization provides users with a comprehensive map of their options, allowing them to better understand the spatial relationships between their location and recommended restaurants.
![Screenshot 2024-11-07 205540](https://github.com/user-attachments/assets/1eb2449e-b9af-45c8-abbd-de7666b6a1ae)

---

![Map Visualization Example](path/to/map_visualization_image.png)

This methodology allows us to deliver a balanced restaurant recommendation system with both simple (BFS) and preference-sensitive (A*) algorithms, enhancing the usability and efficiency of the recommendation process.

---

