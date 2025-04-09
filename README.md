# 🤖 Chat Interativo com PDFs usando Azure AI Foundry

## 📘 Descrição do Projeto

Este projeto simula o desenvolvimento de um **chat inteligente** capaz de responder perguntas com base no conteúdo de arquivos PDF, utilizando exclusivamente ferramentas da plataforma **Azure**. A solução é ideal para estudantes de Engenharia de Software que precisam revisar, entender e correlacionar conteúdos de múltiplos artigos científicos.

É projeto foi o segundo desafio do Bootcamp Dio em parceria com a Microsoft, como curso/treinamento para a obtenção da Certificação DP-100 da Microsoft

A ideia central é combinar **IA generativa**, **embeddings** e **busca vetorial**, tudo orquestrado pelo **Azure AI Foundry**, criando um sistema robusto e escalável para análise de documentos acadêmicos.

---

## 🎯 Objetivos

✅ Carregar arquivos PDF relevantes para um TCC  
✅ Indexar o conteúdo desses arquivos em um sistema de busca vetorial  
✅ Utilizar IA generativa para responder perguntas com base nos documentos  
✅ Criar um chat interativo acessível e contextual  

---

## 🧠 Arquitetura da Solução (100% Azure)

```mermaid
graph TD
    A[📤 Upload dos PDFs] --> B[🗂️ Azure Blob Storage]
    B --> C[📄 Azure AI Document Intelligence]
    C --> D[🔎 Azure AI Foundry - Embedding Generator]
    D --> E[🧭 Azure AI Search - Vetorização e Indexação]
    F[🗨️ Usuário faz pergunta] --> G[🧠 Azure OpenAI - Chat Model]
    E --> G
    G --> H[✅ Resposta baseada no conteúdo dos PDFs]
````

---

## 🛠️ Serviços do Azure Utilizados

| Serviço                                | Função                                                                 |
|----------------------------------------|------------------------------------------------------------------------|
| ☁️ **Azure Blob Storage**              | Armazenamento seguro dos PDFs                                          |
| 🧾 **Azure AI Document Intelligence**  | Extração estruturada de texto dos arquivos PDF                         |
| 🧠 **Azure AI Foundry**                | Orquestração do pipeline de embeddings, busca e chat                   |
| 💬 **Azure OpenAI**                    | Geração de respostas em linguagem natural                              |
| 🧭 **Azure AI Search (Vector Search)** | Indexação vetorial e recuperação semântica do conteúdo dos documentos  |

---

## 🔄 Etapas Técnicas do Projeto
1️⃣ Upload de PDFs no Azure Blob Storage
- Criação um container tcc-pdfs no portal do Azure
- Upload manual de alguns artigos científicos

2️⃣ Extração de Texto com Azure AI Document Intelligence
- Utilização de modelo pré-treinado
- Conversão de arquivos em JSON com texto estruturado

3️⃣ Geração de Embeddings com Azure AI Foundry
- Divisão dos conteúdos dos PDFs em chunks
- Vetores gerados enviados ao Azure AI Search

4️⃣ Indexação Vetorial com Azure AI Search

5️⃣ Geração de Respostas com Azure OpenAI
- Utilização do modelo gpt4.o Azure OpenAI
- As perguntas são combinadas com os trechos mais relevantes extraídos via busca vetorial
- As respostas são geradas com base exclusiva no conteúdo dos documentos

6️⃣ Interface de Chat com Azure AI Foundry Studio
- Criação de um agente interativo no Azure AI Foundry Studio
- Interface amigável que permite ao usuário perguntar livremente e apenas sobre o conteúdo dos PDFs
- As respostas são sempre fundamentadas no conteúdo dos PDFs

---

💡 Insights e Aprendizados
✨ O Azure AI Foundry oferece uma abordagem moderna e modular para lidar com documentos proprietários.
✨ A busca vetorial com Azure AI Search é escalável e se integra facilmente ao pipeline.
✨ Utilizar ferramentas nativas do Azure simplifica o deploy e garante segurança e governança.
✨ Separar bem cada etapa (extração, embeddings, resposta) melhora a precisão e explicabilidade do sistema.

---

🚀 Possibilidades Futuras
🔍 Adicionar suporte para PDFs escaneados com OCR
🧠 Criar uma base de conhecimento por área temática (ex: engenharia, IA, saúde)
📄 Exportar respostas como resumos ou anotações automáticas para estudo
🧑‍🏫 Aplicar a mesma arquitetura para bases de conhecimento corporativas

---

✅ Conclusão
Este projeto demonstrou como é possível criar um sistema de perguntas e respostas baseado em PDFs utilizando apenas ferramentas nativas do Azure. A abordagem oferece escalabilidade, confiabilidade e permite que o usuário tenha acesso rápido a informações críticas de documentos acadêmicos sem precisar ler todos os textos manualmente.

A tecnologia da IA generativa, quando combinada com embeddings e busca vetorial, transforma a maneira como lidamos com grandes volumes de informação.

---
