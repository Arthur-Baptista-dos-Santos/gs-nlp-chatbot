# `gs-nlp-chatbot: RAG para Edificios Net Zero`

> Sistema RAG (Retrieval-Augmented Generation) para consulta de normas de sustentabilidade em edificios Net Zero. LangChain + FAISS + embeddings HuggingFace. Global Solution 2026.1, FIAP.

---

## `Tecnologias`

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![LangChain](https://img.shields.io/badge/LangChain-RAG-1C3C3C)
![FAISS](https://img.shields.io/badge/FAISS-vector%20search-orange)
![HuggingFace](https://img.shields.io/badge/HuggingFace-embeddings-yellow)
![Colab](https://img.shields.io/badge/Google%20Colab-GPU-F9AB00)
![License](https://img.shields.io/badge/license-MIT-green)

---

## `O que faz`

Assistente conversacional para normas e praticas de edificios sustentaveis: LEED, BREEAM, ABNT NBR 15575, requisitos de Net Zero Carbon. O usuario faz perguntas em linguagem natural e o sistema recupera passagens relevantes dos documentos e gera respostas fundamentadas.

---

## `Pipeline RAG`

```
Documentos PDF/TXT (normas LEED, BREEAM, ABNT)
    |
    Chunking: RecursiveCharacterTextSplitter
        chunk_size=500, overlap=50
    |
    Embeddings: sentence-transformers (multilingual-mpnet-base-v2)
        Dim: 768 · pt-BR nativo
    |
    VectorStore: FAISS (IndexFlatIP, busca por cosseno)
        Persistido localmente, sem servidor
    |
    Retriever: top-k=4 chunks mais similares
    |
    LLM: Ollama (llama3) local OU HuggingFace Hub
    |
    RetrievalQA Chain (LangChain)
        Prompt: contexto + pergunta → resposta fundamentada
```

---

## `Metricas`

| Metrica | Valor |
|---------|-------|
| Precisao de recuperacao | ~90% (top-4 relevantes) |
| Latencia media (GPU Colab) | < 3s por query |
| Documentos indexados | 8 normas tecnicas |
| Chunks gerados | ~1.200 |
| Modelo de embedding | multilingual-mpnet-base-v2 |

---

## `Arquivos`

| Arquivo | Descricao |
|---------|---------|
| `gs_nlp_rag_netzero.ipynb` | Pipeline RAG completo com exemplos de queries |
| `relatorio_gs_nlp.pdf` | Relatorio tecnico ABNT (arquitetura, resultados, limitacoes) |
| `requirements.txt` | Dependencias do projeto |

---

## `Como executar`

```bash
# Google Colab (recomendado: GPU T4)
# 1. Abra gs_nlp_rag_netzero.ipynb no Colab
# 2. Runtime > Change runtime type > GPU

# Ou localmente:
pip install langchain faiss-cpu sentence-transformers
# Configure HUGGINGFACEHUB_API_TOKEN no .env
```

---

## `Contexto: Global Solution 2026.1`

Projeto integrador da FIAP 2026.1, tema: **Monitoramento Espacial e Sustentabilidade Ambiental**.

Este chatbot e o componente de PLN/NLP da solucao multi-disciplinar GPOS (Global Project Operating System):

```
gs-nlp-chatbot        → RAG para normas de sustentabilidade (este repo)
gs-quantum-computing  → QSVC para anomalias em telemetria de satelites
gs-neuromorphic-cluster → Computacao neuromorfica com redes LIF
gs-wildfire-vision    → Deteccao de incendios por visao computacional
iot-space-launch-monitor → IoT de monitoramento de lancamentos
space-rag-assistant   → RAG para nova economia espacial
```

---

## `Conceitos aplicados`

- **`RAG`**: combina recuperacao semantica (FAISS) com geracao de texto (LLM) para respostas fundamentadas em documentos
- **`FAISS IndexFlatIP`**: busca exata por produto interno (equivalente a cosseno em vetores normalizados)
- **`sentence-transformers`**: modelos pre-treinados para embeddings de sentencas com suporte multilingual
- **`LangChain RetrievalQA`**: abstrai o pipeline RAG: retriever + prompt template + LLM em uma chain

---

## `Licenca`

Distribuido sob a licenca MIT.

---

## `Autor`

**Arthur Baptista dos Santos**
RM 565346 · Inteligencia Artificial · FIAP 2025-2026

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Arthur%20Baptista-0077B5?logo=linkedin)](https://linkedin.com/in/arthur-baptista-dos-santos)
[![GitHub](https://img.shields.io/badge/GitHub-Arthur--Baptista--dos--Santos-181717?logo=github)](https://github.com/Arthur-Baptista-dos-Santos)