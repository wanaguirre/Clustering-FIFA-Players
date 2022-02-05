This repository is just to show and teach some of Unsupervised ML methods used to solve Clustering problems.

# Clustering-FIFA-Players

In this repository I compare the actual preferred position of the players with the most suitable one based on the characterisics of ech player.

This clustering application is made through the **K-means algorithm**, with the help of the **Elbow and Silhouette methods**.

Also implementing techniques to visualize in a properly way the decitions taken like, scaterplots, histograms, heatmaps or the Sankey diagram.

---

### Background:

The data set was scraped from [this website](https://sofifa.com/). It give us the main attributes of different FIFA players, and also their most common positions.


### Task:

Based on these characteristics we are going to predict which is their ideal position, and then check if the predicted one correspond with the actual one.


### Feature Descriptions:

For non-football enthusiasts, you can check out Wiki website for more clarification about football player's positions. [Find type and meaning of positions here](https://en.wikipedia.org/wiki/Association_football_positions).

- id
- acceleration
- aggression
- agility
- balance
- ball_control
- composure
- crossing
- curve
- dribbling
- finishing free_kick_accuracy
- gk_diving
- gk_handling
- gk_kicking
- gk_positioning
- gk_reflexes
- heading_accuracy
- interceptions
- jumping
- long_passing
- long_shots
- marking',penalties
- positioning
- reactions
- short_passing
- shot_power
- sliding_tackle
- sprint_speed
- stamina
- standing_tackle
- strength
- vision
- volleys

---
### Methodology

  - **Data Understanding and preprocessing:** 
    - Check the type of values of each column and shape of the DataFrame
    - Check if any id is duplicated along the df, thanks to the "id" feature
    - Check if the df has NaN values and rows with missing values
    - Handle the problem wih the values of some columns (applying eval() mehod)
    - Drop irrelevant features
    - Data visualization: Correlation Heatmap, Histograms and Box plots to check all the features (Distributions and Outliers)
  
<p align="center">
<image src="Notebook/images/1.jpg"/>
</p>

    
  - **Unsuperviced Machine Learning, K-Means Algorithm:**
    - Create a pipeline to scale the data and apply the K-Means method.
    - Finding the optimal number of clusters: 
      - Elbow Method
      - Silhouette Method
      - Scatter plot with our 4 clusters selected
    - Compare and evaluate our results: Sankey Diagram



#### Elbow Method

<p align="center">
<image src="Notebook/images/2.png"/>
</p>

#### Silhouette Method

<p align="center">
<image src="Notebook/images/3.png"/>
</p>

#### Scatter plot with our 4 clusters selected

<p align="center">
<image src="Notebook/images/4.png"/>
</p>

#### Sankey Diagram

<p align="center">
<image src="Notebook/images/5.png"/>
</p>

### Results

**4 clusters seem to describe GK, Defenders, Mid-Fielders and Attackers:**

0 --> Defenders [CB,RB,LB]

1 --> Goal Keepers [GK]

2 --> Mid-Fielders [CDM,CM,LM,RM]

3 --> Attackers [ST,CAM,LW,RW,CF]

The Goal Keepers cluster seems to be well defined. But there seems to be a bit of an overlap between the other 3 which may have occurred due to us selecting only the first preferred position of a player.
