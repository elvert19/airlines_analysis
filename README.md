
#  Airline Flight Price Analysis with Python

This project explores and analyzes a dataset of airline flights in India, focusing on ticket pricing, airline performance, route patterns, and travel trends.

##  Dataset

The dataset includes the following key columns:
- `airline`: Name of the airline
- `flight`: Flight identifier
- `source_city`: Departure city
- `departure_time`: Time of departure
- `stops`: Number of stops
- `arrival_time`: Time of arrival
- `destination_city`: Arrival city
- `class`: Flight class (Economy or Business)
- `duration`: Total flight time
- `days_left`: Days left until the flight date
- `price`: Ticket price

 Cities Covered: Delhi, Mumbai, Bangalore, Kolkata, Hyderabad, Chennai

---

## 🛠 Features & Analysis

### ✅ Descriptive Analysis
- Count of flights per airline, class, city
- Most common source and destination cities
- Flight class distribution

###  Duration Insights
- Comparison of average flight duration per airline
- Shortest vs longest average flight times

###  Price Insights
- Average price by airline
- Price distribution across flight classes
- Cheapest and most expensive routes
- Effect of `days_left` on ticket pricing
- Airline + class combo that offers the best value

###  Visualizations
- Bar plots for average prices, routes, and class distribution
- Line plots showing price variation over days
- Pie chart of most used airlines
- Interactive input: Search for flights between two cities

---

## 🧪 Sample Code Snippets

```python
# Cheapest flight routes
df['route'] = df['source_city'] + ' → ' + df['destination_city']
cheapest_routes = df.groupby('route')['price'].mean().sort_values().head(10)

# Visualize
sns.barplot(x=cheapest_routes.values, y=cheapest_routes.index)
plt.title('Top 10 Cheapest Routes')
