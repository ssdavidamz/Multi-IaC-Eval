---
license: cc-by-nc-4.0
task_categories:
- text-generation
language:
- en
tags:
- code
---
# Multi-IaC-Eval

We present Multi-IaC-Eval is a novel benchmark dataset for evaluating LLM-based IaC generation and mutation across AWS CloudFormation, Terraform, and Cloud Development Kit (CDK) formats. The dataset consists of triplets containing initial IaC templates, natural language modification requests, and corresponding updated templates, created through a synthetic data generation pipeline with rigorous validation.

Cloudformation: 263
Terraform: 446
CDK (Python): 64
CDK (Typescript): 64

## Dataset purpose

The purpose of Multi-IaC-Eval is to benchmark the performance of AI models in mutating IaC files based on natural language requests.

## Dataset description

Each example in Multi-IaC-Eval consists of three components - an initial IaC state, a natural language request to modify the initial IaC state, and an expected IaC state (following the same naming convention as the initial state). CDK files are provided as .ZIP files, while Terraform and Cloudformation data is provided as CSV.

CDK data is divided by programming language - either Python or Typescript.

For our Terraform and CFN format data, we provide CSV formatted data to facilitate loading in HuggingFace. Each row contains the following:

```
source: a source file name, along with an index, that can be referenced to the directory structure in the repo. This is the same filename used in the repository from which the data was sourced. The index indicates that we create multiple examples from a single input IaC template.
initial: the initial IaC template.
expected: the expected output IaC template implementing the utterance request.
utterance: the natural language request to modify the initial IaC state.
source_repo: the GitHub repository from which the initial IaC was sourced.
```
