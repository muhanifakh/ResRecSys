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

