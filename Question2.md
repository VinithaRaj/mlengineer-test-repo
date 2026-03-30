How you would design prompts for:
1. Knowledge Q&A
2. Tender document drafting
3. Financial queries

Since these are 3 different requirements, here's how I would do for each of these cases. Across these cases I would use prompt chaining where instead of one large prompt, there are multiple consecutive prompts to produce better results with lesser hallucinations. We would also be changing the temperature to alter the amount of creativity or groundedness as needed.

1. Knowledge Q&A - it's a summarization task wherein the user would want an answer picked up exactly from documents with citations. So the temperature should be lower.
i. The first step would be sending a rewrite prompt to create a concise prompt.
ii. Based on the generated prompt, a hybrid/just semantic search is made using Azure AI search.
iii. The Top K results from the AI search are picked and another prompt is made to generate a summarized answer from the returned search results

The prompt should look like:
You are a strict enterprise knowledge assistant.

Rules:
- Use ONLY the provided sources.
- Do NOT guess or infer missing information.
- If answer is not in sources, say "I don't know."
- Always cite sources like [1], [2].

Sources:
{context}

Question:
{query}

2. Tender document drafting - Since this task involves generating a document requiring a little more creativity than the first task, the temperature is set to be slightly higher than the first.
i. The first step would be sending a rewrite prompt to create a concise prompt.
ii. Based on the generated prompt, a hybrid/just semantic search is made using Azure AI search to find similar scopes and past proposals.
iii. A summarization prompt is sent to summarize the results of step ii.
iv. A generation prompt is sent to generate a document based on the summary in step iii.

3. Financial queries - this requires absolutely zero creativity or hallucinations and requires correct answers rooted in fact which can be cross checked, with correct logical calculations. The steps are:
i. The first step would be sending a rewrite prompt to create a concise prompt.
ii. Based on the generated prompt, a hybrid/just semantic search is made using Azure AI search to find numerical data matching the prompt in step i.
iii. a third prompt is sent to extract the numerical values from the reports and what they mean for example, painting cost - $400 and so on from tables and structures. In this prompt, include the need for citations and validation with absolutely no hallucination.
iv. a fourth prompt is sent to perform calculations with steps and explanations on the required outputs. 