# About the Project

This repository contains **the final project for the UCU Machine Learning course**, which focuses on leveraging advanced analytics to combat disinformation.

The project consists of two important parts:
1. **The Mantis Analytics transformer (under NDA, out of the scope of this repository)**, capable of detecting and classifying 18 propaganda techniques.
2. **The Retrieval Augmented Generation (RAG) pipeline**, which explains these techniques by retrieving relevant information from the vector knowledge base.

The primary goal is to equip end users—mainly journalists and fact-checkers—with tools that not only extract and label manipulations but also explain their classifications.

The inspiration for the project comes from the 2019 research paper "Fine-Grained Analysis of Propaganda in News Articles" by Giovanni Da San Martino et al. This paper identifies manipulation techniques commonly found in various media outlets.

## Tech Stack

Key technologies employed include:

- Python 3.10
- Pytorch 2.1.0
- FAISS
- Mistral LLM
- AWS SageMaker
- LangChain
- Ragas
- Gradio
- RAG

## RAG

The core of the project involves creating a Retrieval-Augmented Generation (RAG) pipeline that integrates transformer outputs with an effective retrieval and generation system. To create a vector knowledge base, 21 sources (both URLs and PDFs) were utilized. These sources were parsed via LangChain UnstructuredURLLoader and PyPDFDirectoryLoader, vectorized with the help of FAISS, stored locally, and later retrieved via LangChain RetrievalQA.from_chain_type() and similarity search functions.

![image](https://github.com/bohuslavska/UCU_ML_Course/assets/94128854/263640f8-db43-47fb-82cd-906ecbb9565b)

## Metrics

Various metrics are used to evaluate the RAG pipeline. These include context precision and recall, which assess retrieval effectiveness, and metrics like faithfulness and answer relevance, which evaluate the generation process. Metrics such as context recall or answer correctness judge the RAG system according to the ground truth. To assess our system, we used the Ragas framework that helps evaluate RAG pipelines.

![Screenshot 2024-06-08 at 15 35 12](https://github.com/bohuslavska/UCU_ML_Course/assets/94128854/e3389517-a83d-40ee-bd50-b79c079dfb5c)

Here are the metrics received on the English test dataset: while retrieval metrics are quite high, faithfulness—a measure of the factual consistency of the generated answer against the given context—is quite low. Efforts are ongoing to refine the prompts to better integrate the context.

<img width="242" alt="image" src="https://github.com/bohuslavska/UCU_ML_Course/assets/94128854/7581cc67-529f-4146-ab60-d9e9b05824c6">


