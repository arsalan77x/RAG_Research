# RAG Research

## RAG Frameworks and Engines
In this section, we first introduce four of the most popular open-source RAG frameworks and provide general information about their features in relation to our work. 
### 1. **txtai** 
   txtAI helps developers create custom tools for tasks like searching documents, questions/answering systems, and summarizing text. It connects retrieving data with useful insights, making it a good option for smaller projects or limited resources. 

### 2. **Haystack**
Haystack works with different search engines like Elasticsearch, OpenSearch, and FAISS. It's more scalable compared to txtai, for example it supports fine-tuning transformer models directly within the framework. 


### 3. **GraphRAG (Microsoft)**
GraphRAG focuses on enhancing retrieval-augmented generation by integrating graph-based approaches. It utilizes knowledge graphs to represent relationships between data points, providing a structured and enriched retrieval mechanism. This makes it particularly effective for tasks that require deep contextual understanding and interlinked information.

### 4. **LangChain** 

LangChain is a versatile framework designed to build applications that combine large language models (LLMs) with external data sources. It provides tools for creating dynamic, multi-step workflows and is particularly known for its robust integrations and ease of use in constructing complex RAG pipelines.

| **Framework**   | **Features**                                                                                   |
|------------------|-----------------------------------------------------------------------------------------------|
| **txtAI**       | 1. Vector Search with SQL Integration                                                          |
|                  | 2. Multimodal Embedding Creation                                                              |
|                  | 3. Language Model Pipelines                                                                   |
|                  | 4. Workflow Integration (connection of multiple pipelines)                                    |
|                  | 5. Easy to develop compared to other three frameworks                                         |
| **Haystack**    | 1. Modular Pipeline Architecture                                                               |
|                  | 2. Integration with Multiple Backends (FAISS, Elasticsearch, ...)                             |
|                  | 3. Scalability and Performance Optimization                                                   |
| **GraphRAG**    | 1. Enhanced Contextual Understanding (leveraging relationships between entities)               |
|                  | 2. Scalability for Complex Data Sets                                                          |
|                  | 3. Integration with Microsoft Azure services                                                  |
|                  | 4. Semi-automated validation for retrieved information                                        |
| **LangChain**   | 1. Multi-Step Workflow Support (complex chaining of LLM interactions)                         |
|                  | 2. Easy Integration with External Data Sources (APIs, databases, file systems)                |
|                  | 3. Support for Custom Prompt Engineering                                                      |
|                  | 4. Fine-Tuning and Customization for Domain-Specific Applications                             |
|                  | 5. Flexible Deployment Options (cloud, on-premises, and hybrid environments)                  |



## Translators
1. LibreTranslate
2. DeepL Translator (free?!)
3. OpenAI Whisper 
4. Microsoft Translator

## Benchmarks
1. Quality: \
   MCQ format.
   Provides Large context -> proper to test Q/A from given doc.
   Need Translation
2. PersianQA: \
   https://github.com/sajjjadayobi/PersianQA
   One word answers. Context is short (1-2 paragraph). Questions are easy to answer. \
3. PersianQuad: \
   https://github.com/Forutanrad/FarsiQuAD/tree/main
   Similar to previous one.

## Notes
1. There are some persian LLM benchmarks -> might be useful for Fine-tuning: \
   https://github.com/ParsBench/ParsBench \
   https://github.com/sajjjadayobi/PersianQA
2. Benchmarks have Train,Dev,Test which can be useful for training.
3. Check: https://colab.research.google.com/github/deepset-ai/haystack-cookbook/blob/main/notebooks/query-expansion.ipynb
