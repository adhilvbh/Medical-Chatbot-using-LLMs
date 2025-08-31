# 🩺 Medical Chatbot using LLMs

A powerful, customizable AI chatbot for answering medical questions, built with Large Language Models (LLMs), semantic vector search, and PDF document ingestion. Instantly turn your medical PDFs into a conversational knowledge base, accessible via a modern web interface.

---

## ✨ Key Features

- **Conversational Chatbot UI**: Clean, responsive web interface for seamless interaction.
- **PDF Knowledge Ingestion**: Effortlessly add and index your own medical PDFs.
- **Semantic Search**: Retrieves the most relevant information using HuggingFace embeddings and Pinecone vector store.
- **LLM-Powered Answers**: Generates natural, context-aware responses with OpenAI GPT models.
- **Customizable Prompts**: Tailor system and user prompts for your specific use-case.
- **Cloud & Serverless Ready**: Easily deployable on AWS, Azure, or any cloud platform.
- **Quick Setup**: Minimal configuration—get started in minutes!

---

## 🗂️ Project Structure

```
.
├── app.py                # Flask app for chatbot UI and API
├── store_index.py        # Script to process PDFs and build Pinecone index
├── src/
│   ├── helper.py         # PDF loading, text splitting, embeddings
│   ├── prompt.py         # Prompt templates for LLM
│   └── __init__.py
├── data/
│   └── Medical_book.pdf  # Example medical PDF
├── templates/
│   └── chat.html         # Chatbot web UI
├── static/
│   └── style.css         # Custom styles for chat UI
├── requirements.txt      # Python dependencies
├── .env                  # API keys and environment variables
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```sh
git clone https://github.com/yourusername/Medical-Chatbot-using-LLMs.git
cd Medical-Chatbot-using-LLMs
```

### 2. Install Dependencies

It’s recommended to use a virtual environment:

```sh
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Set Up Environment Variables

Create a `.env` file in the project root:

```
OPENAI_API_KEY=your-openai-api-key
PINECONE_API_KEY=your-pinecone-api-key
```

### 4. Add Your Medical PDFs

Place your PDF files in the `data/` directory.

### 5. Build the Vector Index

```sh
python store_index.py
```

### 6. Start the Chatbot Web App

```sh
python app.py
```

Visit [http://localhost:8080](http://localhost:8080) in your browser.

---

## 🧠 How It Works

1. **PDF Ingestion**: PDFs are loaded and split into chunks (`src/helper.py`).
2. **Embeddings**: Each chunk is embedded using HuggingFace models.
3. **Vector Store**: Embeddings are stored in Pinecone for fast semantic search.
4. **Retrieval-Augmented Generation**: User questions trigger retrieval of relevant chunks, which are passed to OpenAI GPT for answer generation.
5. **Web UI**: Users interact with the chatbot via a modern chat interface.

---

## 🛠️ Customization

- **Prompts**: Edit [`src/prompt.py`](src/prompt.py) to change system/user prompts.
- **PDFs**: Add or replace files in `data/` and re-run `store_index.py`.
- **Models**: Change HuggingFace or OpenAI models in [`src/helper.py`](src/helper.py) and [`app.py`](app.py).

---

## 💡 Example Questions

- “What are the symptoms of diabetes?”
- “Explain the treatment for hypertension.”
- “How is asthma diagnosed?”

The chatbot will retrieve relevant information from your PDFs and generate a clear, concise answer.

---

## 🤝 Contributing

Contributions are welcome! Please open an issue to discuss your ideas or submit a pull request.

---

## 📜 License

Licensed under the [Apache 2.0 License](LICENSE).

---

## 🙏 Acknowledgements

- [LangChain](https://github.com/langchain-ai/langchain)
- [OpenAI](https://openai.com/)
- [Pinecone](https://www.pinecone.io/)
- [HuggingFace](https://huggingface.co/)

---

> **Disclaimer:** This chatbot is for informational purposes only and should not be used as a substitute for professional medical advice.