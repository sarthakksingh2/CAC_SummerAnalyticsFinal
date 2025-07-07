# CAC_SummerAnalyticsFinal

## 🧠 Overview

Urban parking spaces are limited and highly dynamic. Static pricing often leads to **overcrowding** or **underutilization**.

This project builds a **real-time dynamic pricing engine** for 14 parking lots using:
- Real-world variables (occupancy, queue, traffic, vehicle type, etc.)
- A layered model architecture (baseline → demand-based → competition-aware)
- Real-time data processing using **Pathway**
- Interactive visualizations using **Bokeh**

- ## 🧰 Tech Stack

Python 3, NumPy, Pandas, Pathway, Git, GitHub, Google Colab, Bokeh


## 🔄 Workflow
➤ Step 1: Data Ingestion
Data is loaded via CSV or streamed using Pathway

14 parking lots x 73 days x 18 slots per day (8:00 AM – 4:30 PM)

➤ Step 2: Feature Engineering
We extract features like:

occupancy_rate = occupancy / capacity

norm_traffic, queue_length, special_day, vehicle_type_weight

➤ Step 3: Model Pipeline
Model	Description
Model 1	Price increases linearly with occupancy
Model 2	Price derived from demand function of multiple features
Model 3	Competitor pricing adjustments using geo-distance

➤ Step 4: Real-Time Visualization
Interactive line plots using Bokeh

Plots include:

Per-lot price curves over time

Competitor price comparisons


![Screenshot 2025-07-07 234142](https://github.com/user-attachments/assets/d926103a-5c66-4e4c-a708-912153b27ece)

## 🏗️ Architecture Diagram 

```mermaid
graph TD
  A[CSV / Real-Time Input Data] --> B[Pathway Stream]
  B --> C[Feature Engineering]
  C --> D1[Model 1: Occupancy-Based]
  C --> D2[Model 2: Demand-Based]
  C --> D3[Model 3: Competition-Aware]
  D1 --> E[Price Output]
  D2 --> E
  D3 --> E
  E --> F[Bokeh Dashboard]

