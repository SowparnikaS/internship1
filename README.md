# Weather Data Visualization using OpenWeatherMap API

This project is submitted as part of Task - 1 for the internship with CodTech. It demonstrates API integration and data visualization using Python.

## Objective
- Fetch weather data from a public API (OpenWeatherMap)
- Process and visualize the data using Matplotlib and Seaborn
- Create a clear and informative weather dashboard

## Features
- Fetches live weather data for multiple cities
- Visualizes:
  - Temperature (°C)
  - Humidity (%)
- Displays data in both tabular and graphical format

## Tech Stack
- Python
- [OpenWeatherMap API](https://openweathermap.org/api)
- Requests
- Pandas
- Seaborn
- Matplotlib

## How to Run
1. Python script :

- import requests
- import pandas as pd
- import seaborn as sns
- import matplotlib.pyplot as plt
- API_KEY = "                "
- cities = ["London", "New York", "Tokyo", "Paris", "Mumbai"]
- weather_data = []
- for city in cities:
-    url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={API_KEY}&units=metric"
-    response = requests.get(url)
-    if response.status_code == 200:
-        data = response.json()
-        weather_data.append({
-            "City": city,
-            "Temperature (°C)": data["main"]["temp"],
-            "Humidity (%)": data["main"]["humidity"],
-            "Weather": data["weather"][0]["description"].title()
-        })
-    else:
-        print(f"Failed to get data for {city}")
- df = pd.DataFrame(weather_data)
- print(df)
- plt.figure(figsize=(10, 6))
- sns.barplot(x="City", y="Temperature (°C)", data=df)
- plt.title("City-wise Temperature")
- plt.figure(figsize=(10, 6))
- sns.barplot(x="City", y="Humidity (%)", data=df)
- plt.title("City-wise Humidity")
- plt.show()

2. Install the required libraries: (in command prompt) --> pip install requests pandas matplotlib seaborn
    
3. Get your free API key from [OpenWeatherMap](https://openweathermap.org/api)

4. Replace the placeholder in the code:
    API_KEY = "your_api_key_here"
    
5. Run the script:
    python weather_visualizer.py
   
## Sample Output

- Console output: Tabular weather data for selected cities
- Graph 1: Bar plot of Temperature (°C)
- Graph 2: Bar plot of Humidity (%)

## Deliverables
- weather_visualizer.py – Complete Python script
- README.md – Documentation file

## Author
Sowparnika S 
(Intern at CodTech)
