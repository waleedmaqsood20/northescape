# NorthEscape

![MIT License](https://img.shields.io/badge/license-MIT-green)
![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![PyTorch](https://img.shields.io/badge/pytorch-%3E%3D1.13-red)
![HuggingFace](https://img.shields.io/badge/huggingface-hub-orange)

## Project Overview

NorthEscape — Domain-Specific LLM Fine-Tuning for Northern Pakistan Travel Assistance.

This research project fine-tunes a Llama 3 (8B) base model with 4-bit quantization using LoRA (PEFT) and tools from Unsloth + HuggingFace TRL to build a conversational travel assistant for Northern Pakistan.

## Dataset

- Dataset: `Waleedai/north_escape`
- Hugging Face: https://huggingface.co/datasets/Waleedai/north_escape
- Size: 50,000 instruction-input-response examples

## Model Architecture

| Component | Details |
|---|---|
| Base model | Llama 3 8B (4-bit quantized) |
| Parameter-efficient fine-tuning | LoRA (PEFT) |
| Trainable parameters | 41.94 million |
| Quantization | 4-bit (bitsandbytes) |

## Training Configuration

| Hyperparameter | Value |
|---|---|
| Batch size | 2 |
| Gradient accumulation | 4 |
| LoRA rank (r) | 16 |
| LoRA alpha | 16 |
| Steps | 60 |
| Optimizer | AdamW (via accelerate/trl defaults) |
| Hardware | Tesla T4 (14.75 GB) |

## Results (Loss Trajectory)

| Step | Training Loss |
|---:|---:|
| 0 | 1.8194 |
| 60 | 0.9046 |

## Example Inference Outputs

Q: "What is the best time to visit Hunza Valley?"

A: "The best time to visit Hunza Valley is between May and September when the weather is mild and most roads are open. Late spring (May–June) and early autumn (September) are particularly pleasant, with blooming orchards and clear skies."

Q: "How can I travel from Islamabad to Skardu on a budget?"

A: "Budget travel options include taking a bus to Skardu (overnight services available) or flying during sales. For the most flexibility and cost savings, consider shared jeeps from Skardu bus terminal to local villages. Book in advance during peak seasons."

## Tech Stack

- Model & training: transformers, peft, trl, unsloth, bitsandbytes
- Data: datasets, huggingface_hub
- Compute: PyTorch, accelerate
- Application: Flutter (frontend conversational assistant)

## Author

- Waleed Maqsood
- LinkedIn: https://linkedin.com/in/waleed-maqsood1
- HuggingFace: https://huggingface.co/Waleedai
- GitHub: https://github.com/waleedmaqsood20
- University: University of Southern Queensland

## Files

- `notebook.ipynb` — Notebook with installation, dataset loading, training, and inference examples
- `requirements.txt` — Python dependencies
- `LICENSE` — MIT License

---

If you need the README adjusted (more detail in model architecture, an included paper citation section, or additional badges), tell me and it will be updated to research-quality standards.