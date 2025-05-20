import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import folium
from folium.plugins import MarkerCluster
from IPython.display import display

# Define city zones with coordinates
zones = {
    "Central Park": (40.785091, -73.968285),
    "Tech District": (40.748817, -73.985428),
    "Industrial Zone": (40.730610, -73.935242),
    "Residential Area": (40.729515, -73.998672),
    "Harbor District": (40.700292, -74.015974)
}

# Simulate performance metrics for each zone
data = []
for zone, coords in zones.items():
    aqi = np.random.randint(40, 200)
    traffic = np.random.randint(100, 1200)
    noise = round(np.random.uniform(40, 100), 2)
    temp = round(np.random.uniform(15, 40), 2)
    humidity = round(np.random.uniform(30, 80), 2)

    alert = []
    if aqi > 150: 
        alert.append("High AQI")
    if traffic > 1000: 
        alert.append("Traffic Congestion")
    if noise > 85: 
        alert.append("High Noise")

    data.append({
        "Zone": zone,
        "Latitude": coords[0],
        "Longitude": coords[1],
        "AQI": aqi,
        "Traffic": traffic,
        "Noise": noise,
        "Temperature (C)": temp,
        "Humidity (%)": humidity,
        "Alert": ", ".join(alert) if alert else "Normal"
    })

# Create DataFrame and display
urban_df = pd.DataFrame(data)
display(urban_df)

# Save to CSV
urban_df.to_csv("final_urban_planning_data.csv", index=False)

# Plot metrics
plt.figure(figsize=(10,5))
plt.plot(urban_df["Zone"], urban_df["AQI"], label="AQI", marker="o")
plt.plot(urban_df["Zone"], urban_df["Traffic"], label="Traffic", marker="s")
plt.plot(urban_df["Zone"], urban_df["Noise"], label="Noise", marker="^")
plt.title("Urban Performance Metrics by Zone")
plt.ylabel("Value")
plt.grid(True)
plt.legend()
plt.tight_layout()
plt.show()
