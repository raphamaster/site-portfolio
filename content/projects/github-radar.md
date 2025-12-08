---
title: GitHub Radar
date: 2025-10-04T10:00:00-03:00
draft: false
tags: ["Power BI", "Python", "Figma"]
# Descrição usada no card da Home Page e na Listagem
description: "Dashboard analítico para inspeção de repositórios GitHub (atividade, concentração/“bus factor”, processo/qualidade e linguagens). O projeto coleta dados via scripts Python (etl/), gera CSVs em out/ e carrega tudo em um relatório Power BI (template .pbit)."
featured_image: "https://github.com/raphamaster/github_radar/blob/main/powerbi/screenshots/Screenshot_1.png?raw=true"
github_url: "https://github.com/raphamaster/github_radar"
---
## Desafio e Solução

# GitHub Radar — Power BI (Data Engineering)

Dashboard analítico para inspeção de repositórios GitHub (atividade, concentração/“bus factor”, processo/qualidade e linguagens).
O projeto coleta dados via scripts Python (`etl/`), gera CSVs em `out/` e carrega tudo em um relatório Power BI (template `.pbit`).

---

## 🧭 Visão rápida
- **Stack**: Python (ETL) + Power BI
- **Dados**: API do GitHub → CSVs em `out/`
- **Relatório**: `powerbi_template/GithubRadar.pbit` (fonte oficial para versionamento)
- **Design**: arquivos **SVG** e **Figma** em `powerbi/design/`

## 📊 Páginas do Dashboard

### 1) Visão Geral
- **KPIs**: Stars • Commits (janela) • Contribuidores Únicos • Lead Time (médio/mediano)
- **Tabela-hub**: ranking por atividade/concentração com link para o repo
- **Top 10 por atividade** (commits na janela)
![Visão Geral](https://raw.githubusercontent.com/raphamaster/github_radar/refs/heads/main/powerbi/screenshots/Screenshot_1.png)

### 2) Atividade
- Série temporal de commits (dia/semana) e **média móvel (MM7)**
- Slicers de repo/owner/language e janela de tempo
![Atividade](https://raw.githubusercontent.com/raphamaster/github_radar/refs/heads/main/powerbi/screenshots/Screenshot_2.png)

### 3) Concentração (Bus Factor)
- **Top1 Commits %** e **Top3 Commits %** por repositório
- Tabela “drill” por contribuidor (`login`, contribuições, % no repo)
![Concentração](https://github.com/raphamaster/github_radar/blob/main/powerbi/screenshots/Screenshot_3.png?raw=true)

### 4) Processo / Qualidade
- **Histograma** de `lead_time_days` (bins) e **P90/P95**
- Barras: Issues fechadas na janela por repo
![Processo](https://github.com/raphamaster/github_radar/blob/main/powerbi/screenshots/Screenshot_4.png?raw=true)

### 5) Linguagens
- **Treemap** % por linguagem • Barra empilhada `linguagem × repo`
![Linguagens](https://github.com/raphamaster/github_radar/blob/main/powerbi/screenshots/Screenshot_5.png?raw=true)

### 6) Layout/Design
- Paleta e tipografia do tema, grid e componentes
![Design](https://github.com/raphamaster/github_radar/blob/main/powerbi/screenshots/Screenshot_6.png?raw=true)

> Os arquivos vetoriais de cada página estão em `powerbi/design/*.svg` e o projeto Figma em `powerbi/design/GithubRadar_Design.fig`.

---

## 🧩 Medidas-chave (DAX) — highlights
- **Atividade**: `Commits (Janela)`, `Média Diária (30d)`
- **Concentração**: `Top1 Commits %`, `Top3 Commits %`, `Contribuidores Únicos`
- **Processo**: `Lead Time Mediano`, `Lead Time P95`, `Issues Fechadas (Janela)`
- **Linguagens**: `Bytes Linguagem`, `% Linguagem`

> O modelo segue estrela: `RepoMeta` (dim) → fatos (`RepoCommitsDaily`, `RepoContrib`, `RepoIssuesClosed`, `RepoLang`). Chave: `RepoKey = owner & "/" & repo`.

---
