# GPT_Architecture
# Abstract: Custom Transformer-Based Text Generation Model

This project presents a custom implementation of a transformer-based autoregressive language model inspired by the GPT-2 architecture. Unlike traditional GPT models, this version does not use pretraining on massive datasets. Instead, it is designed for educational and experimental use, enabling text generation via dynamic tokenization and Wikipedia-based prompt input.

The architecture includes multi-head self-attention, feed-forward layers, residual connections, and causal masking, implemented using TensorFlow and Keras. The model allows generation of coherent text outputs from a given prompt using top-k sampling and temperature controls.

---

## Key Features

- **Architecture**: 12 transformer layers, 12 attention heads, embedding dimension of 768 (~90M parameters).
- **Tokenizer**: Custom regex-based tokenizer with a vocabulary of 3,000 tokens.
- **Training Strategy**: No pretraining; relies on on-the-fly tokenization and user-supplied text for inference.
- **Text Generation**: Uses autoregressive decoding with temperature scaling and top-k sampling.

---

## Performance & Comparison

Compared with mainstream pretrained language models:

| Model               | Params | Pretrained | Generation Speed | Memory Footprint | Quality |
|--------------------|--------|------------|------------------|------------------|---------|
| **This Model (Custom Transformer)** | ~90M   | ❌ No       | ✅ Fast           | ✅ Low            | ⚠️ Medium |
| GPT-2 Small         | 117M   | ✅ Yes      | ⚖️ Moderate       | ⚖️ Medium         | ✅ High |
| GPT-Neo 125M        | 125M   | ✅ Yes      | ⚖️ Moderate       | ❌ High           | ✅ High |
| GPT-J 6B            | 6B     | ✅ Yes      | ❌ Slow           | ❌ Very High      | ✅✅ Very High |

---

## Limitations

- **Lack of Pretraining**: No generalized knowledge of grammar, semantics, or world facts.
- **Limited Vocabulary**: Vocabulary size restricts linguistic variety and token resolution.
- **Tokenizer Simplicity**: Regex-based tokenization lacks subword granularity and multilingual support.
- **Evaluation**: No integrated metrics like perplexity or BLEU to assess output quality quantitatively.

---

## Future Work

- Incorporate **pretraining** on curated datasets for language fluency.
- Replace regex tokenizer with **Byte Pair Encoding (BPE)** or similar methods.
- Introduce **attention visualization tools** for model interpretability.
- Add **metric evaluation** for better benchmarking of output quality.
- Create an API or **interactive frontend** for easier user interaction.

---

## References

1. Vaswani et al. (2017), *Attention is All You Need*
2. Radford et al. (2019), *Language Models are Unsupervised Multitask Learners*
3. TensorFlow Documentation - https://www.tensorflow.org/api_docs
4. Wikipedia API - https://pypi.org/project/wikipedia/

---

*This model serves as a foundational implementation for researchers and developers interested in transformer mechanics without relying on pretrained corpora. Ideal for controlled experiments and NLP education.*
