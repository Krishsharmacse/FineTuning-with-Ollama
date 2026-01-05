# Fine-Tuning with Ollama (GGUF-safe Repository)

This repository demonstrates **fine-tuning a lightweight LLM and running it with Ollama**, while following best practices for GitHub (⚠️ **no large model files committed**).

The goal of this project is to:

* Fine-tune an LLM locally (CPU-friendly workflow)
* Convert the fine-tuned model to **GGUF** format
* Run and test the model using **Ollama**
* Keep the GitHub repo clean (code-only, no heavy artifacts)

---

## 🚀 Features

* Local fine-tuning workflow (no mandatory GPU)
* GGUF model support for Ollama
* Clean Git history (models excluded)
* Beginner-friendly and reproducible

---

## 📂 Project Structure

```
FineTuning-with-Ollama/
│
├── endtoend_finetunning.ipynb   # Complete fine-tuning pipeline
├── ollama-test/                # Ollama-related configs (no models)
├── .gitignore                  # Ignores GGUF & large model files
├── README.md                   # Project documentation
└── requirements.txt            # Python dependencies (optional)
```

> ⚠️ **Important:** `.gguf`, `.bin`, and `.safetensors` files are intentionally ignored and must NOT be committed.

---

## 🧠 Workflow Overview

1. **Prepare Dataset**

   * Load and preprocess training data

2. **Fine-tune Base Model**

   * Uses lightweight LLM (e.g., TinyLLaMA)
   * CPU-compatible (slow but works)

3. **Export to GGUF**

   * Convert HuggingFace model → GGUF

4. **Run with Ollama**

   * Create Modelfile
   * Run locally using `ollama run`

---

## 🧪 Fine-Tuning Notebook

The full pipeline is implemented in:

```
endtoend_finetunning.ipynb
```

This notebook includes:

* Environment setup
* Model loading
* Training loop
* GGUF conversion
* Ollama testing

---

## 🦙 Running with Ollama

Example Modelfile:

```text
FROM ./model.gguf

PARAMETER temperature 0.7
PARAMETER top_p 0.9
```

Build and run:

```bash
ollama create my-model -f Modelfile
ollama run my-model
```

---

## 🧾 GitHub Safety Rules

This repo follows **strict GitHub-safe rules**:

```gitignore
*.gguf
*.bin
*.safetensors
__pycache__/
venv/
.env
```

Large models should be stored **locally or externally**, not in Git.

---

## 📦 Model Storage (Recommended)

Store trained models using:

* Local disk
* External drive
* Hugging Face Hub (private/public)

GitHub = **code only** ✅

---

## 🛠 Requirements

* Python 3.9+
* Ollama
* llama.cpp
* PyTorch
* transformers

Install Ollama:
👉 [https://ollama.com](https://ollama.com)

---

## 👨‍💻 Author

**Krish Sharma**
AI / ML Engineer

---

## 📜 License

This project is for educational and research purposes.

---

⭐ If this repo helped you, consider giving it a star!
