# 📊 Portfolio & Blog

Este é o repositório oficial do meu portfólio profissional e blog. O site é construído com **Hugo** e estilizado com **Tailwind CSS**, focado em apresentar meu trabalhos e pensamentos.

## ✨ Destaques do Projeto

* **Arquitetura Sólida (Hugo):** Renderização ultrarrápida, otimizada para SEO e performance.
* **Design Profissional:** Tema Dark Mode Neon com responsividade total (Mobile First).
* **Gestão de Conteúdo Simples:** Artigos (Blog) e cases (Portfólio) gerenciados via **Markdown**.
* **Foco na Stack:** Demonstração da expertise em toda a trilha de dados (ETL, Cloud, BI, ML).

## 🚀 Instalação e Execução Local

Para rodar este projeto, você precisa ter o **Hugo** instalado na sua máquina.

### 1. Clonar o Repositório

```bash
# Clone o projeto
git clone https://github.com/raphamaster/site-portfolio
cd site-portfolio
```

### 2. Rodar o Servidor Local
Use o comando server com a flag -D (drafts) para renderizar todo o conteúdo, mesmo aqueles que ainda estão em rascunho (draft: true no Markdown):

```bash
hugo server -D
```

O site estará disponível em http://localhost:1313/ (ou a porta indicada no terminal).

## ✍️ Gerenciamento de Conteúdo (Markdown)
Todo o conteúdo dinâmico do Blog e do Portfólio é criado e editado em arquivos Markdown dentro da pasta content/.

### 1. Criar um Novo Post
Use o comando hugo new para criar um novo arquivo com o Front Matter padrão:

```bash
# Para um novo artigo de blog
hugo new content blog/novo-artigo-tecnico.md

# Para um novo Case de Projeto
hugo new content projects/novo-case.md
```

### 2. Estrutura do Front Matter
Para garantir que o template da Home Page exiba o resumo e os metadados corretamente, use este formato no topo de seus arquivos .md:

```mk
---
title: "Seu Título Completo Aqui"
date: 2025-12-06T10:00:00-03:00
draft: false
tags: ["Azure", "Python", "ETL"]
reading_time: 10 
description: "Um resumo conciso para aparecer nos cards da página inicial (Home)."
---

## Seu Conteúdo Markdown Começa Aqui
```

## 🌐 Implantação (Deployment)
O site é gerado como arquivos estáticos puros na pasta public/.

Para gerar o site final:

```bash
hugo --minify
```

A pasta public/ pode ser hospedada diretamente em plataformas como GitHub Pages, Netlify ou Azure Static Web Apps.