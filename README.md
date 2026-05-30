# LangChain + Hugging Face RAG App

A simple question-answering app that reads a webpage and answers questions about it using open-source AI models.

---

## What it does

1. Loads a webpage
2. Breaks it into small chunks
3. Finds the most relevant chunks for your question
4. Uses Mistral AI to write an answer based on those chunks

---

## Before you start

You need:
- Python 3.9 or above
- A free [Hugging Face account](https://huggingface.co/) and an API token

---

## Getting started

**1. Clone the repo**
```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

**2. Install the required packages**
```bash
pip install langchain langchain-community langchain-text-splitters langchain-huggingface faiss-cpu python-dotenv
```

**3. Add your API key**

Create a file called `.env` in the project folder and add:
```
HUGGINGFACEHUB_API_TOKEN=your_token_here
```
Get your token from → https://huggingface.co/settings/tokens

---

## Run the notebook

```bash
jupyter notebook langchain_huggingface.ipynb
```

Then just run the cells from top to bottom. The last cell prints the answer to your question.

---

## Want to ask your own question?

- **Change the webpage** — edit the URL in cell 3
- **Change the question** — edit the `input` text in cell 8

---

## Common issues

| Problem | Fix |
|---|---|
| `401 Unauthorized` | Check your Hugging Face token in `.env` |
| Mistral returns empty output | Wait 30 sec and retry — the model may be loading |
| `faiss` won't install on Mac | Make sure you're using `faiss-cpu`, not `faiss-gpu` |

---

## Keep your token safe

Add this `.gitignore` so your secrets never get pushed to GitHub:
```
.env
.venv/
__pycache__/
.ipynb_checkpoints/
```
