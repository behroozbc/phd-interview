# Research Gaps
## Research Interests 
My research interests focus on **neuro-symbolic methods**, **interpretability** and **multilinguality** in NLP.
<v-clicks>

1. **neuro-symbolic methods**
    - It is a hybrid approach and brings advantage of sub-symbolic and symbolic AI. 
2. **interpretability**
    - Rapid progress in deep learning often outpaces our understanding of how changes affect internal behavior. Better interpretability enables more targeted and successful improvements.
3. **multilinguality**
    - As a multilingual speaker, I frequently notice how Large Language Models (LLMs) perform inconsistently on low-resource and unseen languages.
</v-clicks>
---
layout: two-cols-header
---

## Improved neuro-symbolic RAG

<v-click>

The [GraphRAG](https://arxiv.org/pdf/2404.16130) is a strong neuro-symbolic advance but the current graph-based RAG methods often **retrieve redundant information** and **lack strong task alignment**.
</v-click>
::left::
<v-click>

### ⚠️ Resulting Issues

- Generated knowledge graph is nonsense. 
- Models cannot find proper information from the context.
- Correct methods use flat structure to manage.
- They cannot flow the relation on the graph in retrieval.
- Lack task alignments.
- Model cannot find proper relation because it has lack of task alignments.
</v-click>
::right::


<v-click>

### 🎯 Goal

- Generated knowledge graph become more sense and have less hallucinations. 
- Context aware generation of knowledge graph.
- In retrieval flow path of relations. 
- Task alignment in knowledge graph generations.
</v-click>
<!-- <v-clicks>

 

I propose a refined hybrid RAG framework which is PathRAG and RAFT techniques inspired for better alignment.

-  Preprocess documents into an entity-relation graph using LLMs.
-  Retrieve nodes via keyword + semantic similarity, followed by relational path aggregation to reduce redundancy.
-  Generate answers with a prompted LLM.
-  Fine-tune the model.

Evaluation will use UltraDomain benchmark datasets (Agriculture, CS, Legal,Mixed) to test generalization to diverse, long-tail domains.
</v-clicks> -->
---
layout: two-cols-header
---

## Language specialization in multilingual LLMs


Because of rapid achievements we don't know how multilingual LLMs allocate language-specific knowledge across parameters, especially in MoE architectures.

**Are some attention heads or experts specialized for particular languages?**
::left::

### ⚠️ Resulting Issues

- Using many computation parts on unusual part in training and fine-tuning.
- Distillation would damage useful parts of model on the specific tasks. 

::right::

### 🎯 Goal

- Understanding part of model are specific to each language.
- More energy and computation efficient fine-tuning.
    - Only fine-tuning useful parts and fix other parts. 
- Creating distilled smaller model with less losing needed capability.

---
layout: two-cols-header
---

## Multi Language neuro-symbolic method

The [GraphRAG](https://arxiv.org/pdf/2404.16130) methods do not have capability of indexing and augmenting be in different langues, which usually results nonsense outputs. which results questioning in one language and answering in other language not possible or answers be poorly.

::left::

### ⚠️ Resulting Issues

- Responses can sometimes contain hallucinations.
- Answers may be unrelated.
- Answers may include inaccuracies.
::right::

### 🎯 Goal

- Answers be similar to original data answers. 
- Answers contains multi languages data.