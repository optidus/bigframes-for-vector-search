# Build a vector search application in Python using BigFrames

This notebook will guide you through a practical example of using [BigFrames](https://github.com/googleapis/python-bigquery-dataframes/issues) to perform [vector search](https://cloud.google.com/bigquery/docs/vector-search-intro) and analysis on a patent dataset within BigQuery. We will leverage Python and BigFrames to efficiently process, analyze, and gain insights from a large-scale dataset without moving data from BigQuery.

Here's a breakdown of what we'll cover:

1. **Data Ingestion and Embedding Generation:**
We will start by reading a public patent dataset directly from BigQuery into a BigFrames DataFrame.
We'll demonstrate how to use BigFrames' `TextEmbeddingGenerator` to create text embeddings for the patent abstracts. This process converts the textual data into numerical vectors that capture the semantic meaning of each abstract.
We'll show how BigFrames efficiently performs this embedding generation within BigQuery, avoiding data transfer to the client-side.
Finally, we'll store the generated embeddings back into a new BigQuery table for subsequent analysis.

2. **Indexing and Similarity Search:**
Here we'll create a vector index using BigFrames to enable fast and scalable similarity searches.
We'll demonstrate how to create an IVF index for efficient approximate nearest neighbor searches.
We'll then perform a vector search using a sample query string to find patents that are semantically similar to the query. This showcases how vector search goes beyond keyword matching to find relevant results based on meaning.

3. **AI-Powered Summarization with Retrieval Augmented Generation (RAG):**
To further enhance the analysis, we'll implement a RAG pipeline.
We'll retrieve the top most similar patents based on the vector search results from step 2.
We'll use BigFrames' `GeminiTextGenerator` to create a prompt for an LLM to generate a concise summary of the retrieved patents.
This demonstrates how to combine vector search with generative AI to extract and synthesize meaningful insights from complex patent data.


We will tie these pieces together in Python using BigQuery DataFrames. [Click here](https://cloud.google.com/bigquery/docs/dataframes-quickstart) to learn more about BigQuery DataFrames!
