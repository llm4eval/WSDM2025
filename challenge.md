---
title: Challenge
layout: page
description: Challenge
bodyClass: page-about
---

<h1 align="left">
<img style="vertical-align:middle" width="50px" height="40px" src="../images/logo/LLMJudge-logo.png" /> LLMJudge Overview
</h1>

The LLMJudge challenge is organized as part of the LLM4Eval workshop at WSDM 2025. Test collections are essential for evaluating information retrieval (IR) systems. Evaluating and tuning a search system largely depends on relevance labels, which indicate whether a document is useful for a specific search and user. However, collecting relevance judgments on a large scale is costly and resource-intensive. Consequently, typical experiments rely on third-party labellers who may not always produce accurate annotations. The LLMJudge challenge aims to explore an alternative approach by using LLMs to generate relevance judgments. Recent studies have shown that LLMs can generate reliable relevance judgments for search systems. Nevertheless, it remains unclear which LLMs can match the accuracy of human labellers, which prompts are most effective, how fine-tuned open-source LLMs compare to closed-source LLMs like GPT-4, whether there are biases in synthetically generated data, and if data leakage affects the quality of generated labels. This challenge will investigate these questions, and the collected data will be released as a package to support automatic relevance judgment research in information retrieval and search.

The detailed description of the challenge can be found in the following document.

## LLMJudge Task Design
The challenge will be, given the query and document as input, how they are relevant. Here, we use a four-point scale judgments to evaluate the relevance of the query to document as follow:

- __[3] Perfectly relevant__: The passage is dedicated to the query and contains the exact answer. 
- __[2] Highly relevant__: The passage has some answer for the query, but the answer may be a bit unclear, or hidden amongst extraneous information. 
- __[1] Related__: The passage seems related to the query but does not answer it. 
- __[0] Irrelevant__: The passage has nothing to do with the query.

The task is, by providing to the participants the datasets that include quereis, documents, and query-document file, to ask LLMs to generate a score [0, 1, 2, 3] indicating the relevancy of query to document.

## How to participate?
- Teams do not need the registration before the submission, you will need to register your team when you are submissing your results using the Google Form link provided in the [Submission](#submission) section.
- The datasets, baselines and evaluation scripts are available in the following repository: [https://github.com/llm4eval/LLMJudge](https://github.com/llm4eval/LLMJudge)
- Please check [Frequenty Asked Questions (FAQs)](#frequenty-asked-questions-faqs) section or email us if you have any questions: [hossein.rahmani.22@ucl.ac.uk](mailto:hossein.rahmani.22@ucl.ac.uk)

## LLMJudge Data

### Files
Below we list the files for the challenge:
- `./data/llm4eval_document_2024.jsonl` is a JSONL file consisting of document IDs and documents (passages).
- `./data/llm4eval_query_2024.txt` is a TXT file consisting of topic ID's, as well as queries (text).
- `./data/llm4eval_dev_qrel_2024.txt` is a TXT file consisting of train/dev topic ID's and document IDs with relevance labels. It can be used for training, fine-tuning, or in-context learning.
- `./data/llm4eval_test_qrel_2024.txt` is a TXT file consisting of test topic ID's and document IDs. This is the file that the participants must use to predict the relevance judgments of each query to document and submit as the final result file.

Note that all TXT files are tab-separated.

## Evaluation
Participants’ results will then be compared in two ways after submission:
- automated evaluation metrics on human labels in the test set hidden from the participants;
- system ordering evaluation of multiple search systems on human judgments and LLM-based judgments

## Submission
We will use Google Forms for submissions. Submission is closed. We provide a step-by-step Google Form to submit the detailed submission files. Please do not hesitate to contact us in case of questions and/or problems. The final results file should be formatted similarly to the challenge test file including one extra column for the LLM-generated labels for each sample:

```
<query_id> 0 <passage_id> <relevance_score>
```

> Note that each team is allowed to send several submissions. We also encourage running the same prompt on the same model for reproducibility purposes.

## Submission Form (Required Information)

### Section 1: Team information
1. Team ID
2. Submission ID
3. Team Members
4. Email

### Section 2: Submission of detailed information
1. Which LLM did you use for the challenge?
2. What is the size of the LLM?
3. Which prompting technique did you use? For example, Chain-of-Thoughts, or you can refer to paper.
4. Please upload the prompt you used for the challenge in a text file here.
5. Time Analysis. Please add time in seconds and if one of these times is not applied to your submission please consider it 0. Here are the time criteria that we would like to consider:
    - Running/Inference time
    - Fine-tuning time
    - Training time
6. Original output file before post-processing to get the final judgments (No. of generated tokens)
7. Please add a description of the main idea, your experience, interesting findings, or any thoughts that they would like to share with us 

### Section 3: Final result file Submission
1. Final Submission File. Please upload your final result file.

## Timeline
- Data Release: [https://github.com/llm4eval/LLMJudge](https://github.com/llm4eval/LLMJudge)
- Submission Deadline: Up until __February 10, 2025__ participants will be able to submit their results and solutions to be evaluated on the test set using automated metrics (which we will run on our servers).
- Overview of Results: The overview of results will be at LLM4Eval@WSDM2025 which will take place on __March 14, 2025__.

_All deadlines are 11.59 pm UTC -12h ("Anywhere on Earth")._

## Frequenty Asked Questions (FAQs)

> **1. (Model Usage)** Are we allowed to use different models for our submissions, or is there a specific model that we must use?

You can use any models you prefer. There are no restrictions on the models you can use for your submissions.

> **2. (Prompt Flexibility)** Can we change or customise the provided prompt, or must we use the exact prompts as specified in the challenge guidelines?

You can use any prompts you wish. The provided prompt is merely a sample from the paper by Thomas et al. [1].

[1] Thomas, Paul, Seth Spielman, Nick Craswell, and Bhaskar Mitra. "Large language models can accurately predict searcher preferences." arXiv preprint arXiv:2309.10621 (2023).

> **3. (Submission Limits)** How many runs are we permitted to submit for evaluation? Is there a limit to the number of submissions per team or model?

There are no limits on the number of submissions. You can submit as many runs as you want. We also encourage running and submitting the same model and prompt multiple times for reproducibility purposes.

> **4. (Query Format Clarification)** Regarding the format <query_id> 0 <passage_id> <relevance_score>, we understand that the 0 serves as a separator. Can you please confirm if this is correct?

Yes, the 0 serves as a separator.

Here are the answers to the new questions in the same format:

> **5. (Challenge Goal)** I am a bit unclear about the main goal of the challenge. Is it about finding the best evaluation prompt, finding the best public LLM model, fine-tuning an LLM model for judging purposes, or all of the above? Clarity here will help in the experiment setup.

The main goal of the challenge encompasses all of the above: finding the best evaluation prompt, identifying the best public LLM model, and fine-tuning an LLM model for judging purposes. Participants are encouraged to explore and innovate across these aspects.

> **6. (Reproducibility Factors)** To ensure reproducibility and comparison between different submissions, what are the set of factors which should be kept unchanged?

To ensure reproducibility and facilitate comparison between different submissions, the following factors should be kept unchanged:
- The evaluation dataset
- The evaluation metrics

> **7. (Competition and Winners)** Does the challenge have a contest i.e., will there be winners announced at the end of the competition?

Yes, the top-performing teams/submissions will be announced at the workshop.