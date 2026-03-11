---
layout: two-cols-header
---
# TripartiteRAG

## Problem Statement & Motivation
Students often ask questions from ChatGPT or other language models.
::left::
<v-click>

### 🎓 Challenge in Using Language Models for Education
</v-click>
<v-click>
these models do not know:
</v-click>
<v-clicks >

- The student’s background knowledge.
- The prerequisite topics they should already understand.
- What the instructor has covered in class.
</v-clicks>
::right::
<v-click at=1>

![qa](/front-view-female-student-writing-notes.png)
</v-click>
---
layout: two-cols-header
---

### ⚠️ Resulting Issues
::left::
<v-clicks >


- Answers may include inaccuracies.
- Some explanations may be irrelevant or missing.
- The model may ignore details the instructor has already explained.
- Responses can sometimes contain hallucinations.
</v-clicks>
::right::
<v-click>

![dontfindanswer](/front-view-female-student-with-many-files.png)
</v-click>
---

### 🎯 Thesis Goal

My thesis aims to address and solve these limitations by designing a system that:

<v-clicks>

- Adapts responses to the student’s knowledge level.
- Incorporates course‑specific content.
- Reduces hallucinations.
- Provides more accurate, context‑aware answers.
</v-clicks>
---
layout: two-cols-header
---

### Data Structure

::left::
```mermaid
flowchart TD
    symbol["Symbol(Topic)"]
    definition["Definition"]
    explain["Explain"]
    LM["Learner Model"]
    prerequisites["Prerequisites(symbol)"]
    symbol---explain
    symbol---definition
    LM-.-symbol
    prerequisites-->symbol
```
::right::

- All symbols stored on a knowledge graph.
- A learner model is a separate system that predicts a student’s level of understanding based on their interactions with quizzes and problem‑solving tasks.
- All symbols and their relationships are stored in GraphDB, and data retrieval is possible only via SPARQL queries.
- You can see all system on [ALeA system](https://alea.education/).
---

## ✅ What I done so far! 

### Indexing
<v-switch>
<template  #1>

```mermaid
flowchart LR
    Data["Data"]
    Data
```

#### Data
- The course materials and content related to each section and the UUID.
</template >

<template #2>
```mermaid 
flowchart LR
    Data["Data"]
    Process["Chunking"]
    Data-->Process
```
</template>
<template #3>
```mermaid 
flowchart LR
    Data["Data"]
    Process["Chunking"]
    Storage
    Data-->Process-->Storage
```
</template>
</v-switch>

---

### Generating
<v-click>

```mermaid
flowchart LR
input["`User Question`"]
VectorSearch["Vector Search"]
KeywordExtractor["Keyword Extractor"]
LexicalSearch["Lexical Search"] 
RetrievedScored["Retrieved and Scored Content"]



input-->VectorSearch
input-->KeywordExtractor-->LexicalSearch
VectorSearch-->RetrievedScored
LexicalSearch-->RetrievedScored



```

</v-click>

<v-click>

***
```mermaid
flowchart LR
BuildPrompt["Build Prompt"]
GetUserknowleageStatus["Get User Knowledge Status"]
RetrievedScored["Retrieved and Scored Content"]
GatherPrerequisites["Gather Prerequisites"]
GatherSymbols["Gather Symbols"]
RetrievedScored-->BuildPrompt
RetrievedScored-->GatherSymbols
RetrievedScored-->GatherPrerequisites
GetUserknowleageStatus-->BuildPrompt
GatherPrerequisites-->GetUserknowleageStatus
GatherSymbols-->GetUserknowleageStatus
```
</v-click>

---

## Remaining Tasks

<v-clicks depth=2>

- Evaluating my results.
    - Human review: instructor/TA rubric
    - LLM as judge: does the answer align with retrieved fragments?
- Try RAFT method
    - Prepare a small dataset with question and answers.
    - Fine-Tuning the model.
    - compare RAG results with new Results.
</v-clicks>