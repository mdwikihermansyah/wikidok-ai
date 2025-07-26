# 🚀 Panduan Setup Wiki Chatbot wit RAG & Langchain

## 📋 Overview

Project ini adalah RAG (Retrieval Augmented Generation) chatbot yang menggunakan Langchain, OpenAI, Google Generative AI, dan HuggingFace APIs. Anda dapat mengupload dokumen dalam format PDF, TXT, CSV, atau DOCX dan chatting dengan AI yang akan memberikan jawaban berdasarkan dokumen Anda.

## 🛠️ Setup Project

### 1. Prerequisites

- Python 3.13+ (sudah terinstall)
- macOS (sudah dikonfigurasi)

### 2. Setup Virtual Environment

```bash
# Buat virtual environment
python3 -m venv langchain_env

# Aktifkan virtual environment
source langchain_env/bin/activate
```

### 3. Install Dependencies

```bash
# Install dependencies yang sudah diupdate
pip install -r requirements_updated.txt

# Install langchain-cohere untuk CohereRerank
pip install langchain-cohere
```

### 4. Setup Direktori

```bash
# Buat direktori yang diperlukan
mkdir -p data/tmp
```

### 5. API Keys Configuration

Anda perlu menambahkan API keys di sidebar aplikasi:

#### ✅ COHERE_API_KEY (Sudah ditambahkan)

- Untuk menggunakan Cohere reranker
- Model yang digunakan: `rerank-english-v2.0`

#### 🔑 API Keys Lainnya (Opsional)

- **OpenAI API Key**: Untuk menggunakan GPT-3.5, GPT-4
- **Google API Key**: Untuk menggunakan Gemini-pro
- **HuggingFace API Key**: Untuk menggunakan Mistral-7B-Instruct-v0.2

### 6. Menjalankan Aplikasi

```bash
# Aktifkan virtual environment
source langchain_env/bin/activate

# Jalankan aplikasi
streamlit run RAG_app.py --server.port 8501
```

Aplikasi akan berjalan di:

- **Local URL**: http://localhost:8501
- **Network URL**: http://192.168.223.208:8501

## 🎯 Cara Menggunakan

### 1. Konfigurasi LLM Provider

Di sidebar aplikasi:

1. Pilih LLM provider (OpenAI, Google Generative AI, atau HuggingFace)
2. Pilih model yang sesuai
3. Atur parameter (temperature, top_p)
4. Masukkan API key yang diperlukan

### 2. Upload Dokumen

- Klik tab "Upload Documents"
- Upload file PDF, TXT, CSV, atau DOCX
- Pilih retriever type:
  - **Cohere reranker**: Menggunakan Cohere untuk re-ranking hasil
  - **Contextual compression**: Kompresi kontekstual
  - **Vectorstore backed retriever**: Retrieval langsung dari vectorstore

### 3. Load Vectorstore (Alternatif)

- Klik tab "Open Vectorstore"
- Masukkan path ke direktori vectorstore yang sudah ada
- Contoh: `/path/to/your/vectorstore`

### 4. Mulai Chatting

- Setelah dokumen diupload atau vectorstore diload
- Mulai bertanya di chat interface
- AI akan memberikan jawaban berdasarkan dokumen Anda

## 🔧 Fitur Utama

### 📄 Document Processing

- **Supported Formats**: PDF, TXT, CSV, DOCX
- **Text Splitting**: Recursive character text splitter
- **Embeddings**: OpenAI, Google, HuggingFace embeddings

### 🤖 LLM Providers

- **OpenAI**: GPT-3.5-turbo, GPT-4-turbo-preview
- **Google**: Gemini-pro
- **HuggingFace**: Mistral-7B-Instruct-v0.2

### 🔍 Retrieval Methods

- **Cohere Reranker**: Re-ranking hasil dengan Cohere
- **Contextual Compression**: Kompresi dokumen kontekstual
- **Vectorstore Retrieval**: Retrieval langsung dari ChromaDB

### 💾 Vector Store

- **ChromaDB**: Vector database untuk menyimpan embeddings
- **Persistence**: Vectorstore disimpan di `data/vector_stores/`
- **Reusability**: Dapat diload kembali tanpa re-processing

### 🌐 Multi-language Support

- English, French, Spanish, German, Russian, Chinese, Arabic, Portuguese, Italian, Japanese

## 🐛 Troubleshooting

### Error: "No module named '\_tkinter'"

- **Solution**: Sudah diperbaiki dengan mengganti tkinter dengan text input

### Error: "Directory not found: data/tmp"

- **Solution**: Buat direktori dengan `mkdir -p data/tmp`

### Error: "model 'rerank-multilingual-v2.0' not found"

- **Solution**: Sudah diperbaiki menggunakan `rerank-english-v2.0`

### Warning: CohereRerank deprecation

- **Solution**: Sudah diperbaiki menggunakan `langchain-cohere`

### Warning: Memory deprecation

- **Solution**: Sudah diperbaiki menggunakan `langchain_core.memory`

## 📁 Struktur Project

```
RAG_chatabot_with_Langchain-main/
├── RAG_app.py                 # Aplikasi utama Streamlit
├── requirements_updated.txt   # Dependencies yang diupdate
├── requirements.txt          # Dependencies original
├── README.md                 # Dokumentasi original
├── SETUP_GUIDE.md           # Panduan setup ini
├── data/
│   ├── docs/                # Dokumen contoh
│   ├── tmp/                 # File temporary
│   └── vector_stores/       # Vectorstore yang disimpan
└── langchain_env/           # Virtual environment
```

## 🎉 Selamat Menggunakan!

Aplikasi RAG chatbot Anda sudah siap digunakan. Upload dokumen, konfigurasi LLM provider, dan mulai chatting dengan AI assistant yang akan memberikan jawaban akurat berdasarkan dokumen Anda!
