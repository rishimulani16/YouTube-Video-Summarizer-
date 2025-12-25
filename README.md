
## 🚀 Features

- ✅ **Auto Transcript Fetching** - `youtube-transcript-api`
- ✅ **Smart Chunking** - 1000 chars/chunk, 200 overlap
- ✅ **Vector Search** - OpenAI embeddings + FAISS
- ✅ **Q&A + Summarization** - GPT-4o-mini powered
- ✅ **Production Chains** - RunnableParallel for clean pipelines
- ✅ **Error Handling** - Missing transcripts, context limits

## 🤔 Why RAG?

**Problem**: LLMs hallucinate on unseen video content. Stuff entire transcripts → hit token limits.

**Solution**: RAG retrieves **only relevant chunks** (k=4) for precise answers.

| Approach | Accuracy | Cost | Long Videos |
|----------|----------|------|-------------|
| Full Transcript | ❌ Hallucinations | 💰 Expensive | ❌ Token Limit |
| **RAG (This)** | ✅ Grounded | 💵 Cheap | ✅ Scalable |

**Key Wins**:
- Pinpoint answers to niche questions
- No model fine-tuning needed
- Cross-video knowledge bases

## 🛠 Quick Start

### 1. Setup
pip install youtube-transcript-api langchain-community langchain-openai faiss-cpu tiktoken python-dotenv langchain-text-splitters


### 2. Environment
export OPENAI_API_KEY="sk-..."


### 3. Run
From langchain_rag.ipynb
video_id = "Gfr50f6ZBvo" # Extract from any YouTube URL
chain.invoke("Your question here")


## 🏗 Architecture
graph TD
A[YouTube URL] --> B[Fetch Transcript]
B --> C[Recursive Splitter
1000/200 overlap]
C --> D[OpenAI Embeddings]
D --> E[FAISS VectorStore]
F[User Question] --> G[Retriever k=4]
G --> H[RAG Chain]
H --> I[GPT-4o-mini]
I --> J[Grounded Answer]


## 🎯 Use Cases

- **Research**: Query academic lectures, interviews
- **Education**: Build Q&A from course videos
- **Content**: Auto-summarize podcasts
- **Analysis**: Extract insights from long-form content

## Future Implementation 

- UI Based Enhancement
- Evalution with Ragas or LangSmith
- More powerful Indexing and Retrieving
- Add Multimodel and Agentic features
