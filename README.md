# 🤖 RAG Chatbot - Free, Local, Lightweight

A production-ready **Retrieval-Augmented Generation (RAG) chatbot** that runs 100% locally using free, open-source tools. Ask questions about your PDFs and documents with an AI assistant powered by Ollama and FAISS.

**Key Features:**
- ✅ 100% Local - No cloud APIs, no data leaves your machine
- ✅ Free - Uses only open-source software
- ✅ Lightweight - Works on standard laptops (8GB+ RAM)
- ✅ Simple UI - Built with Streamlit
- ✅ Multiple Models - Choose between Mistral, Neural Chat, or Llama2
- ✅ Source Attribution - See which documents the answer came from

---

## 🚀 Quick Start (5 minutes)

### 1️⃣ Install Python Dependencies
```bash
pip install -r requirements.txt
```

### 2️⃣ Install Ollama
1. Download from: https://ollama.ai
2. Install and run the application

### 3️⃣ Pull a Model
```bash
# Mistral 7B (recommended - fastest & good quality)
ollama pull mistral

# Alternatives:
ollama pull neural-chat    # Chat-optimized
ollama pull llama2         # Highest quality (but slower)
```

### 4️⃣ Start the Chatbot
```bash
streamlit run app.py
```

Open `http://localhost:8501` in your browser

### 5️⃣ Use the Chatbot
1. Upload PDFs or text files
2. Click "Process Files"
3. Ask questions in the chat box
4. Get answers with source documents!

---

## 📊 What's Inside

```
rag-chatbot/
├── app.py              # Main Streamlit application
├── config.py           # Advanced configuration & tuning
├── requirements.txt    # Python dependencies
├── SETUP.md           # Installation & setup guide
├── ADVANCED.md        # Advanced features & optimization
└── README.md          # This file
```

---

## 🎯 How It Works

```
1. Upload Documents (PDF/TXT)
   ↓
2. Split into chunks (500 chars each)
   ↓
3. Convert to embeddings (Sentence Transformers)
   ↓
4. Store in FAISS vector database
   ↓
5. User asks question
   ↓
6. Find 3 most similar chunks
   ↓
7. Send to LLM (Ollama)
   ↓
8. Generate answer based on context
   ↓
9. Show answer + source documents
```

---

## 💻 System Requirements

| Requirement | Minimum | Recommended |
|------------|---------|------------|
| RAM | 8GB | 16GB |
| Disk | 5GB | 10GB |
| Processor | Any | Modern CPU/GPU |
| Internet | For download only | For download only |

---

## 🛠️ Configuration

### Easy Options (in UI)
- Model Selection (Mistral, Neural Chat, Llama2)
- Temperature (0 = focused, 1 = creative)
- Embedding Model (MiniLM/MPNET/Multilingual)
- Retrieval Count (how many docs to use)

### Advanced Options (in `config.py`)
- Chunk size and overlap
- Custom prompts
- Memory optimization
- Performance tuning

See `ADVANCED.md` for detailed configuration guide.

---

## 🎓 Model Comparison

| Model | Speed | Quality | VRAM | Best For |
|-------|-------|---------|------|----------|
| **Mistral 7B** ⭐ | ⚡⚡⚡ Fast | Very Good | 4GB | General use |
| Neural Chat | ⚡⚡⚡ Fast | Good | 4GB | Chat-focused |
| Llama2 | ⚡ Slow | Excellent | 7GB | High quality |

**Recommendation**: Start with **Mistral 7B** - best balance of speed and quality.

---

## 🎨 Embedding Models

| Model | Speed | Quality | Best For |
|-------|-------|---------|----------|
| MiniLM-L6-v2 | ⚡⚡⚡ | Good | Quick demos |
| MPNET-base-v2 ⭐ | ⚡⚡ | Very Good | General use |
| Distiluse-multilingual | ⚡⚡ | Excellent | Multiple languages |

---

## 🔍 Example Queries

```
📚 Research Paper:
"What are the main findings of this paper?"
"What methodology was used?"

📖 Book:
"Summarize chapter 3"
"What happens to the main character?"

📄 Technical Docs:
"How do I set up the API?"
"What are the system requirements?"

⚖️ Legal Document:
"What are my obligations?"
"What are the termination clauses?"
```

---

## ⚙️ Troubleshooting

### "Connection refused"
```bash
# Make sure Ollama is running
# Check if it's accessible: http://localhost:11434
```

### "Very slow responses"
1. Switch to Mistral model (faster)
2. Reduce retrieval count to 2
3. Use MiniLM embeddings
4. Check CPU/RAM usage

### "Model not found"
```bash
ollama list  # Check installed models
ollama pull mistral  # Download the model
```

See `SETUP.md` for complete troubleshooting guide.

---

## 🚀 Performance Tips

### For Speed (< 10 seconds per query)
```
Model: Mistral
Embedding: MiniLM-L6-v2
Chunk size: 400
Retrieved docs: 2
```

### For Quality (best answers)
```
Model: Llama2
Embedding: MPNET-base-v2
Chunk size: 600
Retrieved docs: 5
```

### For Low Memory (< 8GB)
```
Model: Mistral
Embedding: MiniLM-L6-v2
Chunk size: 300
Retrieved docs: 2
```

---

## 🔒 Privacy & Security

✅ **Fully Private** - All processing happens on your machine  
✅ **No Tracking** - No analytics or telemetry  
✅ **No Cloud** - Documents never leave your computer  
✅ **Open Source** - Inspect the code yourself  
✅ **Free** - No hidden costs or subscriptions  

---

## 📚 What is RAG?

**RAG = Retrieval-Augmented Generation**

Instead of relying on the LLM's training data, RAG:
1. **Retrieves** relevant document chunks
2. **Augments** the prompt with this context
3. **Generates** an answer based on actual documents

**Why RAG is better:**
- ✅ Answers based on your actual documents
- ✅ Lower hallucination rate
- ✅ Can use smaller, faster models
- ✅ Works with private data
- ✅ Easy to update (just upload new docs)

---

## 🚨 Common Mistakes

❌ Not keeping Ollama running in background  
❌ Uploading duplicates or irrelevant documents  
❌ Using very large chunk sizes (>1000)  
❌ Expecting 100% accuracy (RAG is ~85-95%)  
❌ Not checking source documents  
❌ Running on very old machines  

---

## 💡 Pro Tips

1. **Experiment** - Try different models, find best for your docs
2. **Clean Documents** - Good input = good answers
3. **Chunk Overlap** - Prevents cutting important info
4. **Check Sources** - Always verify answers in source docs
5. **Custom Prompts** - Tailor for your specific domain

---

## 🔗 Resources

- **Ollama**: https://ollama.ai
- **LangChain**: https://python.langchain.com
- **Sentence Transformers**: https://www.sbert.net
- **FAISS**: https://faiss.ai

---

## 📝 Next Steps

1. **Install** - Follow Quick Start above
2. **Test** - Upload a sample PDF
3. **Experiment** - Try different models
4. **Read** - Check `SETUP.md` and `ADVANCED.md`
5. **Optimize** - Use `config.py` to tune for your needs

---

## 🎯 Use Cases

- 📚 **Research** - Analyze papers, extract findings
- 📖 **Reading** - Summarize books, find information
- 🔧 **Technical** - Browse documentation, code examples
- ⚖️ **Legal** - Review contracts, understand clauses
- 🎓 **Education** - Study materials, practice questions
- 💼 **Work** - Analyze reports, meeting notes

---

## 📞 Help & Support

- Check `SETUP.md` for installation help
- Check `ADVANCED.md` for optimization tips
- Check `config.py` for detailed parameters
- Review error messages - they usually point to the solution

---

## 🎉 Ready to Start?

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Start Ollama application
# (Download from https://ollama.ai)

# 3. Pull a model
ollama pull mistral

# 4. Run the chatbot
streamlit run app.py

# 5. Open http://localhost:8501
```

**That's it! Start chatting with your documents!** 🚀

---

## 📄 License

This project uses open-source libraries under their respective licenses:
- LangChain (MIT)
- Ollama (MIT)
- FAISS (MIT)
- Streamlit (Apache 2.0)
- Sentence Transformers (Apache 2.0)

---

**Made with ❤️ using free, open-source tools**

*Happy chatting! 🤖*
