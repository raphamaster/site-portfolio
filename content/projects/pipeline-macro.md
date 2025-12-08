---
title: Pipeline Macro (BCB/SGS → Postgres → BI) 
date: 2024-10-07T10:00:00-03:00
draft: false
tags: ["n8n", "Postgres ", "API do BCB/SGS", "Power BI"]
# Descrição usada no card da Home Page e na Listagem
description: "Ingestão e modelagem de séries econômicas do Banco Central (SGS) usando Docker, n8n e PostgreSQL nas camadas bronze → silver → gold, com orquestração diária e eventos simples."
featured_image: "https://github.com/raphamaster/projeto-bcb-sgs/blob/main/docs/n8n/n8n-W1-ingest-canvas.png?raw=true"
github_url: "https://github.com/raphamaster/projeto-bcb-sgs"
---

Ingestão e modelagem de séries econômicas do Banco Central (SGS) usando **Docker**, **n8n** e **PostgreSQL** nas camadas **bronze → silver → gold**, com orquestração diária e eventos simples.

## 🔎 Visão Geral

- **Fontes**: API pública do BCB/SGS (séries 1, 11, 432, 433 por padrão)
- **Orquestração**: n8n (Workflows W1–W4 + Orquestrador)
- **Persistência**: Postgres (camadas bronze/silver/gold + catálogos e logs)
- **Dashboards**: Power BI conectado direto no Postgres (sem CSV)
- **Eventos**: spikes em USD/BRL e mudança de meta Selic gravados no banco

## 🧱 Arquitetura

```
        +-----------------+
        |   Orchestrator  |  (Cron 07:30 BRT)
        +--------+--------+
                 |
                 v
+-------- W1: Ingest (Code) --------+
| Get series -> Build windows ->    |
| Fetch SGS -> Upsert Bronze        |
+-------------------+---------------+
                    v
         +----------+-----------+
         | W2: Bronze  -> Silver|
         +----------+-----------+
                    v
         +----------+-----------+
         | W3: Silver -> Gold   |
         +----------+-----------+
                    v
         +----------+-----------+
         | W4: Alertas (DB)     |
         +----------------------+
```

## Imagens (prints) e anotações dos workflows n8n e do dashboard.

## Conteúdo
- **n8n/**: prints dos workflows W1–W4 e do Orquestrador
- **dashboard/**: prints do Power BI

## n8n — Workflows

### W1 — Ingest (SGS → Bronze)
![W1 Ingest](https://github.com/raphamaster/projeto-bcb-sgs/blob/main/docs/n8n/n8n-W1-ingest-canvas.png?raw=true)

### W2 — Bronze → Silver
![W2 Silver](https://github.com/raphamaster/projeto-bcb-sgs/blob/main/docs/n8n/n8n-W2-silver-canvas.png?raw=true)

### W3 — Silver → Gold
![W3 Gold](https://github.com/raphamaster/projeto-bcb-sgs/blob/main/docs/n8n/n8n-W3-gold-canvas.png?raw=true)

### W4 — Alertas (DB)
![W4 Alertas](https://github.com/raphamaster/projeto-bcb-sgs/blob/main/docs/n8n/n8n-W4-alertas-canvas.png?raw=true)

### Orquestrador
![Orquestrador](https://github.com/raphamaster/projeto-bcb-sgs/blob/main/docs/n8n/n8n-W0-orchestrator-canvas.png?raw=true)

