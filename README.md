# Fantasy Sports Analytics Toolkit

This toolkit is designed for in-depth analysis and visualization of player performances in fantasy sports. It includes a set of Python functions that work with player performance data, enabling users to predict future trends, compare players, and visualize data effectively. Below are detailed descriptions and usage examples for each function:

## 1. `calculate_regression_slope(weekly_stats)`
### Description:
This function calculates the rate of change, or 'slope', in a player's performance over time. It uses a Huber regression model, which is robust to outliers, making it ideal for sports data that might have occasional extreme values.

- **Input**: A Pandas Series containing weekly performance statistics of a player.
- **Output**: A single float value representing the slope of the player's performance trend.

### Example Usage:
```python
import pandas as pd

# Example weekly stats for a player
weekly_stats = pd.Series([10, 12, 14, 15, 18])

# Calculate the performance trend slope
slope = calculate_regression_slope(weekly_stats)
print(f"Slope of performance trend: {slope}")
```

![alt text]([https://github.com/[username]/[reponame]/blob/[branch]/image.jpg?raw=true](https://github.com/Louisvranderick/PffFantasy/blob/main/PFF/Figure_1.png))

## 2. `calculate_expected_points_change(dataframes, position_filter=None, min_expected_points_average=5, rate_of_change_weeks=2)`
### Description:
This function calculates the expected change in a player's points over a specified number of weeks. It can work with multiple dataframes, allowing for a comprehensive and comparative analysis across different time frames.

- **Inputs**: 
  - `dataframes`: A list of Pandas dataframes, each containing player performance data for different weeks.
  - `position_filter`: Optional. Filters players based on their position.
  - `min_expected_points_average`: The minimum average of expected points for including a player in the analysis.
  - `rate_of_change_weeks`: The number of weeks over which the rate of change is calculated.

### Example Usage:
```python
# Assuming 'dataframes' is a list of Pandas dataframes loaded with player data
expected_points_change = calculate_expected_points_change(dataframes)
print(expected_points_change)
```

## 3. `plot_player_regression(merged_df, player_name, point_type='expected', recent_weeks=5)`
### Description:
Generates a plot showing a player's performance trend over a specified number of weeks. It can display either actual or expected fantasy points.

- **Inputs**:
  - `merged_df`: A Pandas dataframe containing merged player data from multiple weeks.
  - `player_name`: The name of the player to plot.
  - `point_type`: Type of points to plot ('expected' or 'actual').
  - `recent_weeks`: The number of recent weeks to include in the plot.

### Example Usage:
```python
# Plot the regression for a player named 'John Doe'
plot_player_regression(merged_df, 'John Doe', point_type='expected', recent_weeks=5)
```

**[Image Placeholder for `plot_player_regression` Function]**

## 4. `plot_player_comparison(merged_df, player1_name, player2_name, point_type='expected', recent_weeks=5)`
### Description:
This function compares the performance of two players side-by-side. It's useful for directly contrasting their performances in terms of either expected or actual fantasy points over a chosen time frame.

- **Inputs**:
  - `merged_df`: A Pandas dataframe containing merged player data from multiple weeks.
  - `player1_name` & `player2_name`: Names of the two players to compare.
  - `point_type`: Type of points to compare ('expected' or 'actual').
  - `recent_weeks`: The number of recent weeks to include in the comparison.

### Example Usage:
```python
# Compare two players: 'Alice' and 'Bob'
plot_player_comparison(merged_df, 'Alice', 'Bob', point_type='expected', recent_weeks=5)
```

**[Image Placeholder for `plot_player_comparison` Function]**

---

This README provides a comprehensive guide to using each function in the toolkit. The example usages show how to apply these functions to actual data, making it easier for users to integrate them into their analysis workflows. Please add the corresponding images in the placeholders to visually demonstrate each function's output.
