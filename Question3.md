How you would evaluate the answer's quality?

In a RAG framework the quality of the answer can be measured by:
i. Factual correctness - is there a chunk that can be seen that validates the answer?
ii. Adherence to query with respect to the context - is the correct contextual answer given for words that can mean more than one thing, example, 'bug', 'mouse', 'ticket' can mean more than one thing depending on context.
iii. Amount of hallucinations - checking whether the results can be rooted or cross checked with facts and citations can be produced.
iv. Consistency - Is the answer consistent with other queries with similar meaning yet different keywords
v. Retrieval quality - By checking for false positives within the search results