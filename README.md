# Cognitive Bias Detector

A multi-stage NLP reasoning system that detects, explains and corrects cognitive biases in text using local LLMs, LangChain workflows and vector databases.

## Overview

The Cognitive Bias Detector is designed to go beyond simple classification and perform deep reasoning over text. Instead of just labeling bias:

* Extracts structured claims from raw text
* Identifies cognitive biases at the claim level
* Explains why the bias exists
* Highlights the exact parts of the text responsible
* Rewrites the content in a neutral and unbiased form

This project emphasizes pipeline-based reasoning workflows rather than single-step LLM responses.

## System Architecture

The system is built as a multi-stage transformation pipeline:

### 1. Input Processing

* Accepts raw text
* Splits into logical reasoning units

### 2. Claim Extraction

* Identifies individual claims from text
* Structures them into analyzable units

### 3. Claim Normalization

* Converts informal statements into logical representations
* Extracts:
  * Subject
  * Assumptions
  * Evidence Type

### 4. Bias Knowledge Base

* Vector database containing:
  * Definitions of cognitive biases
  * Examples
  * Detection patterns

### 5. Retrieval Layer

* Retrieves relevant biases for each claim using embeddings
* Enables focused reasoning instead of generic classification

### 6. Bias Detection

* Matches claims against retrieved bias patterns
* Outputs:
  * Bias Type
  * Confidence Score
  * Reasoning

### 7. Evidence Mapping

* Links detected bias to exact text spans
* Provides contextual grounding

### 8. Explanation Layer

* Explains:
  * Why the bias exists
  * Flawed assumptions
  * Missing information
* Focuses on interpretability and reasoning

### 9. Bias Correction

* Rewrites biased claims into neutral, balanced statements
* Preserves meaning while removing bias

### 10. Scoring & Aggregation

* Assigns:
  * Bias Severity Score
  * Confidence Level
* Produces a structured final report


## Workflow Design

The system follows a pipeline-based architecture:

Raw Text
↓
Claim Extraction
↓
Claim Normalization
↓
Bias Retrieval (Vector DB)
↓
Bias Detection
↓
Explanation Generation
↓
Bias Correction
↓
Final Structured Output

## Key Features

* Multi-step reasoning pipelines
* Claim-level bias detection
* Explanation-driven outputs
* Bias-aware text rewriting
* Local LLM support
* Vector database integration for knowledge grounding

## Tech Stack

* LangChain for workflow orchestration
* Local LLMs for reasoning and generation
* Hugging Face models for embeddings and inference
* Vector Database for bias knowledge storage

## Example Output

Input:
Everyone I know who invested in crypto got rich, so it is a guaranteed way to make money.

Output:
* Claim: Limited sample used to generalize outcome
* Bias: Hasty Generalization
* Explanation: Based on a small non representative sample
* Highlight: "Everyone I know"
* Corrected: "Some people have made profits from crypto but outcomes vary widely."
* Severity: High

## 🎯 Learning Objectives

This project is designed to develop:

* Workflow-based LLM system design
* Multi-step reasoning pipelines
* Vector database usage beyond basic retrieval
* Structured output generation
* Prompt specialization across tasks
* Understanding limitations of local models

## Challenges

* Bias detection requires reasoning not just classification
* Local models may struggle with deep inference
* Claim extraction quality directly impacts performance
