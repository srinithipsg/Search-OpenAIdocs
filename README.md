# Search-OpenAIdocs
#### OpenAI DocQA: Question Answering on OpenAI Documentation

##### Project Description:
This objective of this project is to perform question answering tasks on OpenAI docuemntation. 

The described process involves using content retrieved from the Apify actor via an API for a Question & Answering system. Here's a breakdown of the steps:

1. **Scraping Content**: Initially, content is scraped from a source using an Apify actor "Website Content Crawler".
   
3. **Content Segmentation**: The scraped content is divided into smaller segments or "chunks". This segmentation allows for a more detailed analysis and processing of the content.

4. **Text Embeddings**: Each of these content segments is then transformed into embeddings using the Huggingface embedding model named "BAAI/bge-base-en-v1.5." Text embeddings are numerical representations of the text that capture its semantic meaning.

5. **Storage in Pinecone DB**: These text embeddings, along with associated metadata, are stored within Pinecone DB. Pinecone is a service that provides semantic search capabilities, allowing for efficient similarity searches in large datasets.

6. **Semantic Search**: Pinecone's semantic search capabilities are leveraged to retrieve similar content matches from the database. This process helps identify content segments that are closely related in meaning to a given query.

7. **Q&A Using Mistral7b**: The next step involves generating answers to user queries. This is done by combining a user's query, a prompt, and the similar content matches identified in the previous step. The Mistral7b model, which is an open-source Language Model (LLM), is used for this purpose. It takes the combined input and generates contextually relevant responses and answers.

8. **Question Recommendation**: In addition to answering questions, the system also provides question recommendations. This is achieved using FAISS, a similarity search library, through the "langchain." FAISS is used to search and identify questions that are closely related to the user's query, which enhances the recommendation process. The similar questions are stored in a separate file or data source.

Overall, this process combines web scraping, text analysis, semantic search, and language modeling to provide users with relevant answers to their queries and recommend related questions based on similarity.

