# Logistics & Transportation- Fleet Performance & Delivery Efficiency

Problem Statement:
To analyze fleet performance of logistics company in terms of on-time deliveries, fuel efficiency, and cost per mile.

Dataset: Logistic Dataset Link

Data Preparation
Data cleaning and modeling is done using Excel and Power BI

key activities included : 
- VLOOKUP function is used to relate "vehicle master" data with "trip data"
syntax =VLOOKUP([@[Vehicle_ID]],vehicle_master,2,FALSE)
- calculated columns and measures were created
- average fuel consumption of each vehicle type is calculated using "group by" in PowerBI

DAX measures
1- On-Time Trips 
on time trips = CALCULATE(COUNTA(trip_data1[Delivery_Status]),trip_data1[Delivery_Status]="on-time")
2- Total Trips
total trips = DISTINCTCOUNT(trip_data1[Trip_id])
3- On-Time Delivery %
On-Time Delivery % = divide(trip_data1[on time trips],trip_data1[total trips])

DAX columns
1- Fuel Efficiency
Fuel Efficiency = DIVIDE(trip_data1[Distance_km],trip_data1[Fuel_Consumed_L])
2- Fuel Cost
fuel cost = trip_data1[Fuel_Consumed_L]*95
3- Cost per km 
Cost per km = (trip_data1[fuel cost] + trip_data1[maintanence_cost]) / trip_data1[Distance_km]
4- Route
route = trip_data1[Origin]&" - "&trip_data1[Destination]
5- Month
month = format(trip_data1[Delivery_Date],"mmmm")

DASHBOARD
	Bar chart: On-Time Delivery % by Route.
	Line chart: Fuel Efficiency trend by month.
  KPI cards: On-Time Delivery % , Cost per km.
	Map visual: Delivery performance by route (Origin → Destination).

SLICERS
- Origin
- Destination
- Vehicle Type
- Month






