# AI Review Summarizer

## Run in Google Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Q06ilwK-Ic9d_2L1vBj0H6l66c8kRzVy?usp=sharing)
---

## Problem
Customers often read multiple product reviews, making it difficult to quickly understand overall sentiment and key insights. This project converts raw reviews into structured insights.

---

## Solution
This project builds an AI-powered pipeline that:
- Generates a concise summary
- Extracts pros and cons
- Predicts sentiment (Positive / Negative / Mixed / Neutral)
- Provides a confidence score

---

## Features
- Structured JSON output
- Schema validation
- Safe JSON parsing (failure handling)
- Confidence-based uncertainty handling
- Multilingual support (English + Arabic)
- Evaluation with multiple test cases

---

## Tech Stack
- Python
- Groq API (LLaMA 3.1)
- JSON

---

## How to Run

### 1. Install dependencies
```bash
pip install groq
```

### 2. Set API key
```bash
export GROQ_API_KEY="your_api_key"
```

### 3. Run the notebook
Open and run:
```
review_summarizer_ai.ipynb
```

---

## Example Output

```json
{
  "summary": "The product is good but considered expensive.",
  "pros": ["good"],
  "cons": ["expensive"],
  "sentiment": "Mixed",
  "confidence": 0.5
}
```

---

## Evaluation

Tested on 10 diverse test cases:
- Positive, Negative, Mixed, Neutral
- Multilingual (Arabic)
- Uncertain inputs

### Results:
- Accuracy: 10/10

### Observations:
- High confidence for clear inputs
- Lower confidence for ambiguous inputs
- Correct handling of mixed sentiment

---

## Example: Uncertain Input

Input:
"I don't know about this product"

Output:
- Sentiment: Neutral  
- Confidence: Low (0.2–0.3)

---

## Multilingual Example

Input:
"المنتج جيد جدا"

Output:
- Correct sentiment detected

---

## Uncertainty Handling
- Uses confidence score (0–1)
- Reduces confidence for unclear inputs
- Avoids overconfident predictions

---

## Tradeoffs
- Small evaluation dataset (manually created)
- Output depends on model behavior
- No UI (focused on core AI pipeline)
- Requires API key

---

## Tooling
- Groq API with LLaMA 3.1 model for inference
- Prompt engineering for structured JSON output
- ChatGPT for debugging and prompt refinement
- Evaluation loop for testing reliability

---

## Notes
- Add your GROQ_API_KEY before running
- Uses safe parsing to handle invalid JSON outputs
