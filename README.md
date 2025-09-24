# Healthcare Chatbot Evals Workshop (15 min)

**Don't Advise � Judge � Improve**

A hands-on workshop for evaluating and improving healthcare chatbots using LLM-as-judge techniques.

## Overview

**Objective:** In ~15 minutes, you will:
1. Run evaluations on a **ground truth dataset** of chatbot replies labeled as `medical_advice`, `borderline`, `non_medical`
2. Improve the **chatbot prompt** to avoid medical advice while staying helpful
3. Improve the **LLM-as-judge prompt** so it better matches human labels (higher agreement, better recall on `medical_advice`)

## Two Key Roles

- **Chatbot**: Answers end-user health questions. Your goal is to **reduce medical advice** via prompt design
- **Judge (LLM-as-judge)**: Classifies chatbot replies as one of `medical_advice`, `borderline`, `non_medical`. Your goal is to **align the judge** to human labels

## Setup Instructions

### Prerequisites
- Python 3.12 or higher
- [uv](https://docs.astral.sh/uv/) package manager

### Installation

1. **Install uv** (if not already installed):
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

2. **Clone and navigate to the project:**
   ```bash
   git clone <your-repo-url>
   cd workshop-llm-evals
   ```

3. **Install dependencies:**
   Create and activate virtual env
   ```bash
   uv venv
   source .venv/bin/activate
   ```

   Install Dependencies: 

   ```bash
   uv sync
   ```

4. **Set up your OpenAI API key:**
   ```bash
   export OPENAI_API_KEY="your-openai-api-key-here"
   ```
   Or create a `.env` file:
   ```
   OPENAI_API_KEY=your-openai-api-key-here
   ```

5. **Start Jupyter:**

   ```bash
   uv run jupyter notebook
   ```

## Workshop Structure

### 1. Ground Truth Dataset
The workshop uses a carefully curated dataset of chatbot replies with human labels:
- **medical_advice**: Direct recommendations, dosages, diagnosis, treatment steps
- **borderline**: Health info, risk factors, general education, triage-like language
- **non_medical**: Deflections with disclaimers, support only questions

### 2. Evaluation Framework
- **Metrics**: Per-class precision/recall/F1 + macro averages
- **Confusion Matrix**: Detailed breakdown of classification errors
- **Cohen's Kappa**: Agreement measurement with human labels
- **Judge Evaluation**: Assess LLM-as-judge alignment with ground truth

### 3. Key Components

#### Chatbot Prompts
- Baseline system prompt for healthcare support

#### Judge Prompts
- Baseline classification prompt

