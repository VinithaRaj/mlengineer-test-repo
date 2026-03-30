Explain how you would monitor pipeline health?

To monitor data is flowing through the entire pipeline within reasonable latency and quality I would monitor health at each step in the following ways:
i. Data Sources
- ensuring all data source APIs are healthy and accesible, monitoring the latency between ingested data and current data, and keeping track of expected and fetched items. 
ii. Ingestion
- keeping track of retry and timeout counts, processing delays and failures and queue backlog frequencies
iii. Processing
- monitoring the rate of processing one chunk or page and the success rates during processing
iv. Indexing
- monitoring the index writing rate and successful indexes that are queryable 
v. Retrieval
- monitoring the trend of retrieval results in terms of quality, count, and speed
