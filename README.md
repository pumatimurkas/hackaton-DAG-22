Background: We operate an online marketplace that collects user data and stores it in HDFS using a JSON-like file format. 
This data includes information about user sessions represented in JSON. 
Based on this data, our objective was to develop dashboards for business analysts.

Storage Structure:
We've implemented two layers due to limited time for development. In the future, we can enhance the storage architecture.
Layer 1 - Staring: This is a replica of the data sourced from HDFS. If needed, we can always derive new metrics and dashboards from this data. The data here accumulates incrementally and is partitioned by date.
Layer 2 - Data Marts: This is a specifically defined schema in Postgres. It contains pre-processed data ready for further visualization in Metabase.

Purchase Definition for Visualizations:
For the 2nd and 3rd visualizations, a purchase is identified by the following sequence of client clicks:
product page -> carts -> payments -> confirmations.
For other click sequences, we cannot confirm that the client proceeded to the cart and completed the purchase without cancelling it.
