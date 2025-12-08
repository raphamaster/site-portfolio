---
title: "MCP com Google AI Studio"
date: 2025-12-01T10:00:00-03:00
draft: false
tags: ["IA", "Gemini", "MCP", "Google"]
reading_time: 8
# Variável que controla o resumo da Home Page
description: "Como gerar sua chave de API no Google AI Studio para usar o Gemini nos seus projetos"
---

Nos últimos dias, várias pessoas me perguntaram qual integração utilizei no meu projeto de MCP (Model Context Protocol) e, principalmente, onde consegui a chave de acesso do Google para utilizar os modelos Gemini. Por isso, resolvi escrever este post para centralizar todas as informações e ajudar quem está começando ou deseja testar os recursos mais recentes de IA generativa do Google.

A resposta é: **utilizei o Google AI Studio**.

O Google AI Studio é atualmente a forma mais direta, simples e gratuita (com limites de uso) para gerar credenciais de API e consumir modelos da família **Gemini** em aplicações reais. Ele permite que você experimente prompts, valide entradas e saídas e, quando estiver satisfeito, gere rapidamente uma chave de API para integrar o modelo ao seu código.

---

![Google AI Studio](/img/Google_AI_Studio.png)

## Por que usar o Google AI Studio?

Além de ser extremamente intuitivo, o Google AI Studio oferece:

- **Um ambiente web interativo** para testar prompts antes de implementar.
- **Geração fácil de chaves de API** sem necessidade de criar projetos complexos no Google Cloud.
- **Tokens gratuitos limitados**, o que é perfeito para estudo, prototipação e primeiros experimentos.
- Suporte a **várias linguagens de programação**, incluindo Python, JavaScript e cURL.

Para quem deseja começar com MCP, RAG ou pequenas automações, ele atende muito bem.

---

![Google AI Studio](/img/Generate_API_Key.png)

## Como gerar sua chave de API

O processo é rápido e pode ser feito acessando diretamente o link abaixo:

👉 **https://lnkd.in/d7Q_xhx7**

Basta entrar com sua conta Google, aceitar os termos de uso e criar sua chave — tudo em menos de dois minutos.

Depois disso, você poderá usar a chave em qualquer aplicação que consuma o endpoint do Gemini.

---

## Como utilizar a chave no seu código

Um exemplo simples em Python para começar:

```python
from google import genai

client = genai.Client(api_key="SUA_CHAVE_AQUI")

response = client.models.generate_content(
    model="gemini-1.5-flash",
    contents="Explique em 3 tópicos o que é MCP."
)

print(response.text)
```

Pronto. Com poucas linhas você já está aproveitando os recursos mais recentes da IA generativa do Google.

## Conclusão

A criação da chave via Google AI Studio é totalmente gratuita (dentro dos limites de uso) e fornece tudo o que você precisa para explorar o potencial do Gemini — seja para estudos, POCs, integrações simples ou experimentos com MCP.

Espero que esse guia ajude a tornar o processo mais claro e facilite o desenvolvimento dos seus próximos projetos.

Se quiser que eu escreva um tutorial completo sobre integração com MCP + Gemini, é só pedir!