

# 🧠 Local LLM Playground with Ollama

![Ollama Logo](https://ollama.com/public/ollama.png)

## Get started with large language models (LLMs) — locally, efficiently, and for free.

Run powerful open-source models like **Llama 3.3**, **DeepSeek-R1**, **Qwen 3**, **Qwen 2.5-VL**, **Gemma 3**, and more — directly on your machine using [**Ollama**](https://ollama.com).

---

## ✨ Features

- Run large language models **locally** without relying on cloud APIs  
- Supports macOS, Linux, and Windows  
- Easy-to-use CLI interface  
- Compatible with popular frameworks and tools  
- Works with multiple models including:
  - `llama3`
  - `deepseek-r1`
  - `qwen`
  - `gemma`
  - `mistral`
  - `phi3`
  - ...and many more!

---

## 🛠️ Included Script: Conda Environment Inspector

This repository includes a **Bash script** to inspect the **size and contents of an active Conda environment**, especially useful when working with large AI/ML libraries.

### 🔍 What it does:

- Checks if **Conda is installed and available**
- Verifies that a **Conda environment is active**
- Locates the `site-packages` directory of the current environment
- Lists the **largest installed packages** by disk usage (top 50)
- Helps identify **which packages are taking up the most space**

### 💡 Why use it?

- Understand what’s installed in your environment
- Optimize storage when working with heavy ML libraries (e.g., PyTorch, TensorFlow)
- Clean up unused or oversized packages

---

## 🚀 How to Use

Make sure you have [Ollama installed](https://ollama.com/download) on your system. Then, pull and run any model:

```bash
ollama pull llama3
ollama run llama3
```

You can also interact with the model via the API:

```bash
curl http://localhost:11434/api/generate -d '{
  "model": "llama3",
  "prompt": "Explain quantum computing in simple terms."
}'
```

To run the **Conda environment inspector script**:

```bash
# Activate your conda environment first
conda activate your_env_name

# Then run the script
./inspect_conda_env.sh
```

---

## 📦 Installation

### macOS / Linux

Download and install from [Ollama's official site](https://ollama.com/download), then verify installation:

```bash
ollama --version
```

### Windows

Ollama is available for Windows via the installer or using WSL2.

---

## 🧩 Example Models

| Model       | Description                              |
|-------------|------------------------------------------|
| `llama3`    | Meta's latest open LLM, great for general tasks |
| `deepseek-r1` | Strong coding and math capabilities         |
| `qwen`      | Developed by Alibaba, supports multilingual tasks |
| `gemma`     | Lightweight models from Google             |
| `mistral`   | High performance on reasoning tasks        |

---

## 🔧 Want to Build Something?

Use this base to build:
- AI-powered documentation generators
- Code assistants
- Personalized chatbots
- Data analysis tools
- Educational content creators

---

## 📚 Resources

- [Ollama Documentation](https://ollama.com)
- [Model Library](https://ollama.com/library)
- [GitHub Repo](https://github.com/ollama/ollama)

---