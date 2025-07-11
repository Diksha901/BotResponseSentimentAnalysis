**Analyzing Teen Mental Health Sentiment and Bot Responses** 
This project focuses on deriving useful insights from a data set containing bot_response and user_input about mental health of teenage children and analyzes the emotional tone of teen chatbot conversations to gain insights into users’ mental health and evaluate the effectiveness of the chatbot's responses. It leverages both traditional rule-based models (NLTK’s VADER) and deep learning models (RoBERTa) to classify sentiment as Positive, Negative, or Neutral.

---


**Files in This Repository**
*TeenMentalHealthAnalysis.ipynb* — Jupyter Notebook with data preprocessing,libraries used for sentiment analysis and conclusions.
*final_teen_mental_health_chatbot_dataset.csv*- Dataset on which we are performing this analysis. It contains the user_input and bot_responses.
*README.md* — You’re reading it!

---

**Models Used**
**VADER**

`VADER` stands for `Valence Aware Dictionary and sEntiment Reasoner`. It is a rule-based sentiment analysis tool that is included in the NLTK (Natural Language Toolkit) library.

* Uses a predefined lexicon of words rated for positive, negative, and neutral sentiment.

* Applies rules to adjust scores based on:

       1. Punctuation (!!!, ?)

       2. Capitalization (GOOD vs good)

       3. Degree modifiers (very, barely)

       4. Negations (not happy)

* Outputs four scores:
  1. pos (positive)
  2. neg (negative)
  3. neu (neutral)
  4. compound (a normalized score between -1 to 1)

* Strengths:
  1. Lightweight, fast
  2. Good for short, social-media-style text
  3. Easy to interpret

* Limitations:
  1. Can miss contextual meaning
  2. Struggles with sarcasm, irony, or complex language
  3. Doesn't learn or adapt from new data

 **RoBERTa**

`RoBERTa (A Robustly Optimized BERT Pretraining Approach)` is a transformer-based language model developed by Facebook AI. It is an improved version of BERT, trained with:

* More data

* Larger batches

* No "next sentence prediction" task

* It can be fine-tuned for various NLP tasks, including sentiment classification.

* *Working*: 
   1. Uses deep contextual embeddings to understand the meaning of each word in context
   2. Fine-tuned with labeled datasets like IMDB, SST-2, or Twitter sentiment
   3. Outputs class probabilities (e.g., negative: 0.2, neutral: 0.6, positive: 0.2)

* Strengths:
  1. Handles nuance, sarcasm, idioms
  2. Understands contextual word usage
  3. Highly accurate, state-of-the-art in many benchmarks

* Limitations:
  1. Computationally heavier
  2. Needs GPU for large datasets
  3. Less interpretable than VADER


---

**Libraries Used**
* `pandas, numpy` — Data processing
* `matplotlib, seaborn` — Data visualization
* `nltk` (VADER, tokenizer)
* `transformers` (RoBERTa from HuggingFace)

---

**Future Work**
* Fine-tune RoBERTa on mental health-specific datasets.
* Add an empathy classifier to assess the warmth of bot replies.
* Generate real-time bot response rewrites using a conditional transformer (e.g., T5)
