# Sentinel-AI

My AI document assistant.

## Overview

Sentinel-AI is an intelligent document assistant powered by AI. This project leverages modern web technologies and machine learning to provide smart document processing and analysis capabilities through RAG (Retrieval-Augmented Generation).

## Tech Stack

- **JavaScript** (79.1%) - Core application logic and frontend
- **CSS** (14.8%) - Styling and user interface
- **Python** (5.9%) - Backend AI/ML functionality
- **HTML** (0.2%) - Document structure

## APIs & External Services

### LLM & AI Services
- **OpenAI API** / **Anthropic Claude API** / **Google Gemini API** - For AI-powered document analysis and question answering
- **RAG (Retrieval-Augmented Generation)** - For intelligent document processing and context-aware responses

### Document Processing
- **PDF.js** - PDF rendering and page navigation
- **PyPDF2** / **pdfplumber** (Python) - PDF text extraction and processing
- **LangChain** - LLM orchestration and RAG pipeline management

### Embedding & Vector Search
- **OpenAI Embeddings API** / **Hugging Face Embeddings** - Text embedding generation
- **Pinecone** / **Weaviate** / **ChromaDB** - Vector database for document embeddings and similarity search
- **FAISS** (Facebook AI Similarity Search) - Fast similarity search for document retrieval

### Backend & APIs
- **FastAPI** (Python) - RESTful backend API for document upload and query processing
- **Flask** / **Django** (alternative Python frameworks)
- **Axios** - HTTP client for frontend-backend communication

## Main Tools & Libraries

### Frontend
- **React 19** - UI framework
- **Vite** - Build tool & dev server
- **Tailwind CSS** - Utility-first styling
- **Framer Motion** - Smooth animations and transitions
- **Lucide React** - Icon library
- **React Markdown** - Markdown rendering in chat responses
- **pdfjs-dist** - PDF viewer integration

### Backend
- **Python 3.x** - Backend runtime
- **FastAPI** - Web framework with automatic documentation
- **Uvicorn** - ASGI server
- **python-multipart** - File upload handling
- **CORS** - Cross-Origin Resource Sharing middleware
- **python-dotenv** - Environment variable management

### AI/ML & NLP
- **LangChain** - LLM framework and RAG implementation
- **OpenAI Python Library** - Direct API integration
- **sentence-transformers** - Text embedding models
- **scikit-learn** - Machine learning utilities
- **NumPy & Pandas** - Data processing

### Data Processing
- **PyPDF2** / **pdfplumber** - PDF text extraction
- **python-docx** - Document processing (future)

## Features

- 🤖 **AI-powered document processing** with RAG
- 📄 **Intelligent text analysis and extraction** from PDFs
- 🎯 **Student-level adaptive responses** (Class 4, 6, 8, 10)
- 💬 **Context-aware Q&A** with citation support
- 📊 **Document insights** (summary, topics, key terms)
- 🧪 **Interactive quiz generation** from document content
- 🔍 **Citation highlighting** with direct PDF navigation
- 🎨 **Premium UI/UX** with glassmorphism and animations
- 📱 **Responsive design** for all devices

## Getting Started

### Prerequisites

- Node.js 18+ and npm (for JavaScript dependencies)
- Python 3.8+ (for AI/ML backend)
- API keys:
  - OpenAI API key (or alternative LLM provider)
  - Vector database credentials (if using Pinecone/Weaviate)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Keertibhat327/Sentinel-AI.git
cd Sentinel-AI
```

2. Install JavaScript dependencies (frontend):
```bash
cd frontend_web
npm install
```

3. Install Python dependencies (backend):
```bash
cd ..
pip install -r requirements.txt
```

4. Set up environment variables:
```bash
cp .env.example .env
# Edit .env with your API keys
```

### Running the Application

**Backend (Terminal 1):**
```bash
cd backend
python main.py
# or with uvicorn
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

**Frontend (Terminal 2):**
```bash
cd frontend_web
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

## Project Structure

```
Sentinel-AI/
├── frontend_web/              # React frontend application
│   ├── src/
│   │   ├── components/        # Reusable React components
│   │   ├── App.jsx            # Main app container
│   │   ├── index.css          # Global styles
│   │   └── main.jsx           # React entry point
│   ├── package.json
│   └── vite.config.js
│
├── backend/                    # Python backend & AI logic
│   ├── main.py                # FastAPI app & endpoints
│   ├── rag_pipeline.py        # RAG implementation
│   ├── document_processor.py  # PDF processing
│   ├── embeddings.py          # Vector embeddings
│   └── requirements.txt       # Python dependencies
│
└── README.md
```

## API Endpoints

### Backend API

**Upload PDF**
```
POST /upload
Content-Type: multipart/form-data
Body: { file: <PDF file> }
Response: { message: "File uploaded successfully", file_id: "..." }
```

**Ask Question**
```
GET /ask?question=<question>&level=<student_level>
Response: {
  answer: "AI-generated answer...",
  citations: [5, 12, 18],
  confidence: 0.95
}
```

**Get Document Insights**
```
GET /insights/{file_id}
Response: {
  summary: "...",
  topics: [...],
  key_terms: [...],
  metadata: { pages: 10, ... }
}
```

## Configuration

### Environment Variables (.env)
```
OPENAI_API_KEY=your_api_key_here
PINECONE_API_KEY=your_api_key_here
PINECONE_ENVIRONMENT=your_environment
BACKEND_URL=http://localhost:8000
```

## Usage Example

1. **Upload a PDF** via drag-and-drop or file picker
2. **Select student level** (Class 4-10) for answer complexity
3. **Ask a question** about the document
4. **View AI response** with citations and insight cards
5. **Click citations** to navigate to source PDF pages
6. **Generate quiz** to test understanding with MCQs
7. **Review results** with instant feedback and scoring

## Contributing

Contributions are welcome! Please feel free to:
- Submit a Pull Request
- Open an issue for bugs or feature requests
- Fork and create your own branch

```bash
git checkout -b feature/YourFeatureName
git commit -m 'Add some AmazingFeature'
git push origin feature/YourFeatureName
```

## License

MIT License - Feel free to use this project for hackathons, projects, and portfolios.

## Support

If you encounter any issues or have questions:
1. Check the [troubleshooting section](#troubleshooting)
2. Open an issue on the [GitHub repository](https://github.com/Keertibhat327/Sentinel-AI/issues)
3. Contact the maintainers

## Troubleshooting

### "Backend connection failed"
- Ensure backend is running on `http://localhost:8000`
- Check CORS settings in `main.py`

### "API key error"
- Verify `.env` file has correct API keys
- Check API key permissions and quota limits

### "PDF not rendering"
- Ensure PDF upload was successful
- Check browser console for errors
- Verify PDF format compatibility

---

Made with ❤️ by Keertibhat327
