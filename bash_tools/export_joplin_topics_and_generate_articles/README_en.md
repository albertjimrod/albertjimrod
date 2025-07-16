
# 🧠 Technical Article Generator with AI (Ollama + LLMs)

This script automates the conversion of technical Markdown notes into clear, educational, and accessible articles using local large language models (LLMs) via [Ollama](https://ollama.com/).

---

## ✨ Why use this script?

In the fields of data science, data engineering, and machine learning, it’s common to produce large amounts of technical notes in `.md` files. However, these notes aren’t always suitable for broader audiences (e.g., blog readers, non-technical colleagues, or students).

This script solves that:

✅ Converts technical notes into readable, engaging articles  
✅ Uses your own GPU/server via [Ollama](https://ollama.com/)  
✅ No need for cloud APIs or external services  
✅ Works with multiple models like `llama3`, `deepseek`, `mistral`, etc.

---

## 🚀 How it works

1. **Input**: A directory containing `.md` files with technical content.
2. **Processing**: It walks through each file recursively, creates an instructive prompt, and sends it to Ollama’s `/api/chat` endpoint.
3. **Output**: A new `_articulo.md` file is generated with accessible, well-structured article content and saved in a `_processed` directory.

---

## 🛠️ Requirements

- A working installation of [Ollama](https://ollama.com/)
- Downloaded LLMs (e.g., `deepseek-r1:14b`)
- Python 3.7+
- `curl` installed (used internally to call the Ollama API)

---

## 📦 Installation

```bash
git clone git@github.com:albertjimrod/bash_tools.git
cd article-generator-ollama