# Timeseries Database Comparisons

TODO merge these words with the iPython Notebook, use the ipynb as basis for blog post.



Here I compare several databases for suitability of storing financial timeseries.

Of particular importance is the ability to query & return a large amount of data that can be turned into a Pandas DataFrame for analysis.

I use historical forex ticks from Pepperstone, which used to be freely available to download. Their dataset is about 30GB of zipped CSV files, organized by month.

https://www.pepperstone.com/en/client-resources/historical-tick-data

I analyze Arctic, kdb+ (32bit), Cassandra and InfluxDB. I have used Docker containers for each, and have provided a compose file for simple replication of what I explore here. You simply need to use your own data.

I am using bid/ask tick data from the AUD/USD pair from May 2005 until April 2016, for a total size of 11GB of uncompressed CSV files.

The data is formatted as:
`PAIR`, `DATE`, `TIME`, `BID`, `ASK`
I.e.
```
AUD/USD,20090501 00:00:00.830,0.72902,0.72923
AUD/USD,20090501 00:00:00.831,0.72902,0.7291
AUD/USD,20090501 00:00:00.832,0.72902,0.72912
AUD/USD,20090501 00:00:01.078,0.72904,0.72912
AUD/USD,20090501 00:00:01.337,0.72903,0.72912
AUD/USD,20090501 00:00:01.580,0.72903,0.72913
AUD/USD,20090501 00:00:01.581,0.72903,0.72915
AUD/USD,20090501 00:00:01.582,0.72907,0.72915
AUD/USD,20090501 00:00:01.602,0.72908,0.72915
AUD/USD,20090501 00:00:02.585,0.72908,0.72919
```

For the sake of a fair comparison, we will look at a small subset of this while comparing KDB+, as the free version is limited to 4GB of memory.


## Overview
Arctic
kdb+
Cassandra
InfluxDB
