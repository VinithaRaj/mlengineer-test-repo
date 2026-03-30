Design a data platform that:
1. Ingests structured & unstructured data
2. Supports AI search and analytics use cases
3. Scales across multiple projects


i. I would design a lakehouse-based data platform using Azure Data Lake Storage as the foundation, with structured and unstructured ingestion handled by Data Factory and Microsoft Graph API. Data would be organized into bronze, silver, and gold layers for raw, processed, and business-ready data. 

ii. For AI use cases, unstructured data would be chunked, embedded, and indexed into Azure AI Search to support hybrid and vector search with ACL-based security. 

iii. Analytics workloads would be served through Synapse or Databricks using the gold layer. The platform would be metadata-driven to support multiple projects, with shared ingestion frameworks, centralized governance via Microsoft Purview, and full observability through Azure Monitor and Application Insights. This ensures scalability, reuse, and strong separation between analytics and AI workloads.