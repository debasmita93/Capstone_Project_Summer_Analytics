# Capstone_Project_Summer_Analytics (Dynamic Pricing for Urban Parking Lots)
This is a final capstone project of Summer Analytics by Consulting & Analytics Club, IIT Guwahati. The project titled, "Dynamic Pricing for Urban Parking Lots" by Debasmita Saha. 

Overview:
Urban parking spaces are scarce and valuable assets. Static pricing often leads to underutilization or overcrowding. This project implements a **real-time, dynamic pricing system** for 14 parking lots using basic economic logic, real-time data simulation with Pathway, and visual feedback through Bokeh.
The system updates prices based on:
- Real-time demand indicators (occupancy, queue length, traffic)
- Event-based conditions (holidays, congestion)
- Vehicle types
- Competitor pricing (spatial intelligence)

Techonologies Used:
 - Python
 - Pandas
 - Pathway
 - Bokeh

Architecture and Workflow of the project:

1. Data Ingestion: Simulated historical-parking data (73 days, 14 lots) is streamed in real-time using Pathway. Each record contains parking lot status, vehicle type, environmental conditions, and timestamps.
2. Feature Engineering: Calculate occupancy ratio, queue length, traffic congestion weight, and special-day impact. Normalize all demand-affecting features for stability and bounded pricing.
3. Pricing Models: We implemented 3 models with increasing intelligence:
- Model 1 (Linear Occupancy): Basic linear price increase with occupancy rate.
- Model 2 (Demand Function): Multi-feature demand function (queue, traffic, vehicle type).
- Model 3 (Competitive Pricing): Adds spatial competition using Haversine distance and neighbor pricing comparison.
4. Real-Time Integration with Pathway: **apply_model()** injects pricing logic into the Pathway stream. Pathway maintains time-ordering and simulates real-time flow and reactions to parking state.
5. Live Visualization with Bokeh: Displays real-time price movement for each parking lot. Shows competitor prices for reference. Enables interactive analysis of pricing behavior under varying demand patterns.

