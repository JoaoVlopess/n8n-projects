# 🤖 n8n-projects | Seu Repositório de Automações Low-Code

Este repositório é uma coletânea de fluxos de trabalho (workflows) desenvolvidos na plataforma de automação **n8n** (Low-Code/No-Code). O objetivo é compartilhar soluções de automação prontas para uso, desde integrações simples até Agentes de IA complexos.

## 🚀 Como Usar os Fluxos

Para começar a usar qualquer um dos fluxos contidos aqui, siga estes passos:

1.  **Escolha o Fluxo:** Navegue pela pasta do fluxo desejado (por exemplo, `agente-educado-groq`).
2.  **Baixe o JSON:** Faça o download do arquivo `.json` do fluxo (ex: `agente-educado.json`).
3.  **Importe no n8n:**
    * Abra sua instância do n8n (self-hosted ou cloud).
    * Clique em **"Workflows"** e depois em **"New"**.
    * No menu superior, clique em **`...`** (ou no nome do fluxo) e escolha **"Import from File"** ou cole o conteúdo JSON diretamente na tela de importação.
4.  **Configure as Credenciais:** Associe as credenciais (APIs Keys) necessárias para os Nodes de serviços externos (como Groq, Google Sheets, etc.).
5.  **Ative o Fluxo:** Alterne o botão de **`Active`** para começar a usar a automação!

## 📂 Projetos Atuais

| Nome do Projeto | Descrição Breve | Tecnologias Chave | Status |
| :--- | :--- | :--- | :--- |
| **Agente Educado Groq (Web)** | Um chatbot versátil que usa a API Groq (com seu modelo de alta velocidade) e memória simples para responder a qualquer pergunta do usuário e lembrar de conversas anteriores. (Web-based) | n8n, Groq Chat Model, Simple Memory | ✅ Ativo |
| **Agente Educado Groq (Telegram)** | **Versão do Agente Educado integrada ao Telegram. Responde a mensagens em tempo real e salva o histórico da conversa em uma planilha do Google Sheets.** | **n8n, Telegram Trigger, Groq, Google Sheets** | **✅ Ativo** |

## ✨ Destaque: Agente Educado Groq (Telegram)

O projeto do Telegram demonstra a robustez do n8n na criação de agentes conversacionais que interagem diretamente com o usuário e persistem dados em serviços externos.

### Visão Geral do Fluxo

O fluxo é acionado por uma mensagem no Telegram e segue a seguinte lógica:

1.  **Gatilho:** `Telegram Trigger (On Message)` — Acionado por qualquer mensagem de texto recebida.
2.  **Processamento:** `Edit Fields` (para formatar dados da mensagem).
3.  **Log:** `Append row in sheet` (salva o usuário, mensagem e timestamp no Google Sheets).
4.  **IA Principal:** `AI Agent` (orquestra a conversa, utiliza Groq, memória e ferramentas).
    * **Modelo:** Groq Chat Model (rápido e eficiente)
    * **Memória:** Simple Memory
    * **Ferramenta:** Calculator e Wikipedia.
5.  **Resposta:** **`Telegram Action (Send a text message)`** — Envia a resposta gerada pela IA de volta ao Chat ID de origem.
6.  **Finalização:** `No Operation, do nothing` (encerra o fluxo).

### Requisitos

* Instância do n8n.
* **Token do BotFather (Telegram).**
* Credencial da API **Groq**.
* Credencial do **Google Sheets** (para o log de histórico).

## 🤝 Contribuições

Este é um repositório de código aberto e projetos são bem-vindos! Se você tem um fluxo n8n interessante que gostaria de compartilhar:

1.  **Fork** este repositório.
2.  Crie uma nova pasta para o seu projeto e inclua o arquivo `.json` exportado.
3.  Crie um Pull Request, adicionando uma linha na tabela de projetos e uma breve descrição.

---
Feito com 💜 por [Seu Nome ou Nome do Projeto]
