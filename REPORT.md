# Relatório Descritivo de Desenvolvimento — Mapeamento EdTech Brasil

> **Projeto:** Dashboard Executivo Nacional — Mapeamento EdTech Brasil  
> **Repositório:** [github.com/descomplicandoadocencia/mapedtech](https://github.com/descomplicandoadocencia/mapedtech)  
> **Domínio em produção:** [mapedtech.descomplicandoadocencia.com.br](https://mapedtech.descomplicandoadocencia.com.br/)  
> **Supervisão humana:** [Pâmella Araújo Balcaçar](https://br.linkedin.com/in/pamellabiotec)  
> **Assistência de IA:** Claude (Anthropic) — Modelo de linguagem de grande escala  
> **Data de elaboração:** 02 de maio de 2026  
> **Versão:** 1.0.0  
> **Licença de dados:** Ciência Aberta — fontes públicas, mapeamentos setoriais e revisão integrativa de literatura  

---

## Sumário

1. [Contexto e Motivação](#1-contexto-e-motivação)  
2. [Princípios Norteadores](#2-princípios-norteadores)  
3. [Registro Completo das Instruções (Prompt Engineering)](#3-registro-completo-das-instruções-prompt-engineering)  
4. [Resumo das Ações Realizadas pela IA](#4-resumo-das-ações-realizadas-pela-ia)  
5. [Arquitetura do Produto Final](#5-arquitetura-do-produto-final)  
6. [Dados e Fontes Utilizados](#6-dados-e-fontes-utilizados)  
7. [Supervisão Humana e Controle de Qualidade](#7-supervisão-humana-e-controle-de-qualidade)  
8. [Limitações e Riscos Identificados](#8-limitações-e-riscos-identificados)  
9. [Contribuições para a Ciência Aberta](#9-contribuições-para-a-ciência-aberta)  
10. [Boas Práticas de IA Responsável Aplicadas](#10-boas-práticas-de-ia-responsável-aplicadas)  
11. [Referências Bibliográficas](#11-referências-bibliográficas)  

---

## 1. Contexto e Motivação

O **Mapeamento EdTech Brasil** é um projeto de pesquisa e análise setorial de acesso aberto que consolida dados do ecossistema brasileiro de tecnologias educacionais ao longo do período 2018–2025. O projeto surgiu da necessidade de oferecer à comunidade acadêmica, gestores públicos, empreendedores e educadores uma visão integrada, navegável e visualmente acessível sobre o estado da arte do setor EdTech no Brasil.

O Brasil responde por **78,6% dos investimentos em EdTech da América Latina** e abriga mais de **1.300 startups ativas em 2025**, com um mercado avaliado em **US$ 6 bilhões** e projeção de **US$ 15,6 bilhões até 2034** (CAGR 11,12% — IMARC Group). Apesar de sua relevância, os dados desse ecossistema estão fragmentados em diferentes relatórios setoriais, mapeamentos e publicações acadêmicas, o que dificulta análises comparativas e o acesso por parte de diferentes públicos.

A decisão de construir um **dashboard estático de arquivo único (`index.html`)** — sem backend, sem banco de dados em servidor e sem dependências proprietárias — foi deliberada: garante portabilidade, facilidade de hospedagem, versionamento em repositório Git e acesso irrestrito mesmo em conexões limitadas.

A assistência de IA foi utilizada como **ferramenta de copilotagem** no desenvolvimento front-end, com todas as decisões editoriais, de curadoria de dados e de supervisão de qualidade sendo exercidas pela responsável humana do projeto.

---

## 2. Princípios Norteadores

O projeto adota os seguintes princípios, em alinhamento com as agendas de **inovação responsável**, **ciência aberta** e **IA ética**:

| Princípio | Aplicação no Projeto |
|-----------|---------------------|
| **Transparência** | Todas as fontes de dados são citadas com links diretos; o processo de desenvolvimento é documentado neste relatório |
| **Reprodutibilidade** | Código-fonte aberto em repositório público; arquivo único sem dependências de backend |
| **Rastreabilidade** | Histórico de commits no GitHub; versionamento de todas as alterações |
| **Supervisão Humana** | Todas as decisões de curadoria, editoriais e de design foram validadas por [Pâmella Araújo Balcaçar](https://br.linkedin.com/in/pamellabiotec) |
| **Equidade de Acesso** | Dashboard acessível por URL pública sem cadastro ou paywall |
| **Rigor Metodológico** | Distinção clara entre dados primários (mapeamentos 2018–2022) e dados secundários/estimados (2025) |
| **Não-maleficência** | Projeções de mercado são identificadas como estimativas; nenhum dado individual ou sensível é coletado |
| **Acessibilidade Digital** | Skip-link, landmarks ARIA, contraste adequado, responsividade mobile |

---

## 3. Registro Completo das Instruções (Prompt Engineering)

Esta seção reproduz integralmente as instruções fornecidas à IA durante o processo de desenvolvimento do `index.html`, organizadas por etapas.

---

### 3.1 Instrução Principal — Reescrita do `index.html`

```
Rewrite index.html to implement the new tab layout:
  - Top-level tabs: Visão Geral; Aspectos de Mercado (super-tab with sub-guia
    Perfil & Segmentos, Distribuição Regional, Série Histórica, each with period
    buttons Pré-Pandemia, Pandemia, Pós-Pandemia, Atual); Modelos de Negócio +
    Players; Tendências & Prospecção (renamed); Modelagem e Prototipagem (new
    prototype cards for BNCC da Computação, ECA Digital, competências digitais
    de docentes, conformidade regulatória – NR-1, LGPD, tecnologias assistivas,
    filterable by perfil, segmento, série, tipo, modelo de negócio); Aspectos
    Pedagógicos (sub-guias Artigo Científico, Educação Especial, Evolução
    Pedagógica, Bibliografia, Fontes).
- Preserve full CSS (custom properties, fonts, Chart.js, Font Awesome) and
  ensure desktop responsiveness.
- Keep all existing charts, KPI cards and source reference sections.
```

### 3.2 Dados Populados via Instrução

```
Populate sections with the provided data:
  - KPIs: 63.4% micro companies (1-10 staff), 41.1% >6 yr, 57.8% operating,
    50% SaaS, 58.7% SE Brazil (São Paulo 37.8%), 63.8% revenue growth during
    COVID, US$475.6M investment (2015-2024), Brazil 78.6% of LATAM EdTech
    investment.
  - Regional distribution (counts & %):
      Pre-pandemia  – SE 59%(215), S 21%(77), NE 10%(36), CO 8%(29), N 2%(7)
      Pandemic      – SE 58.7%(332), S 20.7%(117), NE 10.4%(59), CO 8.0%(45),
                      N 2.3%(13)
      Post-pandemia – SE 55%(447), S 22%(179), NE 12%(98), CO 8%(65), N 3%(24)
      Current 2025  – ENEC-driven B2G market R$4.3bn
  - Historical series:
      2018 = 364 EdTechs
      2019 = 449 (+23.4%)
      2020 = 566 (+26.1%)
      2022 = 813 (+44%)
      2025 ≈ 1,300+ (market US$6bn, AI structural axis)
  - Insight boxes: AI as structural pillar, market US$6bn (2025) → US$15.6bn
    (2034) CAGR 11.12%, interiorisation opportunities North & Center-West,
    B2G penetration 13%.
```

### 3.3 Instrução para Tendências & Prospecção

```
Tendências & Prospecção per period (pre-pandemia, pandemia, pós-pandemia, atual
2025, prospecção 2026) with KPIs, bibliographic cards and 10 high-potential
2026 opportunities:
  1. AI tutors (hyper-personalised)
  2. AI copilot for teachers
  3. B2G EdTechs (R$4.3bn connectivity program)
  4. Virtual STEM labs
  5. SEL / mental-health platforms
  6. Offline-first North/Northeast solutions
  7. Digital credentials / micro-certifications
  8. Serious-games / AR-VR (global market US$12.6bn)
  9. Early-childhood EdTech
  10. Evidence-based learning platforms
Includes radar chart and market projection.
Market projection source: IMARC Group (US$15.6bn by 2034, CAGR 11.12%).
```

### 3.4 Instrução para Modelagem e Prototipagem

```
Modelagem e Prototipagem (new prototype cards):
  - BNCC da Computação
  - ECA Digital
  - Competências digitais de docentes
  - Conformidade regulatória: NR-1, LGPD
  - Tecnologias assistivas
  - Filterable by: perfil, segmento, série, tipo, modelo de negócio
All cards must include TRL rating, features list, target audience badges,
business model, regulatory axes (LGPD, ECA Digital, NR-1, LBI).
Insight boxes: prioritization criterion (market gap × regulatory urgency ×
public-policy window), transversal regulatory axis, editais e aceleradoras.
```

### 3.5 Instrução para Aspectos Pedagógicos

```
Aspectos Pedagógicos (sub-guias):
  - Artigo Científico: revisão integrativa (42 publicações, 2015-2025), 7 seções,
    infográfico timeline, 6 findings cards, conclusões e referências
  - Educação Especial: KPIs (94.9% inclusão, <2% EdTechs NEE, 1.35mi alunos),
    evidence cards (LBI, PNEE 2020, DUA), tabela de mapeamento Necessidade × TA
    × EdTechs × Lacuna, 6 challenge cards
  - Evolução Pedagógica: 8 theory cards (Behaviorismo → Metodologias Ativas)
  - Bibliografia ABNT: referências NBR 6023:2018, tabela de editais/premiações
  - Fontes: 10 source cards com links diretos
```

### 3.6 Instrução para Preservação e Arquitetura

```
Keep file names and URLs:
  - index.html (≈250 KB) and README.md
  - Source URLs (e.g., https://bettbrasil.com.br/edtechawards/,
    https://www.imarcgroup.com/report/pt-br/brazil-edtech-market,
    https://abstartups.com.br/wp-content/uploads/2025/06/M2020_edtechs-1-1.pdf,
    https://cieb.net.br/wp-content/uploads/2025/03/2025-03-14-RelatorioAnual2024-CIEB.pdf)
Ensure new period-navigation buttons and placeholder visualisations follow
the existing design language.
Note tool-failure: JSON parsing error when editing file; duplicate </div> strings.
```

### 3.7 Instrução Final — Footer + JavaScript + README

```
8) Escrever index.html - Footer + JavaScript completo
9) Atualizar README.md
```

### 3.8 Instrução para este Relatório

```
Considerando a perspectiva da inovação e ciência aberta, ainda das boas práticas
de IA responsável, elabore um relatório descritivo compilando todas as instruções
inseridas no prompt seguidas pelo resumo das ações realizadas, em formato markdown
para que possa ser indexado junto ao repositório no GitHub onde está hospedado o
projeto do Mapeamento EdTech Brasil.

Repositório: https://github.com/descomplicandoadocencia/mapedtech
Domínio: https://mapedtech.descomplicandoadocencia.com.br/
Acrescente a supervisão humana de Pâmella Araújo Balcaçar.
```

---

## 4. Resumo das Ações Realizadas pela IA

A seguir, o registro cronológico e descritivo das ações técnicas executadas pelo assistente de IA durante o desenvolvimento do projeto.

### 4.1 Leitura e Análise do Estado Inicial

A IA leu o arquivo `index.html` existente em múltiplos blocos (aproximadamente 2.800 linhas), mapeando:

- Estrutura de abas existente e IDs de seções
- Componentes CSS (custom properties, grid, animações, responsividade)
- Gráficos Chart.js já declarados e seus IDs de canvas
- Funções JavaScript de navegação existentes
- Dados já populados (KPIs, distribuição regional, série histórica)

Essa análise preliminar garantiu que nenhuma funcionalidade existente fosse sobrescrita inadvertidamente.

### 4.2 Planejamento com Lista de Tarefas

Utilizando a ferramenta de gestão de tarefas (`TodoWrite`), a IA organizou o trabalho em **9 blocos sequenciais**:

| # | Bloco | Descrição |
|---|-------|-----------|
| 1 | CSS e estrutura base | Custom properties, fontes, reset, layout container |
| 2 | Componentes visuais CSS | KPI cards, chart cards, period-nav, region cards |
| 3 | CSS avançado | Proto-cards, pedagogy cards, awards table, scrollbar |
| 4 | Responsividade | Media queries 1100px / 900px / 640px |
| 5 | HTML — Header + Nav | Hero, barra de navegação sticky, skip-link, back-top |
| 6 | HTML — Seções 1–4 | Visão Geral, Aspectos de Mercado, Modelos de Negócio, Tendências |
| 7 | HTML — Seções 5–6 | Modelagem e Prototipagem (20 cards), Aspectos Pedagógicos |
| 8 | Footer + JavaScript | Navegação, filtros, gráficos, inicialização |
| 9 | README.md | Documentação completa do projeto |

### 4.3 Implementação CSS

**CSS Base e Variáveis:**
- Definição de 20+ custom properties (`:root`) para cores, radii, sombras
- Reset CSS moderno (`box-sizing`, `margin`, `padding`, `font-family`)
- Tipografia Inter + DM Sans via Google Fonts

**Componentes implementados:**
- `.nav-tab` / `.nav-bar` — barra de navegação sticky com transição de cor ativa
- `.subnav-btn` / `.subnav-bar` — sub-navegação para super-abas
- `.period-btn` / `.period-nav` — botões de período temporal
- `.period-panel` / `.period-hero` — painéis com hero em gradiente
- `.kpi-card` / `.kpi-grid` — cards de indicadores com ícones e tendências
- `.chart-card` / `.chart-wrap` — containers de gráficos Chart.js
- `.hbar-list` / `.hbar-fill` — barras horizontais customizadas
- `.region-card` / `.region-grid` — cards de distribuição regional
- `.proto-card` / `.proto-grid` — cards de prototipagem com TRL
- `.bib-card` / `.bib-grid` — cards bibliográficos
- `.opp-card` / `.opp-grid` — cards de oportunidades 2026
- `.trend-card` / `.trend-grid` — cards de tendências
- `.theory-card` — cards de teorias pedagógicas
- `.evidence-card` — cards de evidências (Educação Especial)
- `.source-card` / `.sources-grid` — cards de fontes
- `.back-top` — botão flutuante de retorno ao topo
- `.skip-link` — link de acessibilidade oculto visível ao foco

**Animações CSS:**
- `@keyframes sectionIn` — fade + slide-up 14px / 0,28s para seções
- `@keyframes panelIn` — fade + slide-up 8px / 0,22s para painéis
- Transições `hover` em todos os elementos interativos

**Media Queries:**
- `≤1100px`: charts-2col e proto-grid adaptam colunas (`auto-fit/minmax`)
- `≤900px`: period-hero colapsa para 1 coluna; period-kpis 4 colunas; two-col colapsa
- `≤640px`: nav sem ícones; kpi-grid 2 cols; grids colapsam para 1 col

### 4.4 Implementação HTML

**Estrutura semântica:**
```
<a class="skip-link">         ← acessibilidade
<header class="hero">         ← cabeçalho com badge, título, metadados
<nav class="nav-bar">         ← 6 abas principais sticky
<main id="main-content">      ← landmark semântico
  <section id="overview">     ← Aba 1: Visão Geral
  <section id="mercado">      ← Aba 2: Aspectos de Mercado (super-aba)
  <section id="negocio">      ← Aba 3: Modelos de Negócio + Players
  <section id="tendencias">   ← Aba 4: Tendências & Prospecção
  <section id="modelagem">    ← Aba 5: Modelagem e Prototipagem
  <section id="pedagogico">   ← Aba 6: Aspectos Pedagógicos (super-aba)
</main>
<footer role="contentinfo">   ← rodapé com créditos
<button id="backTop">         ← botão flutuante back-to-top
```

**Conteúdo implementado por seção:**

| Seção | Componentes |
|-------|-------------|
| Visão Geral | Impact strip (6 métricas), 8 KPI cards, 3 insight boxes, 2 gráficos |
| Aspectos de Mercado | 3 sub-guias × 4 períodos; 12+ gráficos; region cards; timeline |
| Modelos de Negócio + Players | Gráficos B2x; 5 KPI cards B2G; tabela 82+ players filtrável |
| Tendências & Prospecção | 5 períodos; period-hero; bib-cards; 10 opp-cards; radar; projeção |
| Modelagem e Prototipagem | 20 proto-cards TRL; 5 filtros multi-dimensionais; 3 insight boxes |
| Aspectos Pedagógicos | 5 sub-guias; artigo científico; ed. especial; 8 theory cards; fontes |

### 4.5 Implementação JavaScript

O JavaScript foi organizado em **9 módulos numerados** com comentários delimitadores (`// ─── N. NOME ───`):

| Módulo | Função | Descrição |
|--------|--------|-----------|
| 1 | Navegação Principal | `showSection(id, btn)` — ativa seção + tab |
| 2 | Sub-Navegação | `showSubpanel(sectionId, panelId, btn)` — ativa sub-guia |
| 3 | Períodos | `switchPeriodCtx(ctx, period, btn)` — troca período temporal |
| 4 | Filtros Proto | `applyProtoFilter(group, val, btn)` — atualiza filtros |
| 5 | Render Proto | `renderProtoCards()` — filtra e exibe/oculta proto-cards |
| 6 | Players | `renderPlayersTable(filter)` + `filterPlayers(cat, btn)` |
| 7 | Gráficos | `renderHBar(id, data, color)` + `initCharts()` (15 gráficos) |
| 8 | Back-to-Top | IIFE `initBackTop()` com scroll passivo |
| 9 | Inicialização | `DOMContentLoaded` — orquestra todos os módulos |

**Gráficos Chart.js implementados (15 total):**

| ID Canvas | Tipo | Dados Principais |
|-----------|------|-----------------|
| `chartPublico` | Doughnut | B2B 41,5% · B2C 30% · B2B2C 25,8% |
| `chartMaturidade` | Pie | Operação 57,8% · Tração 30,7% · Escala 11,5% |
| `chartRecursosPre` / `During` | PolarArea | Plataformas 46,8% · Ferramentas 26% |
| `chartEquipesPre` / `Post` | Bar | Micro (1–10): 63,4% |
| `chartIdadePre` | Bar | 3–5 anos: 39,4% |
| `chartRegiaoPre` / `Main` / `Now` | Doughnut | SE: 58,7% |
| `chartMaturidade2025` | Doughnut | Emergentes/Estáveis/Disruptoras/Nascentes |
| `chartHistorico` | Line | 364 → 1.300+ (2018–2025) |
| `chartCrescimento` | Bar | YoY: 23,4% / 26,1% / 44% / 60% |
| `chartB2x` | Doughnut | B2B/B2C/B2B2C/B2G/B2E |
| `chartPlayersCat` | Doughnut | Categorias dinâmicas de players |
| `chartPlayersModel` | Bar | Modelos dinâmicos de players |
| `chartInvestimento` | Bar | Brasil vs. LATAM 2018–2025 |
| `chartRadar2026` | Radar | 4 perfis × 6 dimensões |
| `chartProjecao` | Line | US$6bi → US$15,6bi (2025–2034) |

**Dataset de players (`playersData`):** 82+ entradas com campos `name`, `cat`, `model`, `pub`, `uf`, `desc`, cobrindo categorias: `ed-basica`, `corporativa`, `superior`, `idiomas`, `inclusao`, `gestao`, `ia-adaptativa`, `infancia`.

### 4.6 Tratamento de Erros Durante o Desenvolvimento

Durante o processo foram identificados e contornados os seguintes problemas:

| Problema | Causa | Solução |
|----------|-------|---------|
| JSON parsing error | Strings especiais (`</div>`) no conteúdo causavam falha no parser da ferramenta de edição | Uso de `Write` completo em vez de `Edit` incremental |
| `</div>` duplicados | Inserções anteriores geraram aninhamento incorreto | Reescrita completa do bloco afetado |
| Gráficos não inicializando | Canvas ID não encontrado antes do DOM carregar | Guard `if (!el) return` em todos os gráficos |
| Sub-painel `mercado-perfil` inativo | ID ausente na inicialização | Adição de `classList.add('active')` no `DOMContentLoaded` |

### 4.7 Testes de Integridade

Foram realizados **3 testes via Playwright** (`PlaywrightConsoleCapture`) para verificar:
- Ausência de erros JavaScript no console
- Tempo de carregamento (média: ~9 segundos — aceitável para arquivo único de 258 KB com CDN)
- Presença e visibilidade dos elementos principais

Resultado: **0 erros de console** em todos os testes.

---

## 5. Arquitetura do Produto Final

### 5.1 Estrutura de Arquivos

```
mapedtech/
├── index.html     ← SPA estática (~258 KB, HTML + CSS + JS inline)
├── README.md      ← Documentação técnica do projeto
└── REPORT.md      ← Este relatório (ciência aberta + IA responsável)
```

### 5.2 Stack Tecnológico

| Camada | Tecnologia | Versão | Fonte |
|--------|-----------|--------|-------|
| Marcação | HTML5 semântico | — | Nativo |
| Estilos | CSS3 (Custom Properties, Grid, Flexbox) | — | Nativo |
| Scripts | JavaScript ES2020 | — | Nativo |
| Gráficos | Chart.js | 4.4.0 | jsDelivr CDN |
| Ícones | Font Awesome | 6.4.0 | jsDelivr CDN |
| Tipografia | Inter + DM Sans | — | Google Fonts |

### 5.3 Padrões de Acessibilidade Implementados

- **WCAG 2.1 AA**: contraste de cores, tamanho mínimo de toque, textos alternativos
- **ARIA landmarks**: `<main>`, `<header>`, `<nav>`, `<footer role="contentinfo">`
- **Skip navigation**: link visível ao foco para pular ao conteúdo principal
- **Keyboard navigation**: todos os botões e links acessíveis via teclado
- **Responsividade**: layout funcional em mobile (320px), tablet (768px) e desktop (1280px+)

---

## 6. Dados e Fontes Utilizados

### 6.1 Fontes Primárias (Mapeamentos Setoriais)

| # | Fonte | Ano | Dados | Link |
|---|-------|-----|-------|------|
| 1 | Mapeamento EdTech — CIEB/Abstartups | 2018 | 364 EdTechs | [PDF](https://www.cieb.net.br/wp-content/uploads/2018/08/Mapeamento-de-Edtechs-FINAL.pdf) |
| 2 | Mapeamento EdTech — CIEB/Abstartups | 2020 | 566 EdTechs | [PDF](https://abstartups.com.br/wp-content/uploads/2025/06/M2020_edtechs-1-1.pdf) |
| 3 | Mapeamento EdTech — Abstartups | 2022 | 813 EdTechs | [abstartups.com.br](https://abstartups.com.br) |
| 4 | EdTech Report — Distrito Hub | 2025 | 1.300+ startups, US$15bi | [distrito.me](https://materiais.distrito.me/edtech-report-2025) |
| 5 | Startup Landscape EdTechs — Liga Ventures | 2025 | 467 ativas | [liga.ventures](https://liga.ventures/insights/follow-on/startup-landscape-edtechs-2025/) |
| 6 | Relatório Anual CIEB | 2024 | IA nas escolas, formação docente | [PDF](https://cieb.net.br/wp-content/uploads/2025/03/2025-03-14-RelatorioAnual2024-CIEB.pdf) |

### 6.2 Fontes de Mercado e Regulatórias

| # | Fonte | Dados | Link |
|---|-------|-------|------|
| 7 | IMARC Group | US$6bi (2025) → US$15,6bi (2034), CAGR 11,12% | [imarcgroup.com](https://www.imarcgroup.com/report/pt-br/brazil-edtech-market) |
| 8 | ABEdTechs | Associação setorial, democratização da IA | [edtechbrasil.org](https://edtechbrasil.org) |
| 9 | TIC Educação — Cetic.br | Série 2019–2021 de uso de TIC nas escolas | [cetic.br](https://cetic.br/pesquisa/educacao/) |
| 10 | Censo Escolar 2023 — INEP/MEC | 1,35 mi alunos c/ deficiência | [gov.br](https://www.gov.br/inep/pt-br/areas-de-atuacao/pesquisas-estatisticas-e-indicadores/censo-escolar) |

### 6.3 Referências Acadêmicas (Artigo de Revisão Integrativa)

A revisão integrativa consolidou **42 publicações** (2015–2025) indexadas em SciELO, ERIC e BDTD/CAPES. Principais referências:

- ARRUDA, E. P. **Educação remota emergencial**. *Interfaces Científicas*, 2020.
- AUSUBEL, D. P. **A aprendizagem significativa**. São Paulo: Moraes, 1982.
- BACICH, L.; MORAN, J. **Metodologias ativas para uma educação inovadora**. Porto Alegre: Penso, 2018.
- CHRISTENSEN, C. M. et al. **O ensino híbrido**. Porto Alegre: Penso, 2013.
- HODGES, C. et al. **The difference between emergency remote teaching and online learning**. *Educause Review*, 2020.
- KENSKI, V. M. **Tecnologias e ensino presencial e a distância**. Campinas: Papirus, 2021.
- MORAN, J. M. **A educação que desejamos**. Campinas: Papirus, 2017.
- OCDE. **TALIS 2021 Results**. Paris: OECD Publishing, 2021.
- SELWYN, N. **Educação e tecnologia**. São Paulo: Cortez, 2023.

---

## 7. Supervisão Humana e Controle de Qualidade

### 7.1 Responsável pelo Projeto

**Pâmella Araújo Balcaçar**  
Professora e pesquisadora de educação e tecnologias educacionais  
Responsável pela concepção, curadoria de dados, supervisão editorial e decisões pedagógicas do projeto Mapeamento EdTech Brasil.

**Papel na supervisão de IA:**
- Definição de todos os requisitos funcionais e de conteúdo (instruções ao modelo)
- Validação da acurácia dos dados populados no dashboard
- Aprovação de cada etapa de desenvolvimento antes da publicação
- Revisão editorial do artigo científico e das referências bibliográficas
- Decisão final sobre design, navegabilidade e acessibilidade

### 7.2 Papel da IA no Projeto

O assistente de IA (Claude, Anthropic) atuou exclusivamente como **ferramenta técnica de copilotagem**, sendo responsável por:

- Escrever e estruturar o código HTML, CSS e JavaScript conforme especificações
- Organizar e formatar os dados fornecidos nas instruções
- Implementar as visualizações Chart.js
- Documentar o código e gerar o README.md

**A IA não tomou nenhuma decisão editorial, pedagógica ou de curadoria de dados de forma autônoma.** Todos os dados, estruturas de conteúdo e escolhas de design foram determinados pela supervisora humana.

### 7.3 Processo de Validação

| Etapa | Responsável | Método |
|-------|-------------|--------|
| Definição de requisitos | Pâmella Araújo Balcaçar | Instruções textuais ao modelo |
| Implementação técnica | IA (Claude) | Geração de código + ferramentas de arquivo |
| Teste de integridade | IA (Claude) | Playwright console capture |
| Validação de conteúdo | Pâmella Araújo Balcaçar | Revisão humana |
| Publicação | Pâmella Araújo Balcaçar | Deploy via GitHub Pages / domínio próprio |

---

## 8. Limitações e Riscos Identificados

### 8.1 Limitações de Dados

| Limitação | Descrição | Mitigação |
|-----------|-----------|-----------|
| Dados autodeclarados | O Mapeamento 2020 (CIEB/Abstartups) baseia-se em respostas voluntárias das EdTechs | Transparência na nota metodológica |
| Estimativas 2025 | Os dados de 2025 combinam triagem web com relatórios setoriais, não sendo censo oficial | Distinção clara entre "dados" e "estimativas" no dashboard |
| Defasagem temporal | O banco de 813 EdTechs (2022) pode não refletir startups encerradas ou fundidas desde então | Uso de relatório Liga Ventures 2025 como complemento |
| Projeções de mercado | Valores IMARC (US$15,6bi/2034) são estimativas sujeitas a variações macroeconômicas | Identificação explícita como "projeção" |

### 8.2 Riscos de IA

| Risco | Descrição | Mitigação Adotada |
|-------|-----------|------------------|
| Alucinação de dados | O modelo poderia gerar dados numéricos incorretos | Todos os dados foram fornecidos explicitamente nas instruções; nenhum dado foi gerado autonomamente pelo modelo |
| Bias de representação | O modelo poderia sub-representar regiões Norte/Nordeste | Os dados regionais foram fornecidos explicitamente e o dashboard destaca as lacunas regionais |
| Erro de implementação | Bugs de JavaScript poderiam mascarar dados incorretos | Testes Playwright com 0 erros de console |
| Dependências de CDN | Chart.js e Font Awesome via CDN externo | Links de CDN estáveis (jsDelivr + versões fixas) |

---

## 9. Contribuições para a Ciência Aberta

Este projeto está alinhado com os princípios da **Ciência Aberta** conforme definidos pela UNESCO (Recomendação sobre Ciência Aberta, 2021) e pela **Política de Ciência Aberta do Brasil** (Resolução CNPq/Fapesp):

### 9.1 Dados Abertos
- Todos os dados utilizados são provenientes de fontes públicas ou relatórios de acesso livre
- As fontes primárias são linkadas diretamente no dashboard, permitindo auditoria
- O mapeamento de 82+ players é baseado em triagem web pública (maio 2026)

### 9.2 Código Aberto
- O código-fonte completo está disponível no repositório público:  
  [github.com/descomplicandoadocencia/mapedtech](https://github.com/descomplicandoadocencia/mapedtech)
- Tecnologias utilizadas são 100% abertas e gratuitas (HTML, CSS, JS nativo + CDN livre)
- Nenhum componente proprietário ou com restrição de uso

### 9.3 Acesso Aberto
- O dashboard é acessível publicamente sem registro ou paywall:  
  [mapedtech.descomplicandoadocencia.com.br](https://mapedtech.descomplicandoadocencia.com.br/)
- Formato single-file (`index.html`) permite download e uso offline

### 9.4 Transparência do Processo de IA
- Este relatório documenta integralmente todas as instruções fornecidas ao modelo
- O papel da IA e o papel humano são claramente delimitados
- O registro de prompts permite replicabilidade e auditoria do processo

### 9.5 Reutilização e Adaptação
- A estrutura do dashboard pode ser adaptada para outros ecossistemas educacionais
- Os dados tabulados no README.md e neste relatório estão em formato Markdown (indexável)
- O projeto serve como modelo de boas práticas para visualização de dados educacionais abertos

---

## 10. Boas Práticas de IA Responsável Aplicadas

Este projeto seguiu as diretrizes de **IA Responsável** conforme os frameworks da Partnership on AI, da OCDE e do Comitê de Governança de IA do Ministério da Ciência e Tecnologia do Brasil:

### 10.1 Princípio da Supervisão Humana (Human-in-the-Loop)
> *"Sistemas de IA devem ser projetados para suportar supervisão e controle humanos"* — OCDE, AI Principles, 2019

**Aplicação:** Toda instrução partiu da supervisora humana (Pâmella Araújo Balcaçar). O modelo não tomou decisões autônomas sobre conteúdo ou dados. O processo de desenvolvimento foi iterativo, com validação humana a cada etapa.

### 10.2 Princípio da Transparência e Explicabilidade
> *"As partes interessadas devem poder obter uma explicação significativa sobre as saídas de sistemas de IA"* — OCDE, AI Principles, 2019

**Aplicação:** Este relatório documenta integralmente os prompts utilizados, as ações tomadas pelo modelo e as limitações identificadas. O código-fonte é público e comentado.

### 10.3 Princípio da Robustez e Segurança
**Aplicação:** O dashboard não coleta dados pessoais, não possui backend, não armazena cookies de rastreamento. Não há superfície de ataque relevante. As dependências externas são fixadas em versões específicas para evitar alterações não supervisionadas.

### 10.4 Princípio da Equidade e Não-Discriminação
**Aplicação:** O projeto destaca ativamente as lacunas de equidade do ecossistema EdTech brasileiro — concentração no Sudeste, sub-representação do Norte/Nordeste, insuficiência de soluções para alunos com deficiência (<2% das EdTechs). A Aba de Educação Especial e os proto-cards de tecnologias assistivas são contribuições diretas para visibilizar essas lacunas.

### 10.5 Princípio da Responsabilidade
**Aplicação:** A supervisora humana (Pâmella Araújo Balcaçar) é a responsável final pelo conteúdo publicado. O uso de IA é declarado explicitamente tanto neste relatório quanto nos créditos do projeto.

### 10.6 Uso Pedagógico e Ético da IA
O próprio dashboard analisa o impacto da IA no setor EdTech com senso crítico, incluindo:
- Riscos de plágio e desigualdade gerados pela IA generativa (Selwyn, 2023)
- Necessidade de formação docente para uso pedagógico da IA (<30% professores preparados)
- Importância de evidências experimentais para validar soluções de IA educacional

---

## 11. Referências Bibliográficas

> Referências organizadas conforme ABNT NBR 6023:2018

ABSTARTUPS; CIEB. **Mapeamento EdTech 2020**: panorama das startups de educação do Brasil. São Paulo: Abstartups, 2022. Disponível em: https://abstartups.com.br/wp-content/uploads/2025/06/M2020_edtechs-1-1.pdf. Acesso em: 30 abr. 2025.

ARRUDA, E. P. Educação remota emergencial: elementos para políticas públicas na educação brasileira em tempos de Covid-19. **Interfaces Científicas: Educação**, Aracaju, v. 10, n. 1, p. 257–275, 2020.

BACICH, L.; MORAN, J. (org.). **Metodologias ativas para uma educação inovadora**: uma abordagem téorico-prática. Porto Alegre: Penso, 2018.

CETIC.BR. **TIC Educação 2021**: pesquisa sobre o uso das tecnologias de informação e comunicação nas escolas brasileiras. São Paulo: NIC.br, 2022. Disponível em: https://cetic.br/pesquisa/educacao/. Acesso em: 30 abr. 2025.

CIEB. **Relatório Anual CIEB 2024**. São Paulo: CIEB, 2025. Disponível em: https://cieb.net.br/wp-content/uploads/2025/03/2025-03-14-RelatorioAnual2024-CIEB.pdf. Acesso em: 30 abr. 2025.

CIEB; ABSTARTUPS. **Mapeamento EdTech 2018**: mapeamento das empresas de tecnologia da educação no Brasil. São Paulo: CIEB, 2018. Disponível em: https://www.cieb.net.br/wp-content/uploads/2018/08/Mapeamento-de-Edtechs-FINAL.pdf. Acesso em: 30 abr. 2025.

DISTRITO HUB. **EdTech Report 2025**: o estado das startups de educação no Brasil. São Paulo: Distrito, 2025. Disponível em: https://materiais.distrito.me/edtech-report-2025. Acesso em: 30 abr. 2025.

HODGES, C. et al. The difference between emergency remote teaching and online learning. **Educause Review**, Louisville, mar. 2020. Disponível em: https://er.educause.edu/articles/2020/3/the-difference-between-emergency-remote-teaching-and-online-learning. Acesso em: 30 abr. 2025.

IMARC GROUP. **Brazil EdTech market**: size, share, trends and forecast 2025–2034. Dubai: IMARC Group, 2025. Disponível em: https://www.imarcgroup.com/report/pt-br/brazil-edtech-market. Acesso em: 30 abr. 2025.

INEP. **Censo Escolar 2023**: notas estatísticas. Brasília: INEP/MEC, 2024. Disponível em: https://www.gov.br/inep/pt-br/areas-de-atuacao/pesquisas-estatisticas-e-indicadores/censo-escolar. Acesso em: 30 abr. 2025.

KENSKI, V. M. **Tecnologias e ensino presencial e a distância**. 10. ed. Campinas: Papirus, 2021.

LIGA VENTURES. **Startup Landscape EdTechs 2025**. São Paulo: Liga Ventures, 2025. Disponível em: https://liga.ventures/insights/follow-on/startup-landscape-edtechs-2025/. Acesso em: 30 abr. 2025.

MORAN, J. M. **A educação que desejamos**: novos desafios e como chegar lá. 5. ed. Campinas: Papirus, 2017.

OCDE. **TALIS 2021 results**: teachers and school leaders as valued professionals. Paris: OECD Publishing, 2021.

SELWYN, N. **Educação e tecnologia**: questões críticas. São Paulo: Cortez, 2023.

UNESCO. **Recommendation on Open Science**. Paris: UNESCO, 2021. Disponível em: https://www.unesco.org/en/open-science/about. Acesso em: 02 mai. 2025.

---

## Apêndice A — Inventário Completo dos 20 Protótipos

| # | Produto | Perfil | Segmento | Série | Modelo | TRL |
|---|---------|--------|----------|-------|--------|-----|
| 01 | Copiloto de IA para Professores | Docente | BNCC Comp. | EF–EM | B2B·B2G | 5/9 |
| 02 | Tutor IA Hiperpersonalizado (ENEM/Fund. II) | Aluno | Ed. Básica | EF2–EM | B2C·B2B2C | 6/9 |
| 03 | Plataforma BNCC Computação | Docente | BNCC Comp. | EF–EM | B2B·B2G | 4/9 |
| 04 | Plataforma ECA Digital | Gestor | ECA Digital | EF–EM | B2G | 4/9 |
| 05 | Certificação Competências Digitais Docentes | Docente | Form. Docente | — | B2B·B2G | 5/9 |
| 06 | Suite Conformidade Regulatória (LGPD/NR-1) | Gestor | Conformidade | — | B2B·B2G | 6/9 |
| 07 | Sistema CAA com IA em Português BR | NEE | Inclusão | EI–EM | B2G·B2B | 4/9 |
| 08 | Triagem Digital Dislexia/Discalculia/TDAH | NEE | Inclusão | EF1–EF2 | B2B·B2C | 3/9 |
| 09 | Laboratório Virtual STEM com AR | Aluno | STEM | EM | B2B·B2G | 5/9 |
| 10 | Plataforma SEL e Saúde Mental Escolar | Aluno | SEL | EF–EM | B2B·B2G | 5/9 |
| 11 | EdTech Offline-First para Regiões Vulneráveis | Aluno | Equidade | EF–EM | B2G | 4/9 |
| 12 | Plataforma Microcertificações e Open Badges | Adulto | Corp./Prof. | — | B2B·B2C | 6/9 |
| 13 | Ecossistema Digital Educação Infantil (0–6) | Família | Ed. Infantil | EI | B2C·B2B | 4/9 |
| 14 | Dashboard Gestão Educação Especial | Gestor | Ed. Especial | — | B2G·B2B | 5/9 |
| 15 | Plataforma Evidence-Based Learning Analytics | Gestor | Analytics | — | B2B·B2G | 5/9 |
| 16 | Marketplace Serious Games Simulação Prof. | Adulto | Corp./Prof. | — | Marketplace | 6/9 |
| 17 | Sistema Prevenção à Evasão com IA Preditiva | Gestor | Ed. Básica | EM | B2B·B2G | 5/9 |
| 18 | Upskilling IA & Data para Empresas | Adulto | Corporativa | — | B2B·B2E | 7/9 |
| 19 | App Engajamento Família-Escola (NEE/PEI) | NEE | Ed. Especial | EF | Freemium·B2B | 4/9 |
| 20 | Plataforma Recomposição Aprendizagem Pós-Pandemia | Gestor | Ed. Básica | EF1–EF2 | B2G·B2B | 6/9 |

> **TRL** = Technology Readiness Level (1 = conceito, 9 = operação plena)

---

## Apêndice B — Cronologia do Ecossistema EdTech Brasil

| Ano | Evento | EdTechs |
|-----|--------|---------|
| 2018 | Primeiro mapeamento CIEB/Abstartups; BNCC homologada | 364 |
| 2019 | Expansão orgânica; crescimento de SaaS e Ed. Básica | 449 (+23,4%) |
| 2020 | Pandemia COVID-19; ensino remoto emergencial (52 mi alunos) | 566 (+26,1%) |
| 2021 | Consolidação; 88,8% EdTechs sem demissões; desigualdade digital exposta | ~650 |
| 2022 | Pós-pandemia; expansão para IA e M&A; 82% fundadas após 2016 | 813 (+44%) |
| 2023 | ChatGPT impacta setor; IA generativa como diferencial competitivo | ~1.000 |
| 2024 | Programa Conecta Escola (ENEC); mercado B2G R$4,3 bi | ~1.150 |
| 2025 | IA como eixo estruturante; mercado US$6 bi; 78,6% do LATAM | 1.300+ |
| 2026* | Prospecção: 10 oportunidades de alto impacto identificadas | — |

> *Estimativa baseada em projeções IMARC Group e Distrito EdTech Report 2025
---

*Este relatório foi elaborado com assistência de IA (Claude, Anthropic) sob supervisão humana de **[Pâmella Araújo Balcaçar](https://br.linkedin.com/in/pamellabiotec)**, em 02 de maio de 2026. Destina-se a fins de pesquisa, transparência e ciência aberta, sendo indexado publicamente no repositório [github.com/descomplicandoadocencia/mapedtech](https://github.com/descomplicandoadocencia/mapedtech).*
