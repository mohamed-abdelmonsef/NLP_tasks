# ROUGE Evaluation Metrics for Text Summarization

The ROUGE (Recall-Oriented Understudy for Gisting Evaluation) metric evaluates the quality of generated text (e.g., a summary) by comparing it to human-produced references. ROUGE primarily measures n-gram overlaps and the longest common subsequence between the candidate and reference summaries.

---

## ROUGE-N

**ROUGE-N** evaluates the overlap of **n-grams** between the candidate and the reference text.

### Example

Reference (R):  
`The cat is on the mat.`

Candidate (C):  
`The cat and the dog.`

### ROUGE-1 (Unigrams)

- **Precision**: Number of matching unigrams in C that appear in R  
  → Matching: `"the", "cat", "the"`  
  → ROUGE-1 Precision = 3 / 5 = **0.60**

- **Recall**: Number of matching unigrams in R that appear in C  
  → Matching: `"the", "cat", "the"`  
  → ROUGE-1 Recall = 3 / 6 = **0.50**

- **F1-Score**:  
  ROUGE-1 F1 = 2 × (P × R) / (P + R) = **0.54**

---

### ROUGE-2 (Bigrams)

- Matching bigram: `"the cat"`

- **Precision**:  
  ROUGE-2 Precision = 1 / 4 = **0.25**

- **Recall**:  
  ROUGE-2 Recall = 1 / 5 = **0.20**

- **F1-Score**:  
  ROUGE-2 F1 = 2 × (P × R) / (P + R) = **0.22**

---

## ROUGE-L

**ROUGE-L** is based on the **Longest Common Subsequence (LCS)**, allowing for non-consecutive matches as long as the sequence order is preserved.

- Reference (R): `The cat is on the mat.`
- Candidate (C): `The cat and the dog.`
- LCS: `"the cat the"`

- **Precision**:  
  ROUGE-L Precision = 3 / 5 = **0.60**

- **Recall**:  
  ROUGE-L Recall = 3 / 6 = **0.50**

- **F1-Score**:  
  ROUGE-L F1 = 2 × (P × R) / (P + R) = **0.55**

---

## ROUGE-S (Skip-Bigram)

**ROUGE-S** uses **skip-bigrams**, allowing for word pairs to be considered a match even if separated by intervening words.

### Example

- Reference: `The cat is on the mat.`
- Candidate: `The gray cat and the dog.`

- The bigram `"the cat"` doesn't match exactly, but **ROUGE-S** counts `"the gray cat"` as a match due to the skip-gram approach.

- ROUGE-S precision, recall, and F1 are computed similarly to ROUGE-N, but with flexibility in word separation.

---

## Summary: Pros and Cons of ROUGE

### ✅ Pros

- Correlates well with human judgment
- Language-independent
- Computationally efficient

### ⚠️ Cons

- Limited to **syntactic** matches; cannot detect **semantic** similarity (e.g., synonyms)
- Penalizes paraphrasing or abstraction

---

## ROUGE Focus

- ROUGE is **recall-oriented**: it emphasizes how much of the human reference is captured in the candidate.
- Precision-recall tradeoffs must be considered when interpreting results.

---
