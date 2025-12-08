---
title: Monitoramento Macroeconômico de Commodities (IC-Br) vs. Dólar 
date: 2025-12-03T10:00:00-03:00
draft: false
tags: ["Jupyter", "Docker", "Pandas"]
# Descrição usada no card da Home Page e na Listagem
description: "Este projeto consiste em uma análise de dados ponta a ponta (ETL, Análise Exploratória e Visualização) para investigar a correlação entre o Índice de Commodities Brasil (IC-Br) e a taxa de câmbio (USD/BRL)."
featured_image: "https://github.com/raphamaster/ic-br/blob/main/output/demo_analise.gif?raw=true"
github_url: "https://github.com/raphamaster/ic-br"
---

Este projeto consiste em uma análise de dados ponta a ponta (ETL, Análise Exploratória e Visualização) para investigar a correlação entre o **Índice de Commodities Brasil (IC-Br)** e a taxa de câmbio **(USD/BRL)**. 

O objetivo é entender como a volatilidade cambial e os choques de oferta globais impactaram os preços das matérias-primas no Brasil nos últimos anos.


## Visualização do Projeto

> **[Clique aqui para ver o Gráfico Interativo (HTML)](https://nbviewer.org/github/raphamaster/ic-br/blob/main/notebooks/Analise_ICBr.ipynb)**

![Preview do Gráfico Estático](https://github.com/raphamaster/ic-br/blob/main/output/Screenshot_64.png?raw=true)


## Principais Insights de Negócio

Com base na análise da série histórica (2015-Presente), destacam-se:

1.  **O "Rali" da Pandemia (2020-2022):** A análise visual evidencia um descolamento agressivo dos preços a partir de março de 2020. A combinação de quebra nas cadeias de suprimento globais com a desvalorização do Real criou um cenário de "tempestade perfeita" para a inflação de custos.
2.  **Sensibilidade Cambial (Metais):** A matriz de correlação revelou que o subíndice de **Metais** possui a maior correlação positiva com o Dólar (> 0.70 em diversos períodos), indicando que este setor é o mais exposto à volatilidade cambial imediata.
3.  **Volatilidade Energética:** O setor de **Energia** apresentou os picos de variação mais bruscos, descolando-se frequentemente do índice Agro, o que sugere dinâmicas geopolíticas (ex: OPEP, conflitos) influenciando mais que a demanda interna.


## Ferramentas

* **Linguagem:** Python 3.9
* **Ambiente:** Docker & Jupyter Lab (Containerização para reprodutibilidade)
* **Fonte de Dados:** API do Banco Central do Brasil (`python-bcb`) - SGS
* **Bibliotecas Principais:**
    * `Pandas`: Manipulação e tratamento de Time Series (Resampling, Merges).
    * `Plotly`: Criação de visualizações interativas para web.
    * `Seaborn/Matplotlib`: Visualizações estáticas e estatísticas.

## Visualização do Projeto

Abaixo, uma demonstração da interatividade da análise, permitindo correlacionar os picos do Dólar com a alta das Commodities:

![Demonstração da Análise](https://github.com/raphamaster/ic-br/blob/main/output/demo_analise.gif?raw=true)
