Explain how you would handle incremental updates vs full reloads?


Incremental updates would be the most frequent and realistic everyday case, where only the new changes have to be updated, mostly on a daily basis. To do this, I would:
i. Track changes by ingesting all data modified after a specific timestamp or by using Delta APIs like MIcrosoft Graph Delta queries to only see the changes.
ii. Then, rechunk and recompute the embeddings for the changed data and add to the indexes. Remove deleted data from the index.

Full reloads are used when the data schema changes or there needs to be a recovery and are mostly less frequent and more expensive. To do this, I would:
i. Extract/ingest the entire dataset using Microsoft Graph API to extract the entire dataset from Microsoft 365.
ii. Re-chunk, re-embed and re-process all the data
iii. Enforce access controls and permissions on the fully reloaded data