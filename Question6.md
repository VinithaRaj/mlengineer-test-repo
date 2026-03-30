How Personally Identifiable Information and sensitive commercial data are protected? 

Multiple steps are required throughout the entire RAG pipeline to completely ensure no Personally Identifiable Information such as name, address, employee IDs are passed on through the search to other users. The steps are:
1. During ingestion - When ingesting from Sharepoint, use Machine Learning classfiers, string trasnformation functions such as Regex and using Microsfot Purview which is able to tag sensitive data
2. During generation - Redact information such as emails and addresses automatically if they do pass from retrieval to the generation stage.
3. Indexing stage - Tag chunks if they contain Personally Identifiable Information so that they can be masked or hashed.
4. Storage stage - make use of Azure Storage's encryption during storage and transit to ensure PII is protected from any sorts of data breach.