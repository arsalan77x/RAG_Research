# RAG Research

## 1. RAG Frameworks and Engines
In this section, we first introduce four of the most popular open-source RAG frameworks and provide general information about their features in relation to our work. 
### 1.1. **txtai** 
   txtAI helps developers create custom tools for tasks like searching documents, questions/answering systems, and summarizing text. It connects retrieving data with useful insights, making it a good option for smaller projects or limited resources. (https://github.com/neuml/txtai)

### 1.2. **Haystack**
Haystack works with different search engines like Elasticsearch, OpenSearch, and FAISS. It's more scalable compared to txtai, for example it supports fine-tuning transformer models directly within the framework. (https://github.com/deepset-ai/haystack)


### 1.3. **GraphRAG (Microsoft)**
GraphRAG focuses on enhancing retrieval-augmented generation by integrating graph-based approaches. It utilizes knowledge graphs to represent relationships between data points, providing a structured and enriched retrieval mechanism. This makes it particularly effective for tasks that require deep contextual understanding and interlinked information. (https://github.com/microsoft/graphrag)

### 1.4. **LangChain** 

LangChain is a versatile framework designed to build applications that combine large language models (LLMs) with external data sources. It provides tools for creating dynamic, multi-step workflows and is particularly known for its robust integrations and ease of use in constructing complex RAG pipelines. (https://github.com/langchain-ai/langchain)

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



## 2. RAG structure Comparison

In this section, 

### 2.1. Paper Review: Q/A analysis on Portuguese (https://arxiv.org/pdf/2401.07883)

We focus on the retriever part investigated in their paper. They analyzed Dense retriever (ADA-002) which is outdated and sparse dense retriever (BM25) and also their combination (hybrid). They also investigated use of Reranker after retrieve which works in this way:

- **Model Used**: `unicamp-dl/mt5-base-en-pt-msmarco-v2`.
  - This is a **sequence-to-sequence Transformer model** trained on multilingual passage ranking datasets (MS MARCO).
  - Optimized for English and Portuguese text.

- **Input Format**:
  - Query and document are combined into a text input.
  - Example: `Query: {query} Document: {document} Relevant:`

- **Output Format**:
  - The model generates a binary label:
    - `yes` (relevant) or `no` (not relevant).
  - The relevance score is derived from the softmax probability of the label `yes`.

- **Reranking Process**:
  - Each retrieved chunk is assigned a relevance score based on the model's prediction.
  - The chunks are reordered according to these scores.

![image](https://github.com/user-attachments/assets/23e719fd-c085-414b-9a6e-7d97317847b3)

#### Metrics:
- A higher MRR@10 means relevant documents are returned at higher positions in the list (closer to rank 1).
- R@3 (Recall at k): Higher recall means the retriever is more comprehensive in retrieving relevant information, even if it doesn't rank them at the top.
- 
![image](https://github.com/user-attachments/assets/a931470a-3249-40d4-8ca4-5742b97f259b)
- **k**: The number of top results considered (e.g., \( R@3 \), \( R@5 \), etc.).
### 2.2. 

### 2.3. RAG structure comparison




### 2.2. Generator Component
GPT-4o
GPT-4o-mini

### 2.3. Question Classification

## 3. Benchmarks
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

## 4. Notes
1. There are some persian LLM benchmarks -> might be useful for Fine-tuning: \
   https://github.com/ParsBench/ParsBench \
   https://github.com/sajjjadayobi/PersianQA
2. Benchmarks have Train,Dev,Test which can be useful for training.
3. Check: https://colab.research.google.com/github/deepset-ai/haystack-cookbook/blob/main/notebooks/query-expansion.ipynb
4. Cuconasu et al. in The Power of Noise: Redefining Retrieval for RAG Systems
 says: Surprisingly, random documents (completely unrelated to the query) improve model accuracy by up to 35% when added to the prompt. This finding challenges traditional assumptions about information retrieval in RAG systems.

