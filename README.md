# Retrieval-augmented Generation using PDF URLs

**Author**: Dany Raihan

This project, for demonstartive purpose, uses `langchain` to chain outputs together into a flow for radibility, `chromadb` as Vector database, `text-embedding-3-small` by OPENAI to vectorize text, and `gpt-4o-mini` by OPENAI to query contexts and questions. However, you can replace any of the componet using any model or alternatives.


## Workflow:
1. **Fetch PDF Content**: Download and extract content from a list of PDF URLs.
2. **Trim Metadata**: Prepare the necessary metadata for vectorization.
3. **Split Text into Chunks**: Convert the PDF content with metadata into overlapping text chunks to prepare the data for vectorization.
4. **Vectorize the Text Chunks**: Vectorize the text chunks using the specified embedding model and store the vectors in a Chroma vector database.
5. **Query the Vector Store**: Perform a similarity search in the vector store based on a given query to retrieve the most relevant documents.
6. **Parse the Search Results**: Parse and join the text from the search results to create a context for the model.
7. **Construct Instruction's Model**: Construct the instruction that includes the context and the query to be passed to the model.
8. **Perform Retrieval-augmented Generation**: Generate the final answer using the RAG pipeline by querying the model with the constructed instruction.

Each step is crucial in constructing a reliable RAG pipeline, especially when working with unstructured data like PDFs.