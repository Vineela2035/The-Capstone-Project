# The-Capstone-Project
# 🚗 Dynamic Urban Parking Pricing with Real-Time Simulation

## 📌 Project Overview

This project simulates real-time dynamic pricing for urban parking spaces based on:
- Occupancy rate
- Traffic conditions
- Special events
- Vehicle types
- Geo-location competitiveness

Real-time data simulation is visualized using **Bokeh + Panel**, displaying daily pricing variations across three models.


---

## 📌 Tech Stack

| Technology         | Purpose                                    |
|--------------------|--------------------------------------------|
| Python             | Core programming language                  |
| Pandas             | Data loading, transformation & analysis    |
| Scikit-learn       | Label Encoding, Clustering, Normalization  |
| Bokeh              | Interactive time-series visualization      |
| Panel              | App layout and real-time UI                |
| Threading (Python) | Simulated real-time streaming              |

---

## 🧠 Features

- ✅ Model 1: **Linear Pricing** — Price based directly on occupancy rate.
- ✅ Model 2: **Demand-Based Pricing** — Adjusted using weighted demand metrics like traffic, queue length, and vehicle type.
- ✅ Model 3: **Competitive Pricing** — Incorporates local price clustering via K-Means and adjusts price based on market conditions.
- ✅ Real-time simulation of dynamic pricing per day.
- ✅ Interactive Bokeh visualization embedded using Panel.

---

## 🏗️ Architecture Flow

This is a step-by-step logical flow of how your dynamic parking pricing simulation system works:

Dataset Loading
→ Load the urban parking data (Modified - modified.csv) with occupancy, capacity, timestamp, traffic, queue length, etc.

Preprocessing
→ Combine date and time into a single timestamp.
→ Encode categorical variables (like vehicle type and traffic condition).
→ Compute derived features like OccupancyRate.

Model-Based Pricing Computation

Model 1: Linear Pricing
→ Simple pricing based on occupancy rate.

Model 2: Demand-Based Pricing
→ Uses weighted demand factors (occupancy, queue length, traffic, vehicle type, special day).

Model 3: Competitive Pricing
→ Clusters data by location using KMeans, and adjusts price based on cluster behavior.

Simulated Real-Time Streaming
→ Group by date and compute daily average prices for each model.
→ Stream prices one day at a time using Python threading.

Visualization using Bokeh + Panel
→ Real-time interactive Bokeh plot shows model prices over time.
→ Panel serves the dashboard as a live web app.

## 🖼️ Architecture Diagram

        ┌──────────────────────┐
        │  Parking CSV Data    │
        └────────┬─────────────┘
                 ↓
       ┌──────────────────────┐
       │    Data Preprocessing│
       └────────┬─────────────┘
                ↓
  ┌─────────────┼──────────────────────────────┐
  
  ↓             ↓                              ↓
Model 1     Model 2                        Model 3
(Linear)    (Demand-Based)                (Cluster-Based)
  ↓             ↓                              ↓
  
  └─────────────┴──────────────┬───────────────┘
  
                               ↓
                               
                  ┌────────────────────────────┐
                  │   Daily Price Aggregation  │
                  └────────────┬───────────────┘
                               ↓
                               
               ┌───────────────────────────────┐
               │ Real-Time Streaming (Thread)  │
               └────────────┬──────────────────┘
                            ↓
                            
        ┌────────────────────────────┐
        │ Bokeh + Panel Visualization│
        └────────────────────────────┘


## 📋 Report :

You can view the full report here: [📄 report.pdf]

The report includes the following:

1. **Problem Statement**
2. **Project Overview**
3. **Technologies & Libraries Used**
4. **Feature Engineering**
5. **Pricing Models Explained**
6. **Pathway Streaming Pipeline**
7. **Real-Time Dashboard**
8. **Scalability Discussion**
9. **Limitations & Future Work**
