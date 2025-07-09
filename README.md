# Capstone
In this Capstone Project, I have created two different models for dynamic pricing


















# Model -2

# Step 1-- Data Preprocessing
  #Creating array of dataframes which contains data for all 14 different locations
  #Encoding the columns like 'VehiceType' and 'TrafficConditionNearby' into integer form using mapping dictionary
  #Creating a new column named 'Demand' -- which is linear function of columns like 'Occupancy','Capacity','QueueLength','TrafficConditionNearby','IsSpecialDay' and 'VehicleType'

# Step 2-- Creating Schema and making CSV files(which will be used for streaming)
  #Here the schema has two feautures named Timestamp and Demand
  #For each Lot ,a csv file is created(which will be later used for stream)

# Step 3-- Creating a demo replay data of each lot
  #data_locations is created from each CSV file
  #then columns like like 't'(for timestamp) , 'day_dt'(Date at Midnight)

# Step 4-- Creating a delta window
  #First daily_stats window is created for computing max_demand and min_demand for a day(for each location)
  #Then finally delta_window_locations is created which uses daily_stats to compute dynamic pricing

# Step 5-- Creating price_plotter and running the stream
  #Creating a price_plotter which plots graph for dynamic pricing for each parking-lot
  #Pushing all the graph in dashboard
  #Finally running the stream using pw.run()
