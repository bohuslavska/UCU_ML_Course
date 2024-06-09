**About the Project**

This repository contains **the final project for the UCU Machine Learning course**, which focuses on leveraging advanced analytics to combat disinformation. 

The project consists of two important parts: (1) the Mantis Analytics transformer (under NDA, out of scope of this repository), which is capable of detecting and classifying 18 propaganda techniques, and (2) the RAG pipeline, which explains these techniques by retrieving relevant information from the vector knowledge base. The primary goal is to equip end users — mainly journalists and fact-checkers — with tools that not only extract and label manipulations but also explain their classifications.

The inspiration for the project comes from the 2019 research paper "Fine-Grained Analysis of Propaganda in News Articles" by Giovanni Da San Martino et al. This paper identifies manipulation techniques commonly found in various media outlets. 

**Tech Stack**

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

**RAG**

The core of the project involves creating a Retrieval-Augmented Generation (RAG) pipeline that integrates transformer outputs with an effective query and context management system. This integration aims to improve the factual accuracy of generated responses. To create a vector knowledge base, 21 sources (both URLs and PDFs) were utilized. These sources were parsed using LangChain's UnstructuredURLLoader and PyPDFDirectoryLoader, and retrieved with the help of the LangChain RetrievalQA.from_chain_type() function.

<img width="601" alt="image" src="https://github.com/bohuslavska/UCU_ML_Course/assets/94128854/263640f8-db43-47fb-82cd-906ecbb9565b">

**Metrics**

Various metrics are used to evaluate the RAG pipeline. These include context precision and recall, which assess retrieval effectiveness, and metrics like faithfulness and answer relevance, which evaluate the generation process. Metrics such as context recall or answer correctness judge the RAG system according to the ground truth. 

<img width="738" alt="Screenshot 2024-06-08 at 15 35 12" src="https://github.com/bohuslavska/UCU_ML_Course/assets/94128854/e3389517-a83d-40ee-bd50-b79c079dfb5c">

Here are the metrics received on the English test dataset: while retrieval metrics are quite high, faithfulness—a measure of the factual consistency of the generated answer against the given context—is quite low. Efforts are ongoing to refine the prompts to better integrate context.

<img width="278" alt="image" src="https://github.com/bohuslavska/UCU_ML_Course/assets/94128854/66999dbd-bf0c-403f-aa72-9f46ea8de922">

