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

- The student’s background knowledge
- The prerequisite topics they should already understand
- What the instructor has covered in class
</v-clicks>
::right::
<v-click>

### ⚠️ Resulting Issues
</v-click>
<v-clicks >


- Answers may include inaccuracies
- Some explanations may be irrelevant or missing
- The model may ignore details the instructor has already explained
- Responses can sometimes contain hallucinations
</v-clicks>
---

### 🎯 Thesis Goal

My thesis aims to address and solve these limitations by designing a system that:

<v-clicks>

- Adapts responses to the student’s knowledge level
- Incorporates course‑specific content
- Reduces hallucinations
- Provides more accurate, context‑aware answers
</v-clicks>
---

### Data Structure


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
    Prossess["Chunking"]
    Data-->Prossess
```
</template>
<template #3>
```mermaid 
flowchart LR
    Data["Data"]
    Prossess["Chunking"]
    Storage
    Data-->Prossess-->Storage
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
GetUserknowleageStatus["Get User Knowleage Status"]
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