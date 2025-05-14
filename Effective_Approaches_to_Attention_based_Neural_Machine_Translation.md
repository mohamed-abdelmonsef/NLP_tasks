# Notes on "Effective Approaches to Attention-based Neural Machine Translation"

**Paper link**: [https://arxiv.org/abs/1508.04025](https://arxiv.org/abs/1508.04025)

## Overview

This paper investigates two simple yet effective classes of attention mechanisms in neural machine translation (NMT):

- **Global attention**: Considers all source words when computing the context vector.
- **Local attention**: Focuses only on a subset (window) of source words at a time.

## Motivation

- Neural machine translation has achieved promising results, but models often struggle with **long sentences** due to the **fixed-length context vector**.
- The **encoder-decoder** architecture processes the input into a single fixed-length vector, which the decoder uses to generate the output sequence.
- **Attention mechanisms** address this bottleneck by dynamically computing a context vector at each decoding step, based on the input sequence.

## Attention Mechanisms

### Global Attention
- Attends to **all positions** in the source sentence.
- Ensures comprehensive coverage of the input.

### Local Attention
- Restricts attention to a **fixed window** of source positions.
- Reduces computational complexity, especially for **long sequences**.
- Offers a good trade-off between performance and speed.

## Alignment Functions

Three types of alignment (scoring) functions are evaluated:

1. **Dot product**  
   - Simple and effective.  
2. **General**  
   - A generalization of the dot product using a trainable weight matrix.  
3. **Concat**  
   - Concatenates vectors and applies a feedforward network, offering greater expressiveness at higher cost.

## Experimental Setup

- **Datasets**:
  - WMT’14 English-to-German: 4.5 million sentence pairs.
  - IWSLT English-to-Vietnamese.
- **Evaluation Metric**:
  - BLEU score: Measures translation quality against reference translations.

## Key Results

- Attention-based models outperform non-attentional baselines by up to **5.9 BLEU points** on the English-to-German task.
- **Local attention** performs comparably to global attention while being significantly **faster**.
- The **dot product** alignment function achieves a strong balance of simplicity and performance.
- **Attention weight visualizations** show meaningful alignments, often corresponding to **linguistic structure**.
- The **input-feeding approach** reduces common errors (e.g., word repetitions), improving overall translation **fluency**.

