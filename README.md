# 🎓 Student Policy AI Assistant – RAG Chatbot

An AI-powered Student Policy Assistant that helps students quickly find answers to questions about academic rules, attendance, examinations, assignments, fees, scholarships, and other institutional policies.

This project uses **Retrieval-Augmented Generation (RAG)** to retrieve relevant information from a Student Policy Handbook PDF and generate context-based answers using a Large Language Model (LLM).

## 🚀 Features

- **PDF-Based Question Answering:** Ask questions about the Student Policy Handbook.
- **Retrieval-Augmented Generation (RAG):** Retrieves relevant document chunks before generating answers.
- **Semantic Search:** Uses Hugging Face sentence embeddings to understand user queries.
- **FAISS Vector Database:** Stores and searches document embeddings efficiently.
- **Groq LLM Integration:** Generates responses using the `openai/gpt-oss-20b` model through Groq.
- **Interactive Chat Interface:** User-friendly chatbot built with Streamlit.
- **Source Transparency:** Displays retrieved document content and page numbers.
- **Suggested Questions:** Provides commonly asked student policy questions.
- **Chat History:** Maintains conversation messages during the Streamlit session.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Backend development |
| LangChain | RAG workflow |
| Streamlit | Frontend interface |
| Groq API | LLM-powered responses |
| Hugging Face | Text embeddings |
| FAISS | Vector database |
| PyPDF | PDF document loading |
| Sentence Transformers | Text embedding model |

## 📁 Project Structure

```text
student-policy-ai-assistant/
│
├── data/
│   └── student_policy_handbook.pdf
│
├── vectorstore/
│   ├── index.faiss
│   └── index.pkl
│
├── ingest.py
├── chatbot.py
├── app.py
├── .env
├── .gitignore
├── requirements.txt
└── README.md
```

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/student-policy-ai-assistant.git
```

```bash
cd student-policy-ai-assistant
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the Groq API Key

Create a `.env` file in the project root directory.

```env
GROQ_API_KEY=your_groq_api_key
```

Get your API key from [Groq Console](https://console.groq.com/).

### 5. Prepare the Vector Database

Place your Student Policy Handbook PDF inside the `data/` folder.

Run:

```bash
python ingest.py
```

This process:
1. Loads the PDF document.
2. Splits the document into smaller text chunks.
3. Generates embeddings using Hugging Face.
4. Stores the embeddings in a FAISS vector database.

### 6. Run the Application

```bash
streamlit run app.py
```

Open the application in your browser:

```text
http://localhost:8501
```

## 🔄 How It Works

```text
       Student Policy PDF
                |
                v
           ingest.py
                |
                v
       Load and Split PDF
                |
                v
      Hugging Face Embeddings
                |
                v
         FAISS Vector Store
                |
                v
       Student Enters Question
                |
                v
         chatbot.py
                |
                v
       Retrieve Relevant Chunks
                |
                v
          Groq LLM
                |
                v
       Generate Context-Based Answer
                |
                v
        Streamlit Chat Interface
```

## 💬 Example Questions

Students can ask questions such as:

- What is the minimum attendance requirement?
- How can I apply for leave?
- What are the examination rules?
- What is the fee refund policy?
- How can I apply for scholarships?
- What are the library rules?
- What are the placement eligibility requirements?

## 🔐 Security

- Store API keys in environment variables.
- Do not upload `.env` files or expose API keys on GitHub.
- Keep sensitive credentials outside the source code.

