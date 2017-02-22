# Timeseries Database Comparisons
Here I compare several databases for suitability of storing financial timeseries.

Of particular importance is the ability to query & return a large amount of data that can be turned into a Pandas DataFrame for analysis.

I use historical forex ticks from Pepperstone, which used to be freely available to download. Their dataset is about 30GB of zipped CSV files, organized by month.

https://www.pepperstone.com/en/client-resources/historical-tick-data

I analyze Arctic, kdb+ (32bit), Cassandra and InfluxDB. I have used Docker containers for each, and have provided a compose file for simple replication of what I explore here. You simply need to use your own data.

## Overview
Arctic
kdb+
Cassandra
InfluxDB
