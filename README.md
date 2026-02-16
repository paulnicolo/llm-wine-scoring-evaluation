# Evaluating LLM Prompting Strategies for Subjective Scoring

## Overview
This project evaluates how large language models perform on subjective scoring tasks by predicting numerical wine ratings from free-text tasting notes. The goal is to understand how different prompting strategies affect accuracy, reliability, and uncertainty when the target variable is inherently subjective.

## Methods
I compare four approaches:
- **Mean baseline:** Predicting the average expert-assigned score
- **Zero-shot prompting:** No examples provided
- **Few-shot prompting:** Two example reviews with known scores
- **Few-shot with chain-of-thought (CoT):** Few-shot prompting with explicit reasoning before scoring

Strict output constraints are enforced to ensure predictions are machine-readable and comparable at scale.

## Evaluation
Model performance is evaluated using mean absolute error (MAE) and mean squared error (MSE). In addition to accuracy, I examine prediction variance by repeatedly scoring the same review to assess uncertainty under identical inputs.

## Key Findings
- A simple mean baseline performs competitively due to the narrow distribution of expert-assigned scores.
- Few-shot prompting provides modest improvements over zero-shot prompting.
- Chain-of-thought reasoning yields incremental gains but does not eliminate subjectivity.
- Repeated inference produces non-zero variance, highlighting uncertainty in mapping language to precise numeric ratings.

## Implications
These results suggest that while LLMs can extract signal from subjective text, their outputs should be treated as estimates rather than ground truth. Baselines, output constraints, and uncertainty analysis are critical when deploying LLMs in real-world evaluation or decision-support systems.

## Files
- `llm_prompting_subjective_scoring.ipynb`: Full analysis notebook
- `llm_prompting_subjective_scoring.pdf` (optional): Static version for quick review
