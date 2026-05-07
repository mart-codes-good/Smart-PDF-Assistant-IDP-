# Smart-PDF-Assistant-IDP

This program is an IDP (intelligent document processor) with a chatbot that acts as a virtual assistant. It features a RAG pipeline with adjustable parameters  such as chunk sizes, overlap, and retrieval depth. 

Knowledge cutoffs are a common limitation of LLM’s. They occur when the model’s training data is finalized, after which it can no longer get new information or updates. In addition to this, LLM’s also struggle with niche topics since they were likely not trained on these sets of information. This program is one of the examples of solving this issue, using an RAG pipeline to provide the chatbot with any niche or private information you may need to work with, so that it can better serve you.

So that you can use this program locally, make a copy of this document after signing into Google Colab and add your Gemini API key in the secrets tab.

The link is here: [IDP Assistant](https://colab.research.google.com/drive/15pr8PLYeqSkbJsfDdOWQlmmCa0KzpEqW?usp=sharing)

Media of the application will be attached here soon.

### Libraries used:
* Gradio
* Llama Index
* Hugging Face Embeddings
* nest_asyncio

## Backend (RAG) Design (mart-codes-good)
When a file is uploaded, pymuPDF is used to scan the PDF file and to then convert it into a blob of text represented as a single string. This string is then chunked into many pieces in the chunking process.

Since I wanted to give users control over chunking sizes, I used SentenceSplitter.
This way, users can adjust chunk sizes and overlap as they see fit, resulting in either sliding window chunking or fixed character chunking, depending on the user's preference and needs.

These chunks are then converted into nodes by llama index’s splitter. Nodes currently do not have metadata, but users could adjust it as they see fit, or I can expand on this design in the future.

Nodes are converted into vector embeddings using an embedding model. 
When a user asks a question, the query is also converted into a vector. The VectorIndexRetriever compares this query vector to the stored node vectors using similarity search and retrieves the top-k most relevant chunks.

The value of k controls how many of the most similar chunks are returned. These retrieved chunks are then passed to the RetrieverQueryEngine, which uses them as context for the chatbot to answer given questions with the appropriate context.


## UI Design (mart-codes-good & zcxu-4444)
The UI is a little bland at the moment, since I wanted to prioritize functionality and ensure that all core features can be operated with few issues. I did some light styling and component adjustments, but I stopped there. 

The UI will be improved by my other collaborator in the future, who has a greater skill in making visually appealing user-facing designs.
