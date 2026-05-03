# Mapeamento EdTech Brasil — Dashboard Executivo Nacional

Dashboard executivo interativo que consolida dados do ecossistema de tecnologias educacionais do Brasil (2018–2025), com foco em perfil das EdTechs, aspectos de mercado, lacunas pedagógicas e oportunidades de inovação.

- **Repositório:** https://github.com/descomplicandoadocencia/mapedtech
- **Dashboard (produção):** https://mapedtech.descomplicandoadocencia.com.br
- **Arquivo principal:** `index.html` (single-page, HTML+CSS+JS inline, sem backend)

---

## Orientação de uso do projeto/REA

Este projeto é um **Recurso Educacional Aberto (REA)** em formato de dashboard de dados, pensado para apoiar:

- gestores públicos de educação;
- pesquisadores e estudantes de pós-graduação;
- empreendedores e investidores EdTech;
- professores e formadores interessados em tendências de tecnologias educacionais.

### Como acessar

- **Online:** acesse o domínio configurado para o projeto (por exemplo, `https://mapedtech.descomplicandoadocencia.com.br`).
- **Offline/local:**
  1. Clone ou baixe o repositório.
  2. Abra o arquivo `index.html` diretamente no navegador (basta duplo clique) ou sirva via um servidor estático simples.

Não há dependências de backend, build ou banco de dados: o dashboard é um **arquivo HTML único**, com CSS e JavaScript inline, usando apenas CDNs públicos para Chart.js, Font Awesome e Google Fonts.

### Público-alvo e cenários de uso

- **Gestão pública:** análise rápida de concentração regional, maturidade das EdTechs, B2G e séries históricas do setor.
- **Pesquisa acadêmica:** exploração de dados consolidados, referências bibliográficas e artigo de revisão integrativa incluído na aba “Aspectos Pedagógicos”.
- **Empreendedorismo EdTech:** identificação de lacunas e oportunidades (20 protótipos conceituais, radar de oportunidades 2026, projeções de mercado).!
- **Formação docente/cursos:** uso em disciplinas de políticas públicas, inovação educacional, tecnologia educacional, etc., como estudo de caso de visualização de dados e ciência aberta.

### Principais seções do dashboard

1. **Visão Geral:** KPIs setoriais, liderança do Brasil na América Latina, série histórica de EdTechs e tamanho de mercado.
2. **Aspectos de Mercado:** perfil das empresas, segmentos, recursos digitais, tamanho de equipe, idade das startups, distribuição regional e marcos históricos.
3. **Modelos de Negócio + Players:** modelos de receita, B2x, tabela filtrável com 80+ players e gráficos dinâmicos por categoria/modelo.
4. **Tendências & Prospecção:** leitura por períodos (pré-pandemia, pandemia, pós-pandemia, 2025, prospecção 2026) com KPIs, bibliografia e 10 oportunidades de alta prioridade.
5. **Modelagem & Prototipagem:** catálogo de 20 protótipos conceituais (proto-cards) com TRL, público-alvo, modelo de negócio, alinhamento regulatório (LGPD, LBI, ECA Digital, BNCC, etc.).
6. **Aspectos Pedagógicos:** artigo científico completo, educação especial e inclusão, evolução de paradigmas pedagógicos, bibliografia ABNT e fontes primárias.

Para reaproveitar como REA, é possível adaptar textos, dados e protótipos mantendo a estrutura visual e as boas práticas de acessibilidade já implementadas.

---

## Ciência aberta

O projeto foi desenhado explícita e intencionalmente como um caso de **ciência aberta** aplicado ao setor EdTech.

### Princípios adotados

- **FAIR (Findable, Accessible, Interoperable, Reusable):**  
  - Encontrável: repositório público no GitHub, README detalhado e relatórios técnicos versionados.  
  - Acessível: dashboard disponível em domínio aberto, sem paywall ou autenticação; estrutura single-file facilita download e uso offline.  
  - Interoperável: dados estruturados em objetos JS e tabelas HTML, passíveis de extração para outras ferramentas (planilhas, notebooks, etc.).
  - Reutilizável: código comentado, arquitetura modular no JS, licenças abertas para código e documentação.

- **Transparência de fontes de dados:**  
  - Todas as métricas e séries históricas têm **fontes primárias declaradas** (CIEB/Abstartups, Distrito, Liga Ventures, IMARC Group, Cetic.br, INEP/MEC, etc.).  
  - O README e as notas metodológicas distinguem claramente dados primários (2018–2022) de estimativas para 2025 e projeções de mercado até 2034.

- **Documentação do processo:**  
  - `REPORT.md` e `RELATORIO_IA.md` documentam arquitetura do produto, decisões metodológicas, cadeia de custódia dos dados e linha do tempo de desenvolvimento.

### Licenças

- **Código do dashboard:** licenciado sob **MIT**, permitindo uso, modificação e redistribuição para fins educacionais e de pesquisa (ver cabeçalhos de licença do repositório, se presentes).
- **Documentação e relatórios:** `REPORT.md` e `RELATORIO_IA.md` são disponibilizados sob **CC BY 4.0**, permitindo remix e adaptação com atribuição à autora/supervisora.
- **Dados:** a reutilização dos dados segue as licenças das fontes originais (relatórios CIEB, Abstartups, Distrito, Liga Ventures, IMARC Group, etc.), que devem ser consultadas caso a caso para uso comercial.

---

## IA Responsável

O projeto assume publicamente o uso de IA generativa no desenvolvimento técnico do dashboard, seguindo boas práticas de **IA responsável**, **Human-in-the-loop** e transparência recomendadas por UNESCO, OCDE e marcos regulatórios emergentes.

### Papel da IA

- A IA atuou como **copiloto técnico**, responsável por:
  - gerar e refatorar HTML, CSS e JavaScript conforme requisitos detalhados em prompts;
  - estruturar dados fornecidos pela supervisão humana em visualizações Chart.js e componentes de UI;
  - auxiliar na redação inicial do README e relatórios técnicos.

- A IA **não**:
  - criou dados quantitativos “do zero”;
  - tomou decisões de curadoria de fontes ou conclusões analíticas sem validação humana;
  - substituiu o julgamento editorial, pedagógico ou metodológico da supervisora.

### Supervisão humana (Human-in-the-loop)

- Todo o ciclo seguiu o fluxo: 

**PROMPT humano → GERAÇÃO IA → REVISÃO humana → APROVAÇÃO humana → PUBLICAÇÃO**.

- *Pâmella Araújo Balcaçar* é responsável pela concepção do projeto, curadoria de dados, arquitetura de informação, revisão do código e aprovação final dos conteúdos.
- Eventuais riscos (alucinação numérica, vieses de representação regional, interpretações equivocadas) foram mitigados por revisão manual contra as fontes primárias, com registro dessas limitações nas notas metodológicas.

### Transparência e conformidade

- O uso de IA é explicitado:
  - neste README;
  - no próprio dashboard (notas metodológicas);
  - em relatórios específicos (`REPORT.md`, `RELATORIO_IA.md`).
- Os protótipos de soluções EdTech consideram marcos regulatórios nacionais relevantes (LGPD, LBI, ECA Digital, BNCC, ENEC etc.), evitando cenários de uso que impliquem coleta de dados sensíveis sem base legal.

---

## Estrutura do repositório

- `index.html` — dashboard executivo completo (SPA estática, ~250 KB, HTML+CSS+JS inline).
- `README.md` — descrição geral do projeto, uso como REA, ciência aberta e IA responsável (este arquivo).
- `REPORT.md` — relatório descritivo de desenvolvimento, arquitetura de dados, fontes e metodologia.
- `RELATORIO_IA.md` — relato em profundidade do uso de IA, prompts e cadeia de custódia das informações.

---

## Como citar

Sugestão de referência (adaptar ao contexto):

**ABNT (exemplo):**

> BALCAÇAR, Pâmella Araújo. *Mapeamento EdTech Brasil — Dashboard Executivo Nacional*. Dashboard interativo. Descomplicando a Docência. Supervisão humana: Pâmella Araújo Balcaçar. Implementação assistida por IA generativa. 2026. Disponível em: https://mapedtech.descomplicandoadocencia.com.br. Acesso em: dia mês ano.

**APA (exemplo):**

> Balcaçar, P. A. (2026). *Mapeamento EdTech Brasil — Dashboard Executivo Nacional* [Interactive dashboard]. Descomplicando a Docência. https://mapedtech.descomplicandoadocencia.com.br