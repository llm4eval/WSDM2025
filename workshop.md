---
title: Workshop
layout: page
description: Workshop
bodyClass: page-about
---

# Motivation
Large language models (LLMs), like GPT-4, have demonstrated increasing effectiveness, such that a larger model performs well enough to be usable on a task where a smaller model was unusable. Recently, LLMs have been actively explored for various kinds of evaluation among other tasks. 

In information retrieval (IR), among other applications, LLMs are being actively explored for estimating query-document relevance, both for ranking as well as for label generation. The latter can be subsequently used for training and evaluating other less-powerful but more-efficient rankers. For instance, HELM benchmark simultaneously generates query-document relevance labels and a ranking score. The input of the prompt is a query and document. The generated output is a yes/no label. The ranking is carried out based on the generation probabilities of the yes/no tokens. Some later work includes the HELM pointwise approach, and adds more ranking methods.

More interestingly, LLMs are currently being employed for relevance labelling in the industry. The evaluation methodologies can apply a wider range of LLMs and prompts to the labeling problem, and potentially address a wider range of potential quality problems.

More recently, with the advancement of LLMs, retrieval-augmented generation (RAG) systems, a class of LLM applications that use external data to augment the LLM's context, have significantly received attention. Basically, a RAG system consists of a retriever and a downstream language model. Given a user question, the retriever finds relevant passages from a corpus (e.g., a company's internal knowledge base) and the language model uses these passages to generate a response. This formulation admits a multitude of choices: what retrieval model to use, how to divide the documents into retrieval chunks, and how to prompt or fine-tune the language model to use the retrieved information, to name only a few of the simplest design decisions. Recent LLM-based evaluation has emerged as cheap and automatic strategy to evaluate the overall quality and the components of a RAG system.

In natural language processing (NLP), some recent work showed that LLMs can be used as reference-free evaluators for text generation. The idea involves employing LLMs to assess the candidate output by considering its generation probability without relying on a reference target. This approach assumes that LLMs are able to assign higher probabilities to texts that are of high quality and fluency. Studies have shown that LLMs can be perfect alternatives to human evaluation on NLG tasks. Some other work showed that the way of prompting (so-called "prompt engineering") can enhance the LLM evaluation quality, with their proposed chain-of-thought (CoT) prompts outperforming various traditional evaluators by a large margin in terms of correlation with human evaluations.

Motivated by these observations, we believe that a workshop on evaluation strategies in the world of LLMs will question whether IR and NLP are truly facing a paradigm change at the evaluation strategies. Therefore, we propose to organize a workshop with a fresh perspective on LLMs-based evaluation through an information retrieval lens. This workshop will also be a way to reflect on LLM-based evaluation benefits and challenges in academia and industry. Finally, we will encourage submissions and discussions on further evaluation topics and models, where existing literature is scarce, such as recommender systems, learning to rank, diffusion models, etc.

# Theme and Scope
The workshop will focus on models, techniques, data collections, and methodologies for information retrieval evaluation in the era of LLMs. These include but are not limited to:

- LLM-based evaluation metrics for traditional IR and generative IR
- Agreement between human and LLM labels
- Effectiveness and/or efficiency of LLMs to produce robust relevance labels
- Investigating LLM-based relevance estimators for potential systemic biases
- Automated evaluation of text generation systems
- End-to-end evaluation of Retrieval Augmented Generation systems
- Trustworthiness in the world of LLMs evaluation
- Prompt engineering in LLMs evaluation
- Effectiveness and/or efficiency of LLMs as ranking models
