# n8n_Compressed_Docs_Chatbot
AI chatbot built with n8n that uses compressed information from documents (in this example, papers from arXiv) to answer questions related to those documents. This project explores an alternative approach compared to well-known RAG systems.

The project consists of three distinct n8n workflows. They need to be executed in order, however, the first two workflows need to be executed only once. They require two data tables, one of which is populated by the first workflow, while the second must be pre-populated (provided in Prompts.csv). The workflows and data tables are briefly described below:

- The data table "Arxiv_Papers" is used to store information about downloaded and processed papers.

- The data table "Prompts" contains the prompts to be executed for each paper.

- Workflow "01_get" downloads papers from arxiv.org based on search criteria defined in the "HTTP Request" node and stores metadata for the papers in the "Arxiv_Papers" data table.

- Workflow "02_extract" uses the prompts from the "Prompts" data table to extract relevant information from each paper, which is also stored in the "Arxiv_Papers" data table.

- Workflow "03_chatbot" provides an interactive chatbot that uses the extracted information from the papers to answer user questions.

A local LLM (Gemma3:12b) running via Ollama is used for both the information extraction and the chatbot
