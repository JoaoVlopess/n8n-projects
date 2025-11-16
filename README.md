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
| **Agente Educado Groq** | Um chatbot versátil que usa a API Groq (com seu modelo de alta velocidade) e memória simples para responder a qualquer pergunta do usuário e lembrar de conversas anteriores. | n8n, Groq Chat Model, Simple Memory | ✅ Ativo |
| *[Seu Próximo Projeto]* | *[Adicione a descrição do próximo fluxo que você criar]* | *[Ex: n8n, Google Sheets, Webhook]* | 🚧 Em Desenvolvimento |

## ✨ Destaque: Agente Educado Groq

O primeiro projeto deste repositório é um exemplo prático de como construir um Agente de IA conversacional poderoso usando o n8n.

### Visão Geral do Fluxo

O fluxo é acionado por uma mensagem de chat e segue a seguinte lógica:

1.  **Gatilho:** `When chat message received`
2.  **Processamento:** `Edit Fields` (para formatar dados)
3.  **Log:** `Append row in sheet` (salva o histórico em uma planilha)
4.  **IA Principal:** `AI Agent` (orquestra a conversa, utiliza memória e ferramentas)
    * **Modelo:** Groq Chat Model (rápido e eficiente)
    * **Memória:** Simple Memory
    * **Ferramenta:** Calculator (para cálculos matemáticos) e Wikipedia (para pesquisa de conhecimento geral)
5.  **Finalização:** `No Operation, do nothing` (encerra o fluxo)

### Requisitos

* Instância do n8n.
* Credencial da API **Groq**.
* Credencial do **Google Sheets** (para o log de histórico, se mantiver o Node).

## 🤝 Contribuições

Este é um repositório de código aberto e projetos são bem-vindos! Se você tem um fluxo n8n interessante que gostaria de compartilhar:

1.  **Fork** este repositório.
2.  Crie uma nova pasta para o seu projeto e inclua o arquivo `.json` exportado.
3.  Crie um Pull Request, adicionando uma linha na tabela de projetos e uma breve descrição.

---
Feito com 💜 por [Seu Nome ou Nome do Projeto]
