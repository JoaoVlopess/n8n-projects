# 🤖 n8n-projects | Seu Repositório de Automações Low-Code

Este repositório é uma coletânea de fluxos de trabalho (workflows) desenvolvidos na plataforma de automação **n8n** (Low-Code/No-Code). O objetivo é compartilhar soluções de automação prontas para uso, desde integrações simples até Agentes de IA complexos e transacionais.

## 🚀 Como Usar os Fluxos

Para começar a usar qualquer um dos fluxos contidos aqui, siga estes passos:

1.  **Escolha o Fluxo:** Navegue pela pasta do fluxo desejado (por exemplo, `agente-marcador-aulas`).
2.  **Baixe o JSON:** Faça o download do arquivo `.json` do fluxo (ex: `agente-aulas.json`).
3.  **Importe no n8n:**
    * Abra sua instância do n8n (self-hosted ou cloud).
    * Clique em **"Workflows"** e depois em **"New"**.
    * No menu superior, clique em **`...`** (ou no nome do fluxo) e escolha **"Import from File"** ou cole o conteúdo JSON diretamente na tela de importação.
4.  **Configure as Credenciais:** Associe as credenciais (APIs Keys) necessárias para os Nodes de serviços externos (como Groq, Google Calendar, etc.).
5.  **Ative o Fluxo:** Alterne o botão de **`Active`** para começar a usar a automação!

## 📂 Projetos Atuais

| Nome do Projeto | Descrição Breve | Tecnologias Chave | Status |
| :--- | :--- | :--- | :--- |
| **Agente Educado Groq (Web)** | Um chatbot versátil que usa a API Groq (com seu modelo de alta velocidade) e memória simples para responder a qualquer pergunta do usuário e lembrar de conversas anteriores. (Web-based) | n8n, Groq Chat Model, Simple Memory | ✅ Ativo |
| **Agente Marcador de Aulas (Telegram)** | **Sistema transacional de agendamento de aulas de violão que verifica disponibilidade no Google Calendar em tempo real, evitando conflitos de horário.** | **n8n, Telegram Trigger, Groq, Google Calendar, JSON Parsing** | **✅ Ativo** |

## ✨ Destaque: Agente Marcador de Aulas (Telegram)

Este projeto demonstra a capacidade do n8n de construir **Agentes Transacionais robustos**, que não apenas interagem com o usuário, mas também executam lógica de negócios complexa, como a verificação de disponibilidade em uma API externa.

### Visão Geral do Fluxo

O fluxo é acionado por uma mensagem no Telegram e segue a seguinte lógica:

1.  **Gatilho:** `Telegram Trigger (On Message)` — Acionado por qualquer pedido de agendamento.
2.  **IA e Extração:** `AI Agent` com `Structured Output Parser` — Extrai o nome do aluno, data, hora e duração, e **valida** se todos os dados necessários estão presentes.
3.  **Verificação de Conflito:** `Google Calendar (Get Many)` — Pesquisa por eventos que se **sobrepõem** ao horário solicitado pelo aluno.
4.  **Decisão:** `IF` (Lógica Condicional) — Verifica o número de eventos retornados:
    * **Se TRUE (> 0 eventos):** Retorna uma mensagem de **Conflito/Horário Ocupado**.
    * **Se FALSE (0 eventos):** Segue para o agendamento.
5.  **Transação:** `Google Calendar (Create an event)` — Marca a aula na agenda.
6.  **Resposta:** `Telegram Action (Send a text message)` — Envia uma mensagem de **Confirmação de Agendamento** ou **Solicitação de Dados Faltantes** ao aluno.

### Requisitos

* Instância do n8n.
* **Token do BotFather (Telegram).**
* Credencial da API **Groq** (para extração de dados).
* Credencial do **Google Calendar** (com permissão para ler e escrever).

## 🤝 Contribuições

Este é um repositório de código aberto e projetos são bem-vindos! Se você tem um fluxo n8n interessante que gostaria de compartilhar:

1.  **Fork** este repositório.
2.  Crie uma nova pasta para o seu projeto e inclua o arquivo `.json` exportado.
3.  Crie um Pull Request, adicionando uma linha na tabela de projetos e uma breve descrição.

---
Feito por João Lopes!
