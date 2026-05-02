# Mapeamento EdTech Brasil — Dashboard Executivo Nacional

## 🎯 Visão Geral do Projeto

Dashboard executivo interativo que consolida dados do ecossistema de tecnologias educacionais do Brasil (2018–2025). Baseado nos mapeamentos CIEB/Abstartups, Distrito EdTech Report 2025, Liga Ventures Startup Landscape 2025 e IMARC Group.

**URL de acesso:** `index.html` (arquivo único, zero dependências externas de backend)

---

## ✅ Funcionalidades Implementadas

### Navegação
- 6 abas principais com navegação sticky e animações de entrada
- Super-abas com sub-navegação (Aspectos de Mercado · Aspectos Pedagógicos)
- Botões de período temporal (Pré-Pandemia / Pandemia / Pós-Pandemia / Atual / Prospecção)
- Botão **back-to-top** flutuante (aparece após 320px de scroll)
- Skip-link de acessibilidade (`<a class="skip-link">`)
- Tag semântica `<main id="main-content">` para acessibilidade
- Animações CSS suaves em todas as transições de seção e painel

### Aba 1 — Visão Geral
- Impact strip com 6 métricas-chave (EdTechs 2020/2022/2025, mercado, LATAM %)
- 8 KPI cards (micro empresas, maturidade, operação, SaaS, concentração SE, COVID, Ed. Básica, B2G)
- 3 insight boxes (liderança LATAM, IA estruturante, projeção 2034)
- Gráfico doughnut — Público-Alvo (B2B/B2C/B2B2C/B2G/B2E)
- Gráfico pie — Etapa de Desenvolvimento (Operação/Tração/Escala)

### Aba 2 — Aspectos de Mercado (super-aba)
**Sub-guia: Perfil & Segmentos** (4 períodos: Pré / Pandemia / Pós / Atual)
- Horizontal bars de segmentos por período
- Gráficos polarArea de recursos digitais
- Gráficos bar de tamanho de equipes e idade das empresas
- Painel de impacto pandemia (5 KPIs inline)
- Insights por período

**Sub-guia: Distribuição Regional** (4 períodos)
- Region cards com % e contagens (SE/S/NE/CO/N) por período
- Dados: Pré-pandemia (364→215 SE), Pandemia (566→332 SE), Pós (813→447 SE), Atual 2025
- Gráficos doughnut regionais
- Horizontal bars top-6 estados
- Insight Enec B2G R$4,3 bi

**Sub-guia: Série Histórica** (4 períodos: Completa / Pré / Pandemia / Pós)
- Gráfico line série completa 2018–2025 (364→1.300+)
- Timeline de marcos do ecossistema (5 itens)
- Gráfico bar YoY (23,4% / 26,1% / 44% / 60%)
- Cards bibliográficos por período

### Aba 3 — Modelos de Negócio + Players
- Horizontal bars — modelos de receita (SaaS 50%, Venda Direta, Assinatura…)
- Gráfico doughnut B2x
- 5 KPI cards B2G (13%, 53,4%, burocracia, POC, R$4,3bi)
- Tabela de 82+ players filtrável (9 categorias)
- Gráficos doughnut + bar dinâmicos por categoria e modelo de players

### Aba 4 — Tendências & Prospecção (5 períodos)
- **Pré-Pandemia**: period-hero com KPIs, 6 bib-cards
- **Pandemia**: period-hero com KPIs, 6 bib-cards
- **Pós-Pandemia**: period-hero com KPIs, 6 bib-cards
- **Atual 2025**: period-hero com KPIs, 8 trend-cards, horizontal bars top categorias, gráfico bar investimento LATAM
- **Prospecção 2026**: 10 opp-cards com oportunidades de alto potencial, radar chart 6-dimensões, gráfico line projeção 2025–2034, 3 insight boxes

### Aba 5 — Modelagem e Prototipagem
- Barra de filtros multi-dimensionais (Perfil / Segmento / Série / Tipo / Modelo de Negócio)
- **20 proto-cards** completos com features, público-alvo, TRL 1–9 e badges
- Contador dinâmico de protótipos visíveis
- 3 insight boxes (priorização, eixo regulatório, editais)

| Card | Produto | TRL |
|------|---------|-----|
| 01 | Copiloto de IA para Professores | 5/9 |
| 02 | Tutor IA Hiperpersonalizado (ENEM/Fund. II) | 6/9 |
| 03 | Plataforma BNCC Computação | 4/9 |
| 04 | Plataforma ECA Digital | 4/9 |
| 05 | Certificação Competências Digitais Docentes | 5/9 |
| 06 | Suite Conformidade Regulatória (LGPD/NR-1) | 6/9 |
| 07 | Sistema CAA com IA em Português BR | 4/9 |
| 08 | Triagem Digital Dislexia/Discalculia/TDAH | 3/9 |
| 09 | Laboratório Virtual STEM com AR | 5/9 |
| 10 | Plataforma SEL e Saúde Mental Escolar | 5/9 |
| 11 | EdTech Offline-First para Regiões Vulneráveis | 4/9 |
| 12 | Plataforma Microcertificações e Open Badges | 6/9 |
| 13 | Ecossistema Digital Educação Infantil (0–6 anos) | 4/9 |
| 14 | Dashboard Gestão Educação Especial | 5/9 |
| 15 | Plataforma Evidence-Based Learning Analytics | 5/9 |
| 16 | Marketplace Serious Games Simulação Profissional | 6/9 |
| 17 | Sistema Prevenção à Evasão com IA Preditiva | 5/9 |
| 18 | Upskilling IA & Data para Empresas | 7/9 |
| 19 | App Engajamento Família-Escola (NEE/PEI) | 4/9 |
| 20 | Plataforma Recomposição da Aprendizagem Pós-Pandemia | 6/9 |

### Aba 6 — Aspectos Pedagógicos (super-aba)
**Sub-guia: Artigo Científico**
- Infográfico timeline dark (2015–19 / 2020–21 / 2022–23 / 2024–25)
- 6 findings cards (conectividade, formação docente, resiliência EdTech, IA e riscos, concentração, lacuna inclusão)
- Artigo completo (revisão integrativa, 7 seções, 15 referências)

**Sub-guia: Educação Especial**
- 6 KPI cards (94,9% inclusão, <2% EdTechs NEE, 1,35mi alunos, LBI, TA+IA, AEE)
- 4 evidence cards (LBI, PNEE 2020, PBE, DUA)
- Tabela de mapeamento Necessidade × TA × EdTechs × Lacuna (7 linhas)
- 6 challenge cards
- Insight box "maior lacuna do ecossistema"

**Sub-guia: Evolução Pedagógica**
- 8 theory cards (Behaviorismo→Behaviorismo→Construtivismo→Socioconstrutivismo→Cognitivismo→Conectivismo→Personalização IA→SEL→Metodologias Ativas)
- 3 insight boxes pedagógicos

**Sub-guia: Bibliografia ABNT**
- Referências formatadas NBR 6023:2018 em 4 grupos temáticos
- Tabela de editais, premiações e aceleradoras (9 linhas com links)

**Sub-guia: Fontes**
- 10 source cards com links diretos para PDFs e relatórios originais
- Nota metodológica completa

---

## 📊 Gráficos Chart.js Implementados

| ID Canvas | Tipo | Dados |
|-----------|------|-------|
| `chartPublico` | Doughnut | B2B/B2C/B2B2C/B2G/B2E |
| `chartMaturidade` | Pie | Operação/Tração/Escala |
| `chartRecursosPre` / `During` | PolarArea | Tipos de recursos digitais |
| `chartEquipesPre` / `Post` | Bar | Tamanho de equipes |
| `chartIdadePre` | Bar | Idade das empresas |
| `chartRegiaoPre` / `Main` / `Now` | Doughnut | Distribuição regional |
| `chartMaturidade2025` | Doughnut | Emergentes/Estáveis/Disruptoras |
| `chartHistorico` | Line | Série 2018–2025 |
| `chartCrescimento` | Bar | Crescimento YoY |
| `chartB2x` | Doughnut | Modelos B2x |
| `chartPlayersCat` | Doughnut | Categorias de players (dinâmico) |
| `chartPlayersModel` | Bar | Modelos de players (dinâmico) |
| `chartInvestimento` | Bar | Investimento LATAM 2018–2025 |
| `chartRadar2026` | Radar | 4 datasets × 6 dimensões |
| `chartProjecao` | Line | Projeção US$6bi→US$15,6bi (2025–2034) |

---

## 🗂️ Estrutura de Dados

### KPIs principais (Mapeamento CIEB/Abstartups 2020)
- 63,4% micro empresas (1–10 colaboradores)
- 41,1% com 6+ anos de mercado
- 57,8% em fase de operação
- 50% adotam SaaS
- 58,7% concentradas no Sudeste (SP: 37,8%)
- 63,8% mantiveram/cresceram faturamento na COVID-19
- 13% já venderam para o governo (B2G)

### Série histórica
| Ano | EdTechs | Variação |
|-----|---------|----------|
| 2018 | 364 | — |
| 2019 | 449 | +23,4% |
| 2020 | 566 | +26,1% |
| 2022 | 813 | +44,0% |
| 2025 | 1.300+ | +60%* |

### Mercado
- Avaliação 2025: **US$ 6 bilhões**
- Projeção 2034: **US$ 15,6 bilhões** (CAGR 11,12% — IMARC Group)
- Captações 2015–2024: **US$ 475,6 milhões**
- Participação LATAM: **78,6% dos investimentos**

### Distribuição regional (2020)
| Região | % | EdTechs |
|--------|---|---------|
| Sudeste | 58,7% | 332 |
| Sul | 20,7% | 117 |
| Nordeste | 10,4% | 59 |
| Centro-Oeste | 8,0% | 45 |
| Norte | 2,3% | 13 |

---

## 🔧 Arquitetura Técnica

### Stack
- **HTML5** semântico (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- **CSS3** com custom properties (variáveis CSS), grid, flexbox, animações, media queries
- **JavaScript ES2020** (strict mode, arrow functions, destructuring, template literals)
- **Chart.js 4.4.0** via jsDelivr CDN
- **Font Awesome 6.4.0** via jsDelivr CDN
- **Google Fonts** — Inter + DM Sans

### JavaScript — Funções principais
| Função | Descrição |
|--------|-----------|
| `showSection(id, btn)` | Navega entre as 6 abas principais |
| `showSubpanel(sectionId, panelId, btn)` | Navega entre sub-abas (Mercado, Pedagógico) |
| `switchPeriodCtx(ctx, period, btn)` | Alterna painéis de período |
| `applyProtoFilter(group, val, btn)` | Filtra proto-cards por dimensão |
| `renderProtoCards()` | Renderiza/oculta cards com base nos filtros ativos |
| `renderPlayersTable(filter)` | Gera tabela de players por categoria |
| `filterPlayers(cat, btn)` | Filtra tabela de players |
| `renderHBar(id, data, color)` | Renderiza barras horizontais |
| `initCharts()` | Inicializa todos os 15 gráficos (executa uma única vez) |

### CSS — Custom Properties (`:root`)
```css
--bg, --surface, --surface2, --border
--text-1, --text-2, --text-3
--accent-1 (#1C5DFF), --accent-2 (#00C2A8), --accent-3 (#FF6B35)
--accent-4 (#7C3AED), --accent-5 (#F59E0B)
--c1…--c8  (paleta de gráficos)
--radius-sm/md/lg, --shadow-sm/md/lg
```

---

## 📱 Responsividade

| Breakpoint | Ajuste |
|-----------|--------|
| `≤1100px` | charts-2col e proto-grid adaptam colunas |
| `≤900px` | period-hero 1 coluna; period-kpis 4 colunas; two-col colapsa; infographic-timeline 2 colunas |
| `≤640px` | Nav sem ícones; kpi-grid 2 cols; period-kpis 2 cols; proto-grid 1 col; opp-grid/bib-grid 1 col |

---

## ♿ Acessibilidade

- `<a class="skip-link" href="#main-content">` — pular para conteúdo principal
- `<main id="main-content">` — landmark semântico
- `<footer role="contentinfo">` — landmark de rodapé
- Todos os botões interativos têm `title` e `aria-label` onde aplicável
- Contraste de cores adequado (texto sobre fundos claros/escuros)
- Scrollbar customizada leve e não obstrutiva

---

## 📚 Fontes Primárias

1. **Mapeamento EdTech 2020** — CIEB/Abstartups · [PDF](https://abstartups.com.br/wp-content/uploads/2025/06/M2020_edtechs-1-1.pdf)
2. **Mapeamento EdTech 2018** — CIEB/Abstartups · [PDF](https://www.cieb.net.br/wp-content/uploads/2018/08/Mapeamento-de-Edtechs-FINAL.pdf)
3. **Mapeamento EdTech 2022** — Abstartups · [abstartups.com.br](https://abstartups.com.br)
4. **EdTech Report 2025** — Distrito Hub · [distrito.me](https://materiais.distrito.me/edtech-report-2025)
5. **Startup Landscape EdTechs 2025** — Liga Ventures · [liga.ventures](https://liga.ventures/insights/follow-on/startup-landscape-edtechs-2025/)
6. **Relatório Anual CIEB 2024** · [PDF](https://cieb.net.br/wp-content/uploads/2025/03/2025-03-14-RelatorioAnual2024-CIEB.pdf)
7. **Mercado EdTech Brasil** — IMARC Group · [imarcgroup.com](https://www.imarcgroup.com/report/pt-br/brazil-edtech-market)
8. **ABEdTechs** · [edtechbrasil.org](https://edtechbrasil.org)
9. **TIC Educação** — Cetic.br · [cetic.br](https://cetic.br/pesquisa/educacao/)
10. **Censo Escolar 2023** — INEP/MEC · [gov.br](https://www.gov.br/inep/pt-br/areas-de-atuacao/pesquisas-estatisticas-e-indicadores/censo-escolar)

---

## 🚀 Próximos Passos Recomendados

### Alta Prioridade
- [ ] Adicionar gráfico de bolhas (bubble chart) para posicionar os 20 protótipos em matriz TRL × Oportunidade de Mercado
- [ ] Implementar modo escuro (dark mode toggle com `prefers-color-scheme`)
- [ ] Adicionar exportação de dados em CSV para tabela de players
- [ ] Criar painel de comparação de períodos lado a lado (Pandemia vs. Pós-pandemia)

### Média Prioridade
- [ ] Adicionar mapa coroplético do Brasil (SVG inline) para distribuição regional
- [ ] Implementar pesquisa global (`Ctrl+K`) nos players e proto-cards
- [ ] Adicionar tooltips contextuais nas KPI cards com metodologia da fonte
- [ ] Criar painel de tendências com scraping periódico de dados públicos

### Baixa Prioridade
- [ ] PWA (Progressive Web App) com cache offline via Service Worker
- [ ] Internacionalização (i18n) para versão em inglês
- [ ] Impressão/exportação em PDF via `window.print()` com estilos `@media print`
- [ ] Adicionar Google Analytics ou Plausible para métricas de uso

---

## 📝 Nota Metodológica

Os dados de 2020 são autodeclarados pelas EdTechs participantes do mapeamento CIEB/Abstartups. A série histórica 2018–2022 é baseada em dados primários dos mapeamentos. Os dados de 2026 combinam triagem web (dados secundários interpolados) com relatórios setoriais. Projeções de mercado provêm de fontes secundárias (IMARC Group, HolonIQ) e podem variar conforme metodologia.

**Última atualização:** Maio 2026  
**Formato:** Dashboard estático HTML único (single-file SPA)  
**Tamanho:** ~255 KB (HTML + CSS + JS inline)
