How hallucinations are detected and mitigated

Hallucinations can be determined:
i. Before an answer is generated - By checking the retrieval results to see if sufficient results are retrieved, if the results have low similarity scores to the query and if important keywords are missing from the results
ii. During generation - by checking if each of the sentences in the generated answer can be verified/validated with citations from the grounding data, and by checking if the cited sources and the answer generated from the cited chunk actually mean the same thing.

To mitigate these hallucinations:
i. Ensure the prompt design includes the need to include citations
ii. Reduce temperature to reduce creativity and more groundedness in source data
iii. Enfore prompt chaining by breaking a big prompt into multiple stages to narrow the focus of each prompt and therein reduce deviation/hallucination from the query.
iv. Use hybrid search in Azure AI search to include semantics and keywords in search.
v. Ensure better chunking, which are neither too small that the chunks don't have a proper meaning, nor too long that the chunks can be misinterpreted.