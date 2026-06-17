---
title: SQLShelf
date: 2026-06-16T10:00:00-03:00
draft: false
tags: ["Python", "SQL", "SQLite"]
description: "Gerenciador desktop open-source de consultas SQL: organize, descreva, categorize e encontre suas queries por conteúdo, tabela ou campo — sem perder a propriedade dos arquivos."
featured_image: "https://raw.githubusercontent.com/raphamaster/SQLShelf/main/images/logo_sqlshelf.png"
github_url: "https://github.com/raphamaster/SQLShelf"
---

<p align="center">
  <img src="https://raw.githubusercontent.com/raphamaster/SQLShelf/main/images/logo_sqlshelf.png" alt="SQLShelf" height="80">
</p>

Gerenciador desktop open-source de consultas SQL: organize, descreva, categorize e encontre suas queries por **conteúdo**, **tabela** ou **campo** — sem perder a propriedade dos arquivos.

---

## Sobre o Projeto

Se você trabalha com SQL e acumula dezenas (ou centenas) de arquivos `.sql` espalhados por pastas, o SQLShelf é a sua biblioteca. Ele escaneia qualquer pasta, indexa todas as queries e oferece busca full-text instantânea — incluindo buscas por nome de tabela, nome de coluna ou tag.

Seus arquivos continuam exatamente como estão. O SQLShelf adiciona apenas um bloco opcional de metadados no topo de cada arquivo (como comentário SQL), mantendo-os válidos e executáveis no SSMS ou qualquer outra ferramenta.

---

## Funcionalidades

### Busca
- Full-text search em todas as queries com resultado instantâneo
- Filtros por prefixo: `table:orders`, `col:customer_id`, `tag:report`
- Combinação livre de filtros — ex.: `table:orders tag:monthly`

### Organização
- Biblioteca multi-pasta — abra quantas pastas de projeto precisar
- Favoritos, Recentes e navegação por tags na barra lateral
- Tags inline com editor de chips
- Marque queries como favoritas com um clique

### Editor
- Syntax highlighting de SQL com números de linha e destaque da linha atual
- Painel de metadados: título, descrição, autor, tags — modo leitura/edição
- Exibe o caminho absoluto do arquivo (clicável — abre no Explorer ou SSMS)
- Copia o conteúdo SQL sem o bloco de frontmatter

### Filosofia File-First
- Seus arquivos `.sql` no disco são sempre a fonte da verdade
- Metadados ficam em um bloco de comentário YAML no topo de cada arquivo — não em um banco proprietário
- O índice de busca (SQLite) é totalmente regenerável e descartável
- Os arquivos permanecem válidos e executáveis no SSMS após qualquer operação do SQLShelf

---

## Interface

- Temas **dark** e **light** com troca em tempo real
- Interface em **Inglês** e **Português (PT-BR)**
- File watcher: o índice é atualizado automaticamente quando arquivos mudam no disco

**Tema Dark:**
![SQLShelf — tema dark](https://raw.githubusercontent.com/raphamaster/SQLShelf/main/images/Screenshot_SQLShelf.png)

**Tema Light:**
![SQLShelf — tema light](https://raw.githubusercontent.com/raphamaster/SQLShelf/main/images/Screenshot_SQLShelf_white.png)

---

## Download

Disponível para **Windows 10/11 x64** e **Linux x86_64** — instalador ou portátil (sem instalação).

[Baixar última versão](https://github.com/raphamaster/SQLShelf/releases/latest)
