# Research Gaps
<v-click>

## Research Interests 
My research interests focus on **neuro-symbolic methods**, **interpretability** and **multilinguality** in NLP.
</v-click>
<v-clicks>

1. **neuro-symbolic methods**
    - It is a hybrid approach that brings the advantages of sub-symbolic and symbolic AI. 
2. **interpretability**
    - Rapid progress in deep learning often outpaces our understanding of how changes affect internal behavior. Better interpretability enables more targeted and successful improvements.
3. **multilinguality**
    - As a multilingual speaker, I frequently notice how Large Language Models (LLMs) perform inconsistently on low-resource.
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
- They cannot flow the relation on the graph in retrieval.
- Model cannot find proper relation in indexing and retrieval because it has lack of task alignments.

</v-click>
::right::


<v-click>

### 🎯 Goal

- Generated knowledge graph become more sense and have less hallucinations. 
<!-- - Context-aware generation of knowledge graph. -->
- In retrieval, follow the path of relations. 
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

<v-click>
Because of rapid achievements we don't know how multilingual LLMs allocate language-specific knowledge across parameters, especially in MoE architectures.

**Are some attention heads or experts specialized for particular languages?**
</v-click>
::left::
<v-click>

### ⚠️ Resulting Issues

- Using many computation parts on unusual part in training and fine-tuning.
- Distillation would damage useful parts of model on the specific tasks. 
</v-click>
::right::

<v-click>

### 🎯 Goal

- Understanding part of model are specific to each language.
- More energy and computation efficient fine-tuning.
    - Only fine-tuning useful parts and fix other parts. 
- Creating distilled smaller model with less losing needed capability.
</v-click>
---
layout: two-cols-header
---

## Multi Language neuro-symbolic method

The [GraphRAG](https://arxiv.org/pdf/2404.16130) methods do not have capability of indexing and augmenting be in different languages, which usually results nonsense outputs. 
Therefore indexing in one language and answering in other language not possible or answers be poorly.

::left::
<v-click>

### ⚠️ Resulting Issues

- Responses contain hallucinations because insufficient data added on prompt.
- Answers may be unrelated.
- Answers may include inaccuracies.

</v-click>
::right::

<v-click>

### 🎯 Goal

- Answers be similar to original data answers. 
- Answers contains multi languages data.
</v-click>