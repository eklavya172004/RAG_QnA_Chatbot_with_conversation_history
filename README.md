# Conversational PDF RAG (Streamlit + Groq)

Ask questions about one or more PDFs with conversation history. This app builds a FAISS vector index from uploaded documents, rewrites follow-up questions using chat context, and answers with a Groq LLM.

## Features
- Multi-PDF upload and parsing
- Chunking + embeddings with Hugging Face
- FAISS vector store for retrieval
- History-aware retrieval for follow-up questions
- Streamlit chat UI

## Tech Stack
- Streamlit
- LangChain (classic chain APIs)
- Groq (ChatGroq)
- FAISS
- Hugging Face embeddings
- PyPDF

## Project Structure
```
5-conversationalPDF/
  app.py
  requirements.txt
  README.md
  .gitignore
```

## Requirements
- Python 3.11 or 3.12

## Setup (Local)
1. Create and activate a virtual environment.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file (not committed):
   ```env
   GROQ_API_KEY=your_groq_api_key
   HF_TOKEN=your_huggingface_token
   ```
4. Run the app:
   ```bash
   streamlit run app.py
   ```

## Usage
1. Enter your Groq API key in the UI.
2. Upload one or more PDF files.
3. Ask questions about the PDFs and keep asking follow-ups.

## Notes
- The app uses `temp_pdf.pdf` for uploads; it is ignored by `.gitignore`.
- If you deploy to Streamlit Cloud, set `GROQ_API_KEY` and `HF_TOKEN` in the app secrets.

## Deployment (Streamlit Cloud)
1. Push to GitHub.
2. Create a Streamlit Cloud app from the repo.
3. Set secrets:
   - `GROQ_API_KEY`
   - `HF_TOKEN`

## License
MIT
