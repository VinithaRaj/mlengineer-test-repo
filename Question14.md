Describe data lineage tracking.

Data lineage tracking refers to capturing the end-to-end lifecycle of data, from its original source through ingestion, transformation, indexing, and eventual use in LLM responses. In a RAG system, this includes: 
i. tracking the origin of documents from systems like SharePoint or email
ii. transformations applied such as PII masking and chunking, embedding model versions, indexing metadata
iii. monitoring how the data was retrieved and used in generating responses 

this ensures full traceability for compliance, debugging, and governance, and is typically implemented using tools like Microsoft Purview along with custom metadata tracking in Azure AI Search and the application layer.