# interview_tasks


# Assistant for Multilingual Knowledge Extraction & Exploration

 The Bhagavad Gita in Gujarati/Sanskrit is the subject of this project, which creates an intelligent assistant that can comprehend, organize, and explore a scanned multilingual handwritten textbook.


 The issue of low-quality OCR and multilingual content is tackled by utilizing **GenAI tools + Retrieval-Augmented Generation (RAG)**.

 ---

 # Objectives

 Comprehend and organize OCR content from scanned PDFs in Gujarati or Sanskrit.
 Facilitate the investigation of natural language using semantic retrieval.
 Employ cutting-edge GenAI (Gemini 2.5 Flash) to enhance and purify retrieved text.
 Steer clear of superficial methods; give modularity, strategic rationale, and multilingual support top priority.

 ---


 ##  First Task: Understanding and Preprocessing Documents

 ###   ~Tesseract OCR` with Gujarati (`guj`) + Sanskrit support - `Gemini 2.5 Flash API` for text cleaning and reconstruction - ~geeta_cleaned_rotated_keys.md` for the final output

 ###  Why This Works: > The reviewer cautioned against using Tesseract exclusively superficially.  
 By **combining OCR with LLM cleaning**, we were able to resolve the issue and produce a structured output that was **high-quality** despite noise.

 ---

 ## Second Task: Chunking and Embedding Plan

 ###  The procedure involved loading the `.md` file, employing **structure-aware chunking** (`## Page`), and setting a word limit. Multilingual modeling was used for embedding.  
   **FAISS vector store** is where `paraphrase-multilingual-MiniLM-L12-v2` is kept.

 ### Why This Is Effective:  The reviewer requested multilingual support and careful chunking.  
 Using `sentence-transformers`, we provided **multilingual embeddings** and **semantic integrity** (overlap-based chunks).

 ---


 ## Task 3: Gemini RAG QA/Exploration

 ### Features: - The user can enter a question in any language; - FAISS retrieves the top k pieces
 Context-aware responses are generated using `Gemini-2.5-Flash`, which also shows answer and evidence chunks.

 ### Why This Is Effective:  The reviewer unjustly criticized fundamental RAG.  
 With complete transparency of the evidence retrieved, we developed a **clean semantic retriever + context-aware Gemini QA**.

 ---

 ## Results

- `geeta_cleaned_rotated_keys.md` — Cleaned OCR output
- `geeta_index.faiss` — FAISS vector index
- `geeta_chunks_metadata.json` — Chunk text lookup
- RAG Python script — Interactive user QA

 ---

 ## Upcoming Enhancements

 To sort the recovered chunks by relevance, add a reranker.
 Develop and perfect Sanskrit Q&A pairs. Release as the Streamlit/Gradio app.

 ---
