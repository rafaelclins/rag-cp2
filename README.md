# DocMind RAG — Livro de Receitas da Vovó 🍳

Este repositório contém a implementação do **Checkpoint 02 (Módulo 2 - RAG)** da disciplina *Prompt Engineering and Artificial Intelligence* da FIAP.

## 👥 Integrantes do Grupo
* **Rafael Lins** — RM: 570588
* **Rafael Gandolfi** — RM: 569036
* **Carlos Tavares** — RM: 572949
* **Cauã Paes** — RM: 569906
* **Guilherme Miranda** — RM: 573107
* **João Pedro Soler** — RM: 569725

## 📌 Descrição do Domínio
O projeto utiliza o livro oficial **Receitas da Vovó (FASUL, 2013)** contendo 21 páginas com pratos doces e salgados. O sistema RAG realiza a busca semântica por ingredientes e modos de preparo, respondendo com **grounding rigoroso** e citação de fonte e número de página (`page + 1`).

## 📂 Estrutura do Repositório
* `data/livro_de_receitas.pdf`: Documento PDF de 21 páginas com a base de conhecimento.
* `CKP02_Culinaria_Grupo.ipynb`: Notebook com o pipeline RAG completo, duas estratégias de chunking e avaliação quantitativa via LLM-as-Judge.

## 🚀 Como Adicionar Novos Documentos à Base
1. Adicione o novo arquivo PDF na pasta `data/`.
2. No notebook `CKP02_Culinaria_Grupo.ipynb`, inclua o caminho do arquivo no carregador.
3. Re-execute a célula de indexação para atualizar as coleções no ChromaDB.

## 📊 Resumo Comparativo dos Resultados (LLM-as-Judge)
| Estratégia de Chunking | Faithfulness | Answer Relevancy | Chunks Gerados |
| :--- | :---: | :---: | :---: |
| **Estratégia A (Recursive 512 / Overlap 64)** | **0.98** | **0.72** | **81** |
| Estratégia B (SemanticChunker) | 0.80 | 0.16 | 42 |
