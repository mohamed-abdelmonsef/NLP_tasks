# Notes on Comparing RNN Architectures: LSTM vs. GRU

📄 **Paper Link**: [https://arxiv.org/pdf/1412.3555](https://arxiv.org/pdf/1412.3555)


## Overview

This paper compares different types of recurrent neural networks (RNNs), particularly **gated RNNs**—namely:

- **Long Short-Term Memory (LSTM)**
- **Gated Recurrent Unit (GRU)**

These models are evaluated against traditional (vanilla) RNNs in terms of their ability to capture long-term dependencies and training efficiency.

---

## 1. Long Short-Term Memory (LSTM)

LSTM networks are designed to retain information over long sequences using a **memory cell** and **three gating mechanisms**:

- **Input Gate**: Determines what new information should be added to the memory cell.
- **Forget Gate**: Controls which information should be removed from memory.
- **Output Gate**: Decides what information from the memory cell is passed to the next hidden state.

### Key Characteristics:
- Maintains information over long time steps
- Highly expressive but **computationally expensive** due to more parameters
- Effective in learning complex temporal dependencies

---

## 2. Gated Recurrent Unit (GRU)

GRU simplifies the LSTM architecture by combining certain gates and removing the explicit memory cell:

- **Update Gate**: Merges the functionality of input and forget gates to control the flow of information.
- **Reset Gate**: Regulates how much past information to discard when computing the new hidden state.

### Key Characteristics:
- **Fewer parameters** than LSTM
- No separate memory cell (memory is embedded in the hidden state)
- **Faster training** and less resource-intensive
- Similar performance to LSTM in many tasks

---

## Experimental Findings

- Both **LSTM and GRU** outperform the standard RNN.
- The performance gap between LSTM and GRU is **small**.
- **GRU** offers a **more efficient training process** while maintaining strong performance.

---

## Conclusion

- **GRU** provides a compelling alternative to LSTM, achieving similar accuracy with fewer parameters and faster computation.
- The choice between **LSTM** and **GRU** should be guided by task complexity and resource constraints.
- Both models are effective for handling sequences with long-term dependencies.

---

