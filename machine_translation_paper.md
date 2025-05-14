# Notes on Neural Machine Translation by Jointly Learning to Align and Translate

📄 **Paper Link**: [https://arxiv.org/abs/1409.0473](https://arxiv.org/abs/1409.0473)

## Overview

This paper addresses a fundamental limitation in traditional sequence-to-sequence machine translation models:

- While **encoder-decoder architectures** are effective for short sentences, they struggle with **longer sentences** due to the bottleneck of compressing all information into a **single fixed-length context vector**.

To overcome this, the authors propose a **neural attention mechanism** that allows the model to **focus on different parts** of the input sentence during translation. This dynamic alignment process improves translation quality, particularly for longer sequences.

---

## Key Idea

Rather than encoding the entire input sequence into a single vector, the model:

- Produces a **sequence of hidden states** from the encoder (one for each input word).
- Uses an **attention mechanism** in the decoder to dynamically compute a **context vector** at each time step, allowing it to selectively focus on relevant input words.

This mechanism **mimics human translation behavior**, focusing on specific words or phrases as needed, rather than relying on memory of the entire sentence.

---

## Model Architecture

### 🔹 Encoder

- Processes the input sentence word-by-word using an RNN (e.g., **LSTM** or **GRU**).
- Instead of outputting a single vector, it generates a **sequence of hidden states**, each representing contextual information around the corresponding input word.

### 🔹 Decoder with Attention

- Also an RNN that generates the translation **one word at a time**.
- At each decoding step, it computes a **context vector** as a **weighted sum of the encoder's hidden states**.
- These **attention weights** indicate which parts of the input are most relevant for generating the next output word.
- The attention weights are dynamically calculated based on the decoder’s current hidden state and the encoder's outputs.

### 🔹 Attention Mechanism

- The attention scores can be computed using:
  - **Dot-product**
  - **Additive (feedforward network)**

These scores are normalized (typically using a softmax function) to obtain a probability distribution over the input words, effectively learning the **alignment** between input and output tokens.

### 🔹 Output Prediction

- The decoder combines:
  - Its **current hidden state**
  - The **context vector** from attention  
- It then uses this combined representation to predict the **next word** in the target sequence.
- This process repeats until the full translation is generated.

---

## Conclusion

The attention mechanism:
- Enables **better handling of long sentences**
- Provides **interpretable alignments** between input and output
- Significantly **improves translation quality**

---


