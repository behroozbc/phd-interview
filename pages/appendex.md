## Improved neuro-symbolic RAG

<v-clicks>

The [GraphRAG](https://arxiv.org/pdf/2404.16130) is a strong neuro-symbolic advance but the current graph-based RAG methods often **retrieve redundant information** and **lack strong task alignment**. 

I propose a refined hybrid RAG framework which is PathRAG and RAFT techniques inspired for better alignment.

-  Preprocess documents into an entity-relation graph using LLMs.
-  Retrieve nodes via keyword + semantic similarity, followed by relational path aggregation to reduce redundancy.
-  Generate answers with a prompted LLM.
-  Fine-tune the model.

Evaluation will use UltraDomain benchmark datasets (Agriculture, CS, Legal,Mixed) to test generalization to diverse, long-tail domains.
</v-clicks>
---
layout: two-cols-header
---

## Language specialization in multilingual LLMs

How multilingual LLMs allocate language-specific knowledge across parameters, especially in MoE architectures.

**Are some attention heads or experts specialized for particular languages?**
::left::
<v-clicks>

### Attention heads

- Model: Aya-23 <!--Deep leguge undarstanding than aya-101-->
- Dataset: An Small Persian and English parallel data.
- Method: An adapt techniques from “Are Sixteen Heads Really Better than One?” to identify language-specific vs. language-agnostic heads.
</v-clicks>
::right::
---
layout: two-cols
---

<v-clicks>

 ### MoE routing behavior
- Model: Mixtral 8b and gpt-oss-20b 
- Dataset: FLORES-200 dataset and the dataset of the attentoin heads part.
- Method: Averaging router activations to identify language-specific vs. language-agnostic heads.


</v-clicks>
---
src: master-thesis-appendex.md
---
---
src: cv.md
---

---
src: whyme.md
---