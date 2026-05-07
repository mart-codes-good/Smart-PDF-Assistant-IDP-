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

## RAG Design (mart-codes-good) 


## UI Design (mart-codes-good & zcxu-4444)
**Initial Design** 
The intial UI was build in gradio and ...
