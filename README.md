# AI Review Summarizer

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
- Safe JSON parsing
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

Tested on 10 cases:
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

## Future Improvements
- Add Arabic output generation
- Improve confidence calibration
- Use real datasets
- Build UI (Streamlit)

---

## Tooling
- Groq API for LLM inference
- ChatGPT for prompt iteration and debugging

---

## Notes
- Add your API key before running
- Uses safe parsing to handle invalid JSON

 ## Run on Google Colab

- You can open and run this project directly in Colab:
- [Open in Colab](https://colab.research.google.com/drive/1Q06ilwK-Ic9d_2L1vBj0H6l66c8kRzVy?usp=sharing)
