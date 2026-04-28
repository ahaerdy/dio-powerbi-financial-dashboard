# 📊 Dashboard Gerencial Financeiro com Power BI

> **Desafio de Projeto** — Formação NTT DATA: Engenharia de Dados com Python | [DIO](https://www.dio.me/)

[![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge)](#)
[![Formação](https://img.shields.io/badge/NTT%20DATA-Engenharia%20de%20Dados-0073CF?style=for-the-badge)](#)

---

## 📌 Sobre o Projeto

Este projeto é a entrega do **Desafio 01 do Módulo 9** da formação **NTT DATA – Engenharia de Dados com Python** na plataforma DIO. O objetivo foi criar um **Dashboard Gerencial Financeiro** no Power BI voltado para a tomada de decisões estratégicas, com foco em experiência do usuário, clareza visual e interatividade.

O dashboard foi construído com base na tabela `financials`, disponibilizada como dataset de exemplo pela instrutora do curso, e apresenta análises sobre vendas, lucros, segmentos de clientes, produtos e distribuição geográfica.

---

## 🗂️ Estrutura do Projeto

```
📁 dio-powerbi-financial-dashboard/
├── 📊 financial_dashboard.pbix       # Arquivo Power BI Desktop
├── 📂 data/
│   └── 📄 tabela_financials_projeto.xlsx  # Base de dados utilizada
├── 📂 assets/
│   ├── 🖼️ screenshot_homepage.png    # Captura de tela — Home Page
│   └── 🖼️ screenshot_principal.png   # Captura de tela — Página Principal
└── 📝 README.md
```

---

## 📂 Fonte de Dados

A base de dados utilizada é a tabela `financials`, um dataset de vendas fictício amplamente usado em tutoriais de Power BI. Ela contém **700 registros** e as seguintes colunas:

| Coluna | Descrição |
|---|---|
| `Segment` | Segmento de mercado (Government, Small Business, Enterprise, Midmarket, Channel Partners) |
| `Country` | País da venda |
| `Product` | Produto vendido (Paseo, VTT, Velo, Amarilla, Montana, Carretera) |
| `Discount Band` | Faixa de desconto aplicada |
| `Units Sold` | Quantidade de unidades vendidas |
| `Manufacturing Price` | Custo de fabricação por unidade |
| `Sale Price` | Preço de venda por unidade |
| `Gross Sales` | Receita bruta total |
| `Discounts` | Valor dos descontos concedidos |
| `Sales` | Receita líquida (Gross Sales − Discounts) |
| `COGS` | Custo dos produtos vendidos (_Cost of Goods Sold_) |
| `Profit` | Lucro final |
| `Date` | Data da transação |
| `Month Number / Month Name` | Mês da transação |
| `Year` | Ano da transação |
| `Semestres` | Classificação por semestre |
| `Continentes` | Agrupamento continental dos países |
| `Segmentos agrupados` | Reagrupamento dos segmentos |
| `Buckets` | Categorização por faixa de lucro |
| `Profit (clusters)` | Classificação do lucro por cluster |

---

## 🖥️ O Dashboard

O relatório foi desenvolvido com **2 páginas** no Power BI Desktop, com identidade visual em tons de **roxo e gradiente**, seguindo o padrão da formação.

---

### 🏠 Página 1 — Home Page

A primeira página funciona como uma **tela de apresentação e navegação** para o relatório. Ela foi projetada para dar ao usuário uma entrada visual clara antes de acessar os dados.

![Home Page do Dashboard](assets/screenshot_homepage.png)

**Elementos da Home Page:**
- **Logo** da plataforma DIO no canto superior esquerdo
- **Título destaque**: "REPORT FINANCEIRO"
- **Subtítulo**: "Aprendendo na prática com Formação Power BI Analyst"
- **Botão de navegação** → `Explorar análise` — leva diretamente à página principal do relatório (usa ação de navegação de página no Power BI)
- **Imagem 3D decorativa** com moedas, gráficos e calculadora — reforça o tema financeiro
- **Fundo**: degradê em roxo escuro (`#4A0E8F` → `#7B2FBE`)

> 💡 **Dica de UX:** A Home Page é uma boa prática em relatórios Power BI voltados para apresentação. Ela orienta o usuário antes de exibir os dados e pode conter filtros globais, índice ou sumário executivo.

---

### 📈 Página 2 — Principal (Sales Report)

A página principal concentra todas as **visualizações analíticas** do relatório. É composta por um cabeçalho com KPIs e quatro blocos de visualização.

![Página Principal — Sales Report](assets/screenshot_principal.png)

---

#### 🔢 Bloco 1 — KPIs (Cartões de Resumo)

Na parte superior da página, cinco cartões apresentam os **indicadores financeiros globais** do período selecionado:

| KPI | Valor (período do exemplo) | Descrição |
|---|---|---|
| **Total de Vendas** | 118,73 Mi | Soma total da coluna `Sales` |
| **Unidades Vendidas** | 1,13 Mi | Soma da coluna `Units Sold` |
| **Soma de Discounts** | 9,21 Mi | Total de descontos concedidos |
| **Soma de Discounts** _(duplicado)_ | 9,21 Mi | _(campo verificado na construção)_ |
| **Soma de COGS** | 101,83 Mi | Custo total dos produtos vendidos |

> 📌 Os cartões usam o visual **Card** nativo do Power BI, com formatação de número abreviado (Mi = Milhões).

---

#### 📅 Filtro de Período — Segmentação de Data

No canto superior direito da página, há um **slicer de intervalo de datas** que permite ao usuário filtrar todo o relatório por um período personalizado.

- **Tipo de visual**: Segmentação de dados (Slicer) — modo de intervalo
- **Campo**: `Date`
- No exemplo: período de `01/09/2013` a `01/12/2014`

Todos os visuais da página respondem dinamicamente ao filtro de data.

---

#### 📉 Bloco 2 — Vendas por Período (Gráfico de Área)

Um gráfico de área exibe a **evolução das vendas ao longo dos meses do ano**, permitindo identificar sazonalidades e picos de desempenho.

- **Eixo X**: Mês (`Month Name`)
- **Eixo Y**: Soma de Vendas (`Sales`)
- **Visual**: Gráfico de área (_Area Chart_)
- **Destaque**: Pico de vendas visível em **agosto**, com forte recuperação em **outubro/novembro**

> 💡 O gráfico de área é preferível ao de linhas quando se deseja enfatizar o **volume acumulado** ao longo do tempo.

---

#### 📊 Bloco 3 — Vendas x Segmento (Gráfico de Barras Horizontal)

O gráfico de barras horizontais permite comparar rapidamente o desempenho de vendas entre os **diferentes segmentos de mercado**.

- **Eixo Y**: Segmento (`Segment`)
- **Eixo X**: Soma de Vendas (`Sales`)
- **Visual**: Gráfico de barras clusterizado horizontal
- **Ranking observado** (período de exemplo):
  1. 🥇 Government — ~50 Mi
  2. 🥈 Small Business — ~30 Mi
  3. 🥉 Enterprise — ~19 Mi
  4. Midmarket — ~5 Mi
  5. Channel Partners — ~1 Mi

> O visual inclui dois botões de alternância (**Bar Chart** / **Pie Chart**), permitindo ao usuário trocar entre visualizações — recurso de **bookmarks** ou **selection panel** do Power BI.

---

#### 🏷️ Bloco 4 — Vendas por Produto (Barras Horizontais com Gradiente)

Este gráfico apresenta o **desempenho de cada produto** em termos de receita de vendas.

- **Eixo Y**: Produto (`Product`)
- **Eixo X**: Soma de Vendas (`Sales`)
- **Visual**: Gráfico de barras horizontal com escala de cor gradiente (amarelo → laranja → vermelho)
- **Ranking** (período de exemplo):
  1. Paseo — 33 Mi
  2. VTT — 21 Mi
  3. Velo — 18 Mi
  4. Amarilla — 18 Mi
  5. Montana — 15 Mi
  6. Carretera — 14 Mi

> O **Paseo** se destaca como o produto com maior receita, equivalendo à soma aproximada dos dois produtos seguintes.

---

#### 🗺️ Bloco 5 — Mapa por País (Treemap / Map Chart)

Um **Treemap** (ou mapa geográfico alternável) apresenta a **distribuição geográfica das vendas** por país.

- **Campo de grupo**: `Country`
- **Campo de valor**: Soma de Vendas (`Sales`)
- **Visual**: Treemap (com botão de alternância para _Map Chart_)
- **Países destacados**:
  - 🇺🇸 United States of America — maior área (maior volume)
  - 🇫🇷 France
  - 🇩🇪 Germany
  - 🇨🇦 Canada
  - 🇲🇽 Mexico

> O Treemap é eficiente para **comparação proporcional** entre muitos países simultaneamente. O botão de alternância para _Map Chart_ oferece contexto geográfico espacial.

---

## ⚙️ Como Reproduzir o Projeto

### Pré-requisitos

- [Power BI Desktop](https://powerbi.microsoft.com/pt-br/desktop/) (versão mais recente recomendada)
- Arquivo `tabela_financials_projeto.xlsx` (disponível na pasta `/data/` deste repositório)

### Passo a Passo

1. **Clone ou baixe** este repositório
2. **Abra o Power BI Desktop**
3. Clique em **Obter Dados → Excel** e carregue o arquivo `tabela_financials_projeto.xlsx`
4. Selecione a tabela `Planilha1` e clique em **Carregar**
5. No painel **Dados**, confirme que a tabela `financials` está disponível
6. Abra o arquivo `.pbix` incluído neste repositório para ver o relatório completo
7. Explore os filtros, botões de navegação e segmentações interativas

---

## 🎨 Design e Identidade Visual

| Elemento | Especificação |
|---|---|
| **Paleta principal** | Roxo escuro `#4A0E8F`, Roxo médio `#7B2FBE`, Branco, Dourado/Amarelo |
| **Tipografia** | Segoe UI (padrão Power BI) |
| **Tema geral** | Escuro com fundo roxo degradê |
| **Ícones** | Emojis decorativos e imagens 3D de finanças |
| **Botões** | Rounded corners com hover effect — navegação entre páginas |

---

## 📚 Conceitos de Power BI Aplicados

- ✅ **Importação de dados** via Excel (Pasta de Trabalho do Excel)
- ✅ **Criação de medidas DAX** (SUM, contagens)
- ✅ **Visuais utilizados**: Card, Gráfico de Área, Barras Horizontais, Treemap, Mapa, Slicer
- ✅ **Formatação condicional** com gradiente de cores em barras
- ✅ **Bookmarks e Selection Panel** para alternância de visuais (Bar/Pie, Treemap/Map)
- ✅ **Navegação entre páginas** via botão (ação de navegação de página)
- ✅ **Design de relatório** com foco em UX: Home Page + página analítica
- ✅ **Segmentação de dados** por data (slicer de intervalo)
- ✅ **Hierarquia de datas** com drill-down por mês

---

## 🏆 Resultado do Desafio

O desafio propunha atualizar um relatório financeiro com foco na **experiência do usuário**, seguindo boas práticas de design de dashboards no Power BI. Os principais entregáveis foram:

- [x] Página de entrada (Home Page) com identidade visual e botão de navegação
- [x] Relatório principal com KPIs claros e objetivos
- [x] Gráficos interativos com filtros dinâmicos
- [x] Alternância de visualizações via botões (bookmarks)
- [x] Layout limpo, responsivo e profissional

---

## 🔗 Referências

- [Formação NTT DATA — Engenharia de Dados com Python (DIO)](https://www.dio.me/)
- [Documentação oficial do Power BI](https://learn.microsoft.com/pt-br/power-bi/)
- [Dataset Financials — Microsoft Sample Data](https://learn.microsoft.com/en-us/power-bi/create-reports/sample-financial-download)

---

## 👤 Autor

Desenvolvido como entrega de projeto na plataforma **DIO** — Digital Innovation One.

---

> _"Dados bem apresentados transformam informação em decisão."_