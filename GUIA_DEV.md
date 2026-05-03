# Guia Técnico para Desenvolvedores — Mapeamento EdTech Brasil

Este documento complementa o `README.md` com foco em quem deseja **manter, evoluir ou reutilizar** o código do dashboard executivo `Mapeamento EdTech Brasil`.

---

## 1. Arquitetura geral

### 1.1. Tipo de aplicação

- **Single-File SPA estática**: todo o dashboard está em um único arquivo `index.html`.
- **Frontend only**: não há backend, banco de dados ou compilação/bundle.
- **Dados embutidos**: KPIs, séries históricas, players e protótipos são definidos diretamente como estruturas JavaScript e blocos HTML.

### 1.2. Tecnologias utilizadas

- **HTML5 semântico**: `header`, `nav`, `main`, `section`, `article`, `footer`.
- **CSS3**: custom properties, flexbox, grid, animações, media queries responsivas.
- **JavaScript ES2020**: `strict mode`, arrow functions, template literals, destructuring básico.
- **Chart.js 4.4.0** via CDN jsDelivr.
- **Font Awesome 6.4.0** via CDN jsDelivr.
- **Google Fonts**: Inter e DM Sans.

### 1.3. Estrutura de arquivos

- `index.html` — código completo do dashboard (HTML + `<style>` + `<script>`).
- `README.md` — visão geral e orientação de uso.
- `REPORT.md` — relatório técnico-metodológico.
- `RELATORIO_IA.md` — relato do processo de desenvolvimento com IA.

---

## 2. Organização do HTML

### 2.1. Layout principal

Ordem das principais seções dentro de `body`:

1. `a.skip-link` — link de acessibilidade para pular para o conteúdo principal.
2. `button#backTop` — botão flutuante de “voltar ao topo”.
3. `header.hero` — hero com título, contexto e metadados.
4. `nav.nav-bar` — navegação principal com 6 abas.
5. `main#main-content` — container das seções:
   - `section#overview` — Visão Geral.
   - `section#mercado` — Aspectos de Mercado (super-aba com subpainéis).
   - `section#negocio` — Modelos de Negócio + Players.
   - `section#tendencias` — Tendências & Prospecção.
   - `section#modelagem` — Modelagem & Prototipagem.
   - `section#pedagogico` — Aspectos Pedagógicos (super-aba).
6. `footer[role="contentinfo"]` — créditos, nota metodológica e links.

### 2.2. Navegação entre abas

- Cada botão da nav principal é um `button.nav-tab` com `onclick="showSection('overview', this)"` (ou id equivalente).
- A função `showSection`:
  - remove `.active` de todas as `.section` e `.nav-tab`;
  - adiciona `.active` na seção alvo e na aba correspondente.

### 2.3. Super-abas e subpainéis

- Em `#mercado` e `#pedagogico` existe uma `div.subnav-bar` com botões `button.subnav-btn`.
- Cada subpainel é um `div.subpanel` com um `id` específico, por exemplo:
  - `#mercado-perfil`, `#mercado-regional`, `#mercado-historico`;
  - `#pedagogico-artigo`, `#pedagogico-especial`, `#pedagogico-evolucao`, `#pedagogico-bibliografia`, `#pedagogico-fontes`.
- Esses botões chamam `showSubpanel('mercado', 'mercado-regional', this)` etc., que alterna `.active` nos subpainéis e faz scroll para o início da seção.

### 2.4. Navegação por períodos

- Em vários contextos há `div.period-nav` com botões `button.period-btn`.
- Exemplos de contextos (`ctx`):
  - `perfil` — perfil & segmentos;
  - `regional` — distribuição regional;
  - `tend` — tendências & prospecção.
- Cada botão chama `switchPeriodCtx('perfil', 'pre', this)` ou similar.
- A função encontra os `div.period-panel` daquele contexto e marca apenas o painel desejado como `.active` (ex.: `#perfil-pre`, `#perfil-post`, `#tend-prosp`).

---

## 3. CSS: design system e responsividade

### 3.1. Custom properties (`:root`)

O `<style>` no topo de `index.html` define um conjunto de variáveis globais de cor, tipografia, raios e sombras, usadas em todos os componentes.

Principais variáveis:

- Fundo e superfícies: `--bg`, `--surface`, `--surface2`, `--border`.
- Texto: `--text-1`, `--text-2`, `--text-3`.
- Acentos: `--accent-1` a `--accent-5`.
- Paleta para gráficos: `--c1` … `--c8`.
- Raios: `--radius-sm`, `--radius-md`, `--radius-lg`.
- Sombras: `--shadow-sm`, `--shadow-md`, `--shadow-lg`.

### 3.2. Principais componentes

Alguns componentes básicos que valem ser reutilizados:

- **Layout e navegação:** `.container`, `.nav-bar`, `.nav-tab`, `.subnav-bar`, `.subnav-btn`, `.section`, `.section-header`.
- **Cards:** `.kpi-card`, `.chart-card`, `.trend-card`, `.opp-card`, `.proto-card`, `.evidence-card`, `.challenge-card`, `.source-card`.
- **Estruturas de dados:** `.impact-strip`, `.timeline`, `.hbar-list`, `.players-table-wrap`, `.proto-grid`, `.ped-theory-grid`.

Antes de criar novos estilos, verifique se um padrão existente já atende ao uso pretendido para preservar consistência visual.

### 3.3. Responsividade

Media queries principais:

- `@media (max-width: 1100px)`:
  - `charts-2col` e `proto-grid` reduzem o número de colunas.
- `@media (max-width: 900px)`:
  - `period-hero` passa a 1 coluna; `period-kpis` em 4 colunas; `two-col` colapsa.
- `@media (max-width: 640px)`:
  - nav sem ícones, fontes menores, vários grids passam a 1 coluna.

Ao adicionar novos grids ou cards, mantenha o mesmo padrão de breakpoints.

---

## 4. JavaScript: módulos e funções

O JavaScript está no final do `index.html` dentro de um único `<script>`, organizado em blocos funcionais.

### 4.1. Navegação principal

- `function showSection(id, btn)`:
  - alterna `.active` entre as 6 seções principais;
  - atualiza o estado visual da barra de navegação.

### 4.2. Subpainéis

- `function showSubpanel(sectionId, panelId, btn)`:
  - alterna `.active` entre subpainéis de uma super-aba;
  - gerencia `.active` na subnav;
  - realiza `scrollIntoView` para a seção.

### 4.3. Navegação por períodos

- `function switchPeriodCtx(ctx, period, btn)`:
  - controla botões `.period-btn`;
  - ativa o `div.period-panel` correto dentro daquele contexto.

### 4.4. Filtros de protótipos (Modelagem & Prototipagem)

- Cada `article.proto-card` possui atributos `data-perfil`, `data-segmento`, `data-serie`, `data-tipo`, `data-modelo`.
- Botões `.prf-btn` chamam `applyProtoFilter(group, val, btn)`, que atualiza filtros ativos e chama `renderProtoCards()`.
- `renderProtoCards()`:
  - itera sobre `#protoGrid` e aplica lógica de exibição/ocultação conforme filtros;
  - atualiza o contador em `#protoCount`.

### 4.5. Tabela de players (Modelos de Negócio + Players)

- Dados estão em um array `playersData` no script, com campos:
  - `name`, `cat`, `model`, `pub`, `uf`, `desc`.
- `renderPlayersTable(filter)` popula o `<tbody>` da tabela a partir de `playersData`.
- `filterPlayers(cat, btn)` altera o filtro e atualiza o estado dos botões `.pf-btn`.

### 4.6. Gráficos Chart.js

- `initCharts()` inicializa todos os canvases existentes (doughnut, pie, bar, line, radar, polarArea).
- Os principais `id` de canvas são documentados no README (ex.: `chartPublico`, `chartMaturidade`, `chartHistorico`, `chartB2x`, `chartRadar2026`, `chartProjecao`).
- Há helper `renderHBar(id, data, color)` para construir \"barras horizontais\" com HTML em vez de Chart.js.

### 4.7. Back-to-top e inicialização

- `initBackTop()`:
  - adiciona listener de scroll com `passive: true`;
  - mostra/oculta o botão `#backTop` com a classe `.visible`.
- Um listener `DOMContentLoaded` inicializa:
  - estado padrão das abas e sub-abas;
  - gráficos;
  - tabela de players.

---

## 5. Fluxo de dados e atualização

### 5.1. Dados estáticos

- Não há chamadas a API externas; todos os valores estão embutidos.
- As fontes primárias e os detalhes metodológicos estão listados na aba **Fontes** do dashboard e na documentação (`README.md`, `REPORT.md`, `RELATORIO_IA.md`).

### 5.2. Atualizando dados

Para atualizar a série histórica, KPIs ou tabela de players:

1. Localize o bloco correspondente em `index.html` (arrays JS, KPIs em HTML, tabela de players).
2. Atualize valores e, se necessário, rótulos e textos relacionados.
3. Ajuste as tabelas de dados no `README.md`/relatórios para manter consistência.
4. Teste o comportamento visual dos gráficos e cards no navegador.

---

## 6. Padrões de contribuição

### 6.1. Estilo de código

- **HTML/CSS/JS no mesmo arquivo**: mantenha a organização existente e evite fragmentar em vários arquivos, a menos que a refatoração seja deliberada e consensual.
- Indentação e estilo:
  - 2 espaços para HTML e JS;
  - classes e nomes de id descritivos e em inglês, seguindo o padrão atual.

### 6.2. Dados e fontes

- Qualquer novo dado numérico deve vir acompanhado de:
  - fonte primária rastreável (link, relatório, DOI, etc.);
  - indicação clara se é dado primário, estimativa ou interpolação.
- Atualizações que alterem séries históricas ou KPIs devem ser refletidas:
  - no dashboard;
  - na nota metodológica;
  - se relevante, nos relatórios em Markdown.

### 6.3. Acessibilidade

- Manter e expandir boas práticas:
  - landmarks (`main`, `header`, `footer`, `role="contentinfo"` etc.);
  - uso de `aria-label` em botões icônicos;
  - contraste de cores e tamanho mínimo de fonte.
- Testar navegação por teclado após mudanças significativas.

---

## 7. Melhorias técnicas sugeridas

### 7.1. Modularização progressiva

Possíveis passos sem quebrar a arquitetura atual:

- Extrair CSS para `style.css` e JS para `app.js`, mantendo as mesmas referências no `head`/`body`.
- Criar um pequeno módulo para dados (`data/*.js` ou JSON estático) para desacoplar dados da camada de apresentação.
- Adotar um gerador estático ou bundler leve apenas se o projeto crescer muito (ex.: Vite ou Parcel).

### 7.2. Testes automatizados

- Configurar smoke tests com Playwright ou Cypress para:
  - detectar erros de JavaScript em console;
  - validar existência de elementos-chave (gráficos, cards, tabelas);
  - testar navegação entre abas, sub-abas e períodos.

### 7.3. Dark mode e PWA

Alinhado aos “próximos passos” já listados:

- Implementar **modo escuro** utilizando `prefers-color-scheme` + toggle manual.
- Evoluir para **PWA** com Service Worker para cache offline do `index.html` e assets de CDN.
- Adicionar internacionalização (i18n) com chaves de texto e arquivos de tradução.

---

## 8. Execução local

### 8.1. Clonar e servir

```bash
git clone https://github.com/descomplicandoadocencia/mapedtech.git
cd mapedtech

# Abrir direto no navegador
# ou servir com Python
python -m http.server 8000
# acessar http://localhost:8000/index.html
```

Nenhuma dependência adicional é necessária, além de um navegador moderno.

---

## 9. Governança e IA responsável

- Responsável e supervisora: **Pâmella Araújo Balcaçar**.
- Contribuições via Issues/PR são bem-vindas em `descomplicandoadocencia/mapedtech`.
- Caso utilize IA generativa para propor alterações (código, textos, dados), indique isso claramente na descrição do PR, em alinhamento com as práticas de transparência do projeto.