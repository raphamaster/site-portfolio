---
title: MCP Automotivo
date: 2025-11-28T10:00:00-03:00
draft: false
tags: ["MCP", "Docker", "Python", "SQL", "MariaDB", "Gemini"]
# Descrição usada no card da Home Page e na Listagem
description: "Implementação de arquitetura Data Lakehouse Serverless no Azure, unificando dados brutos e estruturados para análises em tempo real."
featured_image: "https://github.com/raphamaster/mcp-automotivo/blob/main/screenshots/mcp-automotivo.png?raw=true"
github_url: "https://github.com/raphamaster/mcp-automotivo"
---

# 🚗 MCP – Sistema de Análise de Dados Automotivos

**Sistema inteligente de análise de dados utilizando Google Gemini e MariaDB**

## 📋 Sobre o Projeto

Este é um projeto **MCP (Model Context Protocol)** que demonstra a integração entre um modelo de IA generativa (**Google Gemini**) e um banco de dados **MariaDB**, permitindo realizar análises de dados usando linguagem natural.

### 🎯 Objetivos Educacionais

- Demonstrar na prática a comunicação entre LLMs e bancos de dados  
- Implementar um sistema completo de análise utilizando NLP  
- Criar um ambiente funcional com **Docker + Python + SQL**  
- Servir como material de estudo em IA aplicada e engenharia de dados  

## 🚀 Tecnologias Utilizadas

- **Python 3.10+**
- **MariaDB 11.4**
- **Google Gemini 2.0 Flash**
- **Docker**
- **pandas**

## ⚙️ Funcionalidades

### 🔍 Análise com Linguagem Natural  
- Perguntas diretas em português  
- Geração automática de queries SQL  
- Execução e interpretação inteligente dos resultados  

## 💡 Como Usar

Exemplos de perguntas simples:

```
"Qual o faturamento total?"
"Quais são os 5 produtos mais vendidos?"
"Quem são os melhores vendedores?"
```

**Imagem:**  
![Prompt](https://github.com/raphamaster/mcp-automotivo/blob/main/screenshots/mcp-automotivo.png?raw=true)

Perguntas mais elaboradas para testar a LLMs:

```
"Qual categoria de produtos tem a melhor margem de lucro (diferença entre preço de venda e custo) e quantas unidades foram vendidas de cada categoria no último mês?"

"Quais clientes do tipo 'Oficina' têm o maior ticket médio e qual a frequência de compras deles? Mostre também o valor total gasto por cada um."

"Como evoluiu o faturamento mensal nos últimos 6 meses? Mostre a variação percentual mês a mês e identifique se há alguma tendência de crescimento ou queda."

"Compare a performance dos vendedores considerando não apenas o faturamento, mas também o número de vendas realizadas e o tempo que cada um está na empresa. Quem tem a melhor eficiência?"

"Quais produtos têm alta demanda (muitas vendas) mas estoque baixo, representando risco de ruptura? E quais têm estoque alto mas pouca saída, representando capital parado?"

"Qual é o produto 'carro-chefe' de cada categoria em termos de faturamento?"

"Existe correlação entre o valor da venda e a forma de pagamento escolhida?"

"Quais vendedores são mais eficientes em vender produtos de alta margem?"
```

