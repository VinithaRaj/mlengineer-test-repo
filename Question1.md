The submission includes a clear README or written overview outlining:

Design a Retrieval-Augmented Generation (RAG) system that:
1. Indexes SharePoint documents, project emails, and QA records
2. Supports semantic search with citations
3. Works securely within an enterprise Azure environment

RAG which is short for Retrieval Augmented Generation is a framework that improves or customises searches by grounding the Large Language Models in a specifi groundtruth which can be an organisation's internal documents or specific verified sources.

Since this is an Azure environment, I will be using Azure native products in this design.

On a high level these are the steps in the RAG pipeline:
1. Data Ingestion - Identifying the data source, and a means to pull the data to its next destination to be processed.

Since the problem statement mentions SharePoint documents, these can include text files, PDF files, Project Plans, Excel Sheets, images, Financial plans, wiki pages and a vast range of documents.

2. Data Storage - Once the data is pulled from its source, it has to be stored somewhere before it can be compiled or processed, to be in a format ready to be used.

Since a vast range of structured and unstructured data can be found within SharePoint, it is safest to pull the data into a data lake which in this case would be Azure Blob Storage.

3. Indexing Stage - this is the stage where the grounding data can become a searchable document and become the grounding data for the LLM. 
i. Cleaning & Standardization - In this stage, the data is standardized by adding metadata in the same format which would be used in the citation step, such as source, date, author or team responsible.
ii. Chunking - The pulled data is chunked wherein large documents are broekn down into smaller more manageable chunks which enables the LLM to better retrieve answers by finding chunks that match the context most instead of returning the whole document. Add overlap to the chunks so that 
iii. Embeddings - The chunks are turned into embeddings so that searches can be performed faster and produce more accurate and meaningful results. Since the problem states that it should be a semantic search, instead of keyword, embeddings ensure that phrases with similar meaning aand context. This can be done using Azure OpenAi embeddings. Store these indexes in Azure AI search.
iv. Semantic Ranking - Enable the vector search capability and semantic ranking since we want this to be a semantic search that understands the meaning/context of the query instead of matching word to word.
v. Adding security - Store access_groups and user_ids to ensure document level filtering
5. Retrieval - this is the stage where a user makes a query and expects an answer. When this happens, the following steps should take place:
i. Input handling - ensure the input is clean, and the semantic or meaning of the query is understood
ii. Query embedding - use the same embedding method used in the indexing stage to embed the query so that answers can be found from the same semantic space.
iii. Search - Then based on the query embedding, a semantic search (since the problem statement states semantic) is made using semantic similarity between the embeddings, and optionally a keyword search is made.
iv. Results ranking - rank the results in order of semantic similarity between the query and answer embeddings.
v. Result selection - select the top k results

6. Generation - This is the stage where the asnwer is generated. To allow this to happen:
i. Prompt template - Ensure there is a prompt template provided to tell the LLM (Azure OpenAI LLM) the format an answer is expected in.
7. Performance Optimization - for repeated queries with similar semantics, cache the embeddings. 
8. Governance - to track the query latency, traffic, retrieval quality, incorporate Azure Monitor with Log Analytics into the pipeline