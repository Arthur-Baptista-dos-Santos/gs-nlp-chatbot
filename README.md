# Assistente Técnico para Projetos de Edifícios Eficientes quanto a Água e Energia

**Disciplina:** Processamento de Linguagem Natural, Chatbots & Virtual Agents  
**Instituição:** FIAP — Faculdade de Informática e Administração Paulista  
**Professor:** Sérgio Palmiere  

## Integrantes

| Nome | RM |
|------|----|
| Arthur Baptista dos Santos | 565346 |
| João Pedro de Moura Dutra Franco | 561738 |
| Nelson Félix Neto | 565603 |

---

## Sobre o Projeto

Sistema RAG (Retrieval-Augmented Generation) especializado em **edifícios verdes e Net Zero de energia e água**, capaz de responder perguntas técnicas com precisão citando obrigatoriamente a fonte de cada informação.

O pipeline foi construído integralmente em ambiente local, sem dependência de APIs externas pagas, utilizando:

- **LLM:** Qwen2.5:3b via Ollama
- **Embeddings:** `intfloat/multilingual-e5-base`
- **Banco vetorial:** ChromaDB com persistência em disco
- **Corpus:** 15 documentos técnicos (normas, relatórios e manuais) — 95 chunks indexados

## Estrutura do Repositório

```
├── GS_1º_(SEM)_Processamento_de_Linguagem_Natural,_Chatbots_&_Virtual_Agents (1).ipynb
│     Pipeline completo: corpus → limpeza → chunking → embeddings → RAG → avaliação → t-SNE
│
├── Relatorio_Critico_GS_RAG_ABNT.docx
│     Relatório crítico em formato ABNT com análise dos resultados
│
├── link_video.txt
│     Link do vídeo de apresentação no YouTube
│
└── README.md
```

## Etapas do Notebook

| Etapa | Descrição |
|-------|-----------|
| 1 | Instalações críticas (Ollama, ChromaDB, SentenceTransformers) |
| 2 | Imports e configuração global |
| 3 | Inicialização do servidor LLM local (Qwen2.5:3b) |
| 4 | Definição e criação do corpus (15 documentos, 3 categorias) |
| 5 | Extração e limpeza de textos |
| 6 | Chunking semântico (95 chunks, média 129 tokens) |
| 7 | Embeddings e indexação no ChromaDB |
| 8 | Pipeline RAG com citação de fontes |
| 9 | Avaliação: 10 perguntas técnicas + comparação RAG vs. LLM puro |
| 10 | Visualização t-SNE + clusters K-Means |

## Resultados

- **Taxa de sucesso:** 9/10 perguntas respondidas com cobertura verificada manualmente
- **Similaridade máxima média:** 0,875
- **Precisão técnica RAG vs. LLM puro:** 4,7/5 vs. 2,0/5
- **Alucinação RAG vs. LLM puro:** 1/5 vs. 4/5

## Vídeo de Apresentação

[![Assistente RAG — Edifícios Verdes e Net Zero](https://img.youtube.com/vi/_eCXcS0mh9k/0.jpg)](https://youtu.be/_eCXcS0mh9k)

[Assistir no YouTube](https://youtu.be/_eCXcS0mh9k)
