---
title: Market Data - FX • Índices • Cripto
date: 2025-11-03T10:00:00-03:00
draft: false
tags: ["Power BI", "Python", "MariaDB"]
# Descrição usada no card da Home Page e na Listagem
description: "Pipeline de engenharia de dados (estilo Medalhão: Bronze → Silver → Gold) para coletar câmbio, índices e cripto, armazenar no MariaDB, e visualizar em Power BI com tema dark de mercado."
featured_image: "https://github.com/raphamaster/market-data-medal/blob/main/screenshots/pagina1_panorama.png?raw=true"
github_url: "https://github.com/raphamaster/market-data-medal"
---

Pipeline de engenharia de dados (estilo **Medalhão: Bronze → Silver → Gold**) para coletar **câmbio**, **índices** e **cripto**, armazenar no **MariaDB**, e visualizar em **Power BI** com tema dark de mercado.

---

## 🗺️ Arquitetura & Fluxo

```
Fontes (APIs/CSV)
   ├─ ECB FX (EUR-base)          → Bronze: md_bronze.ecb_fx_raw
   ├─ PTAX USD/BRL               → Bronze: md_bronze.ptax_raw
   ├─ Stooq (S&P 500 etc.)       → Bronze: md_bronze.stooq_index_raw
   └─ Yahoo (^BVSP) — fallback   → Bronze: md_bronze.stooq_index_raw (mesma tabela)

Bronze  →  Silver (normalização) →  Gold (fatos/dimensões) →  Power BI
```

- **Silver** consolida e padroniza colunas/schemas.
- **Gold** expõe tabelas de consumo analítico (fatos e dimensões) que o Power BI usa.

### Principais Tabelas (Gold)
- `dim_calendario` — calendário completo (Y, M, Y-M, ISO semana etc.)
- `fact_fx_daily` — séries de FX por `currency_pair` (USD/BRL, EUR/BRL, GBP/BRL…)
- `fact_index_daily` — índices: `index_code` (`^spx`, `^bvsp`), `close_price`, `volume`
- `fact_crypto_daily` — cripto (BTC/BRL derivado do BTC/USD + FX quando aplicável)

## 📊 Dashboard (Power BI)

O relatório está organizado em **quatro páginas**. As imagens estão em `./screenshots/`.

### 1) Panorama do Mercado
**Objetivo:** visão rápida do período selecionado.  
**Conteúdo:**
- **Cards** de “Último” e **Variação % (Período)** para USD/BRL, EUR/BRL, GBP/BRL, BTC/BRL, IBOV e S&P 500
- **Linha temporal** das séries FX
- **Barras** de Performance % (ranking)

**Imagem:**  
![Panorama do Mercado](https://github.com/raphamaster/market-data-medal/blob/main/screenshots/pagina1_panorama.png?raw=true)

---

### 2) Moedas (FX) em Detalhe
**Objetivo:** detalhar comportamento das moedas vs BRL.  
**Conteúdo:**
- **Small multiples** (linhas) por par (USD/BRL, EUR/BRL, GBP/BRL)
- **Heatmap mensal** (variação média diária)
- **Tabela diária**: Fechamento, Var % d/d, MM7, Máx/Mín 30d
- **Slicers:** Data e Par Cambial

**Imagem:**  
![FX em Detalhe](https://github.com/raphamaster/market-data-medal/blob/main/screenshots/pagina2_fx_detalhe.png?raw=true)

---

### 3) Índices & Cripto (Risco x Retorno)
**Objetivo:** comparar **IBOV**, **S&P 500** e **BTC/BRL**.  
**Conteúdo:**
- **Scatter** Risco x Retorno (YTD): `Retorno % YTD` × `Volatilidade 30d`
- **Linha normalizada (=100)** para comparar trajetórias
- **Tabela** com: Valor Atual, Retorno % Período, Retorno % YTD, Volatilidade 30d, Drawdown Máx %

**Imagem:**  
![Índices & Cripto](https://github.com/raphamaster/market-data-medal/blob/main/screenshots/pagina3_indices_cripto.png?raw=true)


