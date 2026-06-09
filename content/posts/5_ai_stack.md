---
title: "My Take on the AI Stack"
date: 2026-06-07T22:56:12-05:00
draft: false
tags: 
    - "artificial intelligence"
    - "ai engineering"
    - "ml engineering"
---
When machine learning started taking off around 6 years ago, before the advent of ChatGPT, everyone started chasing after the
title of "machine learning engineer". If you looked at their resumes and the job postings that targeted them, you would have
found a variety of skills across the stack, ranging from data science to MLOps to GPU programming. 

Now, an even more loaded term is floating around the industry: the "AI engineer". My frustration from back then remains the
same. Whenever I'm asked about what I'm working on or what paper I've read related to the AI field, I have a hard time 
setting the context of where exactly the topic falls. 

The following is a top-down view of my take on the LLM-focused AI stack. 

```goat
+---------+---------------------------------------+-----------------------------------------------------+
| Tier    | Layer                                 | Concepts                                            |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 11 | Agent Harnesses / Multi-agent systems | LLMOps  Prompt Optimization (Prompt Ops)            |
|         |                                       |                                                     |
|         |                                       | Generator-Evaluator Loops                           |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 10 | Agents / Agentic Applications         | MCP Servers  Prompt Engineering  Semantic Search    |
|         |                                       |                                                     |
|         |                                       | Retrieval-Augmented Generation                      |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 9  | LLM Inference/Serving                 | Flash Attention  KV Cache  Speculative Decoding     |
|         |                                       |                                                     |
|         |                                       | Continuous Batching  PagedAttention  Quantization   |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 8  | LLM Training/Finetuning               | Pretraining  Finetuning  Distillation               |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 7  | LLM Architecture                      | Multimodal LLMs  Mixture-of-Experts                 |
|         |                                       |                                                     |
|         |                                       | Small Language Models  Multihead Latent Attention   |
|         |                                       |                                                     |
|         |                                       | Vision-Language-Action models (VLAs)                |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 6  | Deep Learning                         | Transformers  CNNs  RNNs  LSTMs  Embedding models   |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 5  | Machine Learning                      | PCA  Clustering  Autoencoders                       |
|         |                                       |                                                     |
|         |                                       | Nearest-Neighbor Search                             |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 4  | ML Frameworks                         | torch.compile (PyTorch)  XLA (JAX)  DeepSpeed       |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 3  | GPU Programming                       | CUDA Programming Model  Triton  RoCM                |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 2  | Intermediate Representations (IR)     | PTX  Tile IR  SASS                                  |
+---------+---------------------------------------+-----------------------------------------------------+
| Tier 1  | Hardware/Networking                   | GPU  SRAM  DPU  TPU  Systolic Architectures         |
|         |                                       |                                                     |
|         |                                       | Caching  NVLink  RDMA  System-on-Module (SOM)       |
+---------+---------------------------------------+-----------------------------------------------------+
```