
# modelcli

`modelcli` is a universal command-line interface (CLI) that lets you interact with **any LLM model** (local or cloud) through a unified prompt interface. It supports OpenAI-compatible APIs, LM Studio, Ollama, OpenRouter, and more.

---

## 🚀 Installation

```bash
pip install modelcli
```

Or clone this repo and install locally:

```bash
git clone https://github.com/Tomigambii/modelcli.git
cd modelcli
pip install .
```

---

## ⚙️ Configuration

### Add your first model (auto-sets as default)

```bash
modelcli configure-model \
  --name mistral-local \
  --url http://localhost:11434/v1/chat/completions \
  --key none \
  --model mistral
```

Fields:
- `--name`: internal alias
- `--url`: model endpoint (OpenAI-compatible)
- `--key`: API key (use `none` if not needed)
- `--model`: actual model name (e.g., `gpt-4`, `mistral`, `llama3`)

---

## ✨ Features

### 🔹 Basic Commands

```bash
modelcli summarize "Long text here..."
modelcli translate "Hola mundo"
modelcli email "Meeting was canceled" --tone formal
```

> `translate` uses the default language (see `set-language` below)

---

### 🔹 Custom Prompts (Default Mode)

Just type your prompt directly:
```bash
modelcli "Give me 3 startup ideas using AI in education"
```

---

### 🔹 Set Defaults

```bash
modelcli set-default --name mistral-local         # set default model
modelcli set-language --to german                 # set default target language for translate
```

---

### 🔹 Aliases

```bash
modelcli alias --for mistral-long-name --as mistral
```

Then:
```bash
modelcli --model mistral "Summarize this paragraph..."
```

---

### 🔹 Model Management

```bash
modelcli list-models
modelcli remove-model --name mistral-local
```

---

## 📌 Global Options

```bash
modelcli --version               # prints current version
modelcli "your prompt here"     # sends directly as a custom prompt
```

---

## ✅ Examples

### Translate using default model and language
```bash
modelcli translate "Buenos días"
```

### Change model for one request
```bash
modelcli translate "Bonjour tout le monde" --model llama3
```

---


## 🤝 Contributing

Feel free to open pull requests or issues.

---

## 📜 License

MIT License © 2024 Tomás Gambirassi
