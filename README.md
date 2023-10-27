# Online Marketplace Data Analysis

## Background
We operate an online marketplace that collects user data and stores it in HDFS using a JSON-like file format. This data captures details about user sessions, all formatted in JSON. Using this data, we aimed to create insightful dashboards for our business analysts.

## Storage Structure
Our data storage is designed in two layers:

- **Layer 1 - Staging**: 
  - A mirror of the data sourced directly from HDFS.
  - Data in this layer accumulates incrementally and is organized by date.
  - Offers flexibility to derive new metrics and dashboards as needed.

- **Layer 2 - Data Marts**:
  - A defined schema in Postgres.
  - Contains processed data, primed for visualization in Metabase.
  
_Note_: Our current two-layer approach was chosen due to developmental time constraints. Future enhancements to the storage architecture are planned.

## Visualization Definitions
For our 2nd and 3rd visualizations, a purchase is defined by the following sequence of client actions:

- `product page` -> `carts` -> `payments` -> `confirmations`

For sequences differing from the above, we lack the certainty that the client completed their purchase without any cancellations.
