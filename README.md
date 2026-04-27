# 📊 Mapeamento EdTech Brasil — Dashboard Executivo Nacional

Painel executivo interativo que sintetiza o **Mapeamento EdTech 2020** (CIEB/Abstartups) com triagem web atualizada até 2025, artigo científico com formatação ABNT, tabela de players e análise de Educação Especial inclusiva.

---

## ✅ Funcionalidades Implementadas

### Navegação por Abas (10 seções)
| Aba | Conteúdo |
|-----|----------|
| **Visão Geral** | KPIs macro, strip de impacto, gráficos de público-alvo e maturidade |
| **Perfil & Segmentos** | Verticais, recursos digitais, equipes e idade das empresas |
| **Distribuição Regional** | Cards por região, gráfico donut, top 6 estados |
| **Modelos de Negócio** | Distribuição de receita, B2x, setor público |
| **Série Histórica** | Linha 2018–2025, timeline de marcos, variação YoY |
| **Tendências & Prospecção** | Levantamento bibliográfico 2017–2025 (pré/durante/pós pandemia) + 10 oportunidades 2026 + radar + infográfico |
| **Artigo Científico** | Revisão integrativa ABNT (42 publicações, 2015–2025) + infográfico científico + referências completas |
| **Players & EdTechs** | Tabela filtrável de 82+ EdTechs por categoria com gráficos |
| **Educação Especial** | Análise baseada em evidências: DUA, PBE, LBI, PNEE + tabela por deficiência + 6 oportunidades |
| **Fontes** | 8 fontes documentadas com links, nota metodológica |

---

## 📁 Estrutura de Arquivos

```
index.html    ← Dashboard completo (HTML + CSS + JS em arquivo único)
README.md     ← Documentação do projeto
```

---

## 🔗 Entry Points

| Caminho | Seção |
|---------|-------|
| `/` | Visão Geral |
| `showSection('overview')` | Visão Geral |
| `showSection('perfil')` | Perfil & Segmentos |
| `showSection('regional')` | Distribuição Regional |
| `showSection('negocio')` | Modelos de Negócio |
| `showSection('historico')` | Série Histórica |
| `showSection('tendencias')` | Tendências & Prospecção 2026 |
| `showSection('artigo')` | Artigo Científico ABNT |
| `showSection('players')` | Players & EdTechs |
| `showSection('inclusiva')` | Educação Especial Inclusiva |
| `showSection('fontes')` | Fontes |

---

## 📊 Dados e Fontes Primárias

| Fonte | Ano | Dado |
|-------|-----|------|
| CIEB/Abstartups — Mapeamento 2018 | 2018 | 364 EdTechs |
| CIEB/Abstartups — Mapeamento 2019 | 2019 | 449 EdTechs |
| CIEB/Abstartups — **Mapeamento 2020** *(ref. central)* | 2021 | 566 EdTechs (+26,1%) |
| Abstartups — Mapeamento 2022 | 2022 | 813 EdTechs (+44%) |
| Distrito — EdTech Report 2025 | 2025 | 1.300+ startups |
| Liga Ventures — Startup Landscape 2025 | 2025 | 467 startups |
| CIEB — Relatório Anual 2024 | 2024 | Políticas públicas, IA |
| IMARC Group | 2025 | US$6bi → US$15,6bi (2034) |

## 📚 Bases Acadêmicas Consultadas (Artigo)
- SciELO (scielo.br)
- ERIC (eric.ed.gov)
- BDTD/CAPES (bdtd.ibict.br)
- Portal de Periódicos CAPES (periodicos.capes.gov.br)
- Google Scholar
- Redalyc

---

## 🛠️ Tecnologias

- **HTML5 / CSS3 / JavaScript** (Vanilla, arquivo único)
- **Chart.js 4.4** (via CDN jsDelivr) — 14 gráficos interativos
- **Font Awesome 6.4** (via CDN) — ícones
- **Google Fonts** — Inter

---

## 🔜 Próximos Passos Sugeridos

- [ ] Adicionar filtros por ano e região nas tabelas
- [ ] Integrar mapa do Brasil com dados regionais (D3.js/SVG)
- [ ] Conectar à API Startupbase para dados em tempo real
- [ ] Criar modo escuro
- [ ] Exportar relatório em PDF
- [ ] Adicionar buscador global de EdTechs
- [ ] Ampliar banco de dados de players para 200+

---

*Elaborado com base no Mapeamento EdTech 2020 (CIEB/Abstartups) e triagem web + levantamento bibliográfico atualizado até Abril/2025. Formatação ABNT NBR 6022/6023:2018.*
