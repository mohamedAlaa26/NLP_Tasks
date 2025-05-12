# 📊 ROUGE: Recall-Oriented Understudy for Gisting Evaluation

**ROUGE** is a set of metrics used to evaluate the quality of automatically generated text, such as **summaries** or **translations**, by comparing them with human-written references.

---

## 🔍 What Does ROUGE Measure?

ROUGE evaluates the **overlap** between the machine-generated output (candidate) and a human-written reference using different strategies like n-gram match, longest common subsequence, and skip-bigrams.

---

## 📏 ROUGE Variants

### 🔹 ROUGE-N

Measures the overlap of **n-grams** between the candidate and reference text.

#### Example:

- **Reference**: `She went to the market to buy vegetables.`
- **Candidate**: `She went to the shop to get groceries.`

**ROUGE-1 (Unigrams)**  
- Matching unigrams: `she`, `went`, `to`, `the`  
- Precision = 4 / 8 = **0.50**  
- Recall = 4 / 8 = **0.50**  
- F1 = **0.50**

**ROUGE-2 (Bigrams)**  
- Matching bigrams: `she went`, `went to`, `to the`  
- Precision = 3 / 7 = **0.43**  
- Recall = 3 / 7 = **0.43**  
- F1 = **0.43**

---

### 🔹 ROUGE-L (Longest Common Subsequence)

Evaluates the **longest common subsequence** (LCS) between the candidate and reference, preserving the word order.

#### Example:

- **Reference**: `He quickly ran across the street.`
- **Candidate**: `He ran across the busy street.`

- LCS = `he ran across the street` (5 words)
- Precision = 5 / 6 = **0.83**
- Recall = 5 / 6 = **0.83**
- F1 = **0.83**

---

### 🔹 ROUGE-S (Skip-Bigrams)

Counts matched **word pairs in order** (not necessarily consecutive).

#### Example:

- **Reference**: `The quick brown fox jumps over the lazy dog.`
- **Candidate**: `The brown fox leaped over a lazy animal.`

- Skip-bigram matches: `brown fox`, `over lazy`  
- Useful when similar content is expressed with slight word reordering.

> Note: ROUGE-S is less frequently used and not always implemented in modern libraries.

---

## ✅ Pros and ❌ Cons

### ✅ Pros
- Simple and fast to compute
- Strong correlation with human judgment
- Language-agnostic

### ❌ Cons
- Sensitive to exact wording (misses paraphrases)
- Does not consider meaning or synonyms

---

## 🔄 ROUGE vs. BLEU

| Metric     | Focus     | Measures                              |
|------------|-----------|---------------------------------------|
| **BLEU**   | Precision | How much of the candidate exists in the reference |
| **ROUGE**  | Recall    | How much of the reference is covered by the candidate |

> ROUGE emphasizes **recall**, BLEU emphasizes **precision**. Used together, they provide a fuller evaluation.

---

## 📚 Further Reading

- ROUGE Paper: [Lin, 2004](https://aclanthology.org/W04-1013)
- Medium Tutorial: [2-Minute NLP - ROUGE Explained](https://medium.com/nlplanet/two-minutes-nlp-learn-the-rouge-metric-by-examples-f179cc285499)

