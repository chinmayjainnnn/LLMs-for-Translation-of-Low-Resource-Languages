# Hindi-English Machine Translation Using Large Language Models (LLMs)

Welcome to the repository for our research and development in Hindi-English machine translation leveraging Large Language Models (LLMs). This repository documents our experiments, results, and contributions toward creating robust translation models for Hindi and other Indic languages.

## 📑 **Overview**

This project focuses on benchmarking and fine-tuning open-source LLMs for Hindi-English translation. Once robust models are achieved, the approach will be extended to India's North-Eastern languages.

## **Key Contributions**

1. **Extensive Zero-Shot Benchmarking**:
   - Evaluated state-of-the-art open-source LLMs: LLaMA, Mistral, Gemma, and OpenHathi.
2. **Exploration of Prompting Strategies**:
   - Benchmarked using 0-shot, 2-shot, and 4-shot prompting.
3. **Fine-Tuning with QLoRA**:
   - Implemented Parameter-Efficient Fine-Tuning (PEFT) with Low-Rank Adaptation (LoRA).

---

## **Models Evaluated**

1. **LLaMA 2**: Pretrained and fine-tuned LLMs by Meta AI (7B, 13B, and 70B parameters).
2. **Mistral**: 7B parameter model with advanced architectural features like grouped query attention.
3. **Gemma**: Transformer decoder-based LLM (2B and 7B parameters) by Google AI.
4. **OpenHathi**: Indic language-specific model optimized for Hindi-English translation.

---

## **Prompting Techniques**

### Zero-Shot Prompting
- No examples provided; model relies on its inherent understanding of the task.

### Few-Shot Prompting
- Provides task examples in the prompt, significantly improving performance.

**Best Prompt Template**:
```text
System: You are a Translator from English to Hindi:
User: What is the translation of the sentence given below?
[English]: <sentence>
[Hindi]:
```
---

## **Fine-Tuning with QLoRA**

### Techniques
- **PEFT (Parameter-Efficient Fine-Tuning)**: Focus on task-relevant parameters to reduce computational cost.
- **LoRA (Low-Rank Adaptation)**: Adjusts layer relevance dynamically during fine-tuning for efficient task adaptation.

---

## **Evaluation Details**

1. **Datasets**:
   - **Training**: Samanantar (English-Hindi pairs).
   - **Evaluation**: IIT-Bombay English-Hindi Corpus.

2. **Metric**:
   - BLEU Score (higher indicates better translation quality).
---

## **Results**

### Zero-Shot Evaluation (BLEU Scores)
| Model        | English → Hindi | Hindi → English |
|--------------|-----------------|-----------------|
| LLaMA 7B-Base | 5.58           | 6.98           |
| LLaMA 7B-Chat | 5.06           | 11.32          |
| OpenHathi     | 17.60          | 15.95          |

### Few-Shot Evaluation (LLaMA 7B-Base)
| Prompting Technique | English → Hindi | Hindi → English |
|----------------------|-----------------|-----------------|
| Two-Shot            | 6.98            | 9.11            |
| Four-Shot           | 8.32            | 8.82            |

### Fine-Tuning Results (English → Hindi, LLaMA 7B-Base)
| Training Examples | BLEU Score |
|--------------------|------------|
| 200                | 7.21       |
| 500                | 7.64       |
| 2500               | 8.34       |
| 10000              | 8.14       |

---

## **Acknowledgments**

- [AI4Bharat](https://ai4bharat.org/)
- [HuggingFace](https://huggingface.co/)
- [WMT](https://www.statmt.org/wmt23/)
