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

The following is top-down view of my take on the LLM-focused AI stack. 

```goat
+---------------------------------------+-----------------------------------------------------+
| Layer                                 | Concepts                                            |
+---------------------------------------+-----------------------------------------------------+
| Agent Harnesses / Multi-agent systems | LLMOps  Prompt Optimization (Prompt Ops)            |
|                                       | Generator-Evaluator Loops                           |
+---------------------------------------+-----------------------------------------------------+
| Agents / Agentic Applications         | MCP Servers  Prompt Engineering  Semantic Search    |
|                                       | Retrieval-Augmented Generation                      |
+---------------------------------------+-----------------------------------------------------+
| LLM Inference/Serving                 | Flash Attention  KV Cache  Speculative Decoding     |
|                                       | Continuous Batching  PagedAttention  Quantization   |
+---------------------------------------+-----------------------------------------------------+
| LLM Training/Finetuning               | Pretraining  Finetuning  Distillation               |
+---------------------------------------+-----------------------------------------------------+
| LLM Architecture                      | Multimodal LLMs  Mixture-of-Experts                 |
|                                       | Small Language Models  Multihead Latent Attention   |
|                                       | Vision-Language-Action models (VLAs)                |
+---------------------------------------+-----------------------------------------------------+
| Deep Learning                         | Transformers  CNNs  RNNs  LSTMs  Embedding models   |
+---------------------------------------+-----------------------------------------------------+
| Machine Learning                      | PCA  Clustering  Autoencoders                       |
|                                       | Nearest-Neighbor Search                             |
+---------------------------------------+-----------------------------------------------------+
| ML Frameworks                         | torch.compile (PyTorch)  XLA (JAX)  DeepSpeed       |
+---------------------------------------+-----------------------------------------------------+
| GPU Programming                       | CUDA Programming Model  Triton  RoCM                |
+---------------------------------------+-----------------------------------------------------+
| Intermediate Representations (IR)     | PTX  Tile IR  SASS                                  |
+---------------------------------------+-----------------------------------------------------+
| Hardware/Networking                   | GPU  SRAM  DPU  TPU  Systolic Architectures         |
|                                       | Caching  NVLink  RDMA  System-on-Module (SOM)       |
+---------------------------------------+-----------------------------------------------------+
```