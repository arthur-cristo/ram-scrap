# O aumento no preço das memórias RAM entre 2025 e 2026 foi causado pela demanda de IA?

## UC Análise de Dados e Big Data  
UNIFACS — 2026.1  

**Aluno:** Arthur Cristo e Silva  
**RA:** 1272323659  

---

# Objetivo do Estudo

O objetivo deste projeto é investigar possíveis causas para o aumento expressivo no preço das memórias RAM no mercado brasileiro entre novembro de 2025 e maio de 2026, analisando fatores econômicos, estruturais e tecnológicos relacionados ao crescimento da Inteligência Artificial.

---

# Base de Dados

Os dados utilizados neste estudo foram coletados através de um sistema de **web scraping desenvolvido em Python**.

A coleta foi realizada no site:

- https://meupc.net/

O MeuPC.net reúne preços dos principais varejistas de hardware e peças de informática do Brasil, permitindo acompanhar a variação de preços no varejo digital brasileiro.

---

# Período Analisado

Os dados analisados compreendem o período:

- **19/11/2025 → 18/05/2026**

---

# Recorte do Estudo
O estudo considerou apenas memórias RAM DDR4 3200MHz 16GB vendidas no varejo digital nacional.
Embora as memórias **DDR5** tenham apresentado aumentos ainda maiores durante o período analisado, este estudo foi realizado utilizando principalmente memórias **DDR4**.

Motivo da escolha:

- DDR4 ainda está presente na maior parte dos computadores brasileiros;
- maior volume de dados disponíveis;
- maior representatividade no varejo consumer nacional.

---

# Tratamento dos Dados

Durante o processo de análise foram realizadas as seguintes etapas:

## Coleta
- Web scraping automatizado em Python para coleta dos preços;
- Armazenamento histórico em CSV;
- Registro dos 200 modelos mais populares encontrados no varejo digital nacional.

## Limpeza
- Conversão de preços para formato numérico;
- Padronização de datas;
- Tratamento de valores ausentes;
- Organização temporal da base;
- Remoção de outliers com preços acima de 2x ou abaixo de 0.5x da média.

Os outliers removidos incluíam:
- anúncios incorretos;
- memórias piratas;
- modelos premium/exclusivos.

Após o processo de limpeza, 55 modelos foram mantidos para análise.

A quantidade final foi considerada suficiente devido ao recorte extremamente específico do estudo:

- memórias RAM DDR4;
- 3200MHz;
- 16GB;
- vendidas no varejo digital nacional.

### Estrutura do Arquivo CSV

A base de dados bruta e tratada foi estruturada a partir das seguintes colunas (features):

| Coluna | Tipo de Dado | Descrição |
| --- | --- | --- |
| **`index`** | Inteiro | Identificador único da linha no dataset. |
| **`nome`** | Texto (String) | Nome completo e modelo do módulo de memória RAM. |
| **`url`** | Texto (String) | Link direto da página do produto no MeuPC.net. |
| **`preco`** | Numérico (Float) | Preço de tabela/parcelado do produto no varejo. |
| **`preco_pix`** | Numérico (Float) | Preço promocional para pagamento à vista via PIX. |
| **`preco_por_gb`** | Numérico (Float) | Métrica calculada ($\text{Preço} \div \text{Capacidade Total}$). |
| **`modulos`** | Inteiro | Quantidade de pentes inclusos no anúncio (ex: 1x, 2x). |
| **`capacidade`** | Inteiro | Capacidade de armazenamento em GB (filtrado em 16GB). |
| **`hash`** | Texto (String) | Identificador alfanumérico único para controle de integridade do anúncio. |
| **`datas`** | Data (`YYYY-MM-DD`) | Registro temporal exato da captura do preço. |

| index | nome | url | preco | preco_pix | preco_por_gb | modulos | capacidade | hash | 2025-11-19 | 2025-11-20 | 2025-11-21 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **1** | Kingston Fury Beast (Preto) | [Acessar](https://meupc.net/peca/64gcGS/memoria-kingston-fury-beast-kf432c16bbk216) | 935.00 | 935.00 | 58.44 | 2x8 GB | 16 | 64gcGS | — | — | 446.65 |
| **2** | Rise Mode Diamond Series (Branco) | [Acessar](https://meupc.net/peca/Yzs6v2/memoria-rise-mode-diamond-series-rm-d4-16g-3200dw) | 999.90 | 849.99 | 53.12 | 1x16 GB | 16 | Yzs6v2 | — | — | — |
| **3** | Rise Mode Z (Preto) | [Acessar](https://meupc.net/peca/bk29mL/memoria-rise-mode-z-rmd416g3200z) | 1066.61 | 1066.61 | 66.66 | 1x16 GB | 16 | bk29mL | — | 477.99 | 477.99 |
| **4** | Kingston Fury Beast (Preto) | [Acessar](https://meupc.net/peca/mng99J/memoria-kingston-fury-beast-kf432c16bb16) | 923.00 | 923.00 | 57.69 | 1x16 GB | 16 | mng99J | 499.99 | 499.99 | 470.00 |
| **5** | Husky Impulse (Preto) | [Acessar](https://meupc.net/peca/WwFPxI/memoria-husky-impulse-hrm001163222pt) | 823.40 | 699.90 | 43.74 | 1x16 GB | 16 | WwFPxI | — | — | — |
---

## Agrupamentos
Foram realizados agrupamentos temporais para facilitar a análise da tendência de preços:

- agrupamento por mês;
- cálculo da média do primeiro mês analisado;
- cálculo da média do último mês analisado;
- comparação percentual entre períodos.

---

# Técnicas de Análise

As seguintes técnicas foram utilizadas:

- análise temporal;
- comparação percentual;
- média de preços;
- visualização gráfica;
- comparação contextual com indicadores econômicos;
- análise qualitativa baseada em notícias do setor.

---

# Resultado Observado

Durante o primeiro mês analisado:

```text
Preço médio: R$ 581,68
```

Durante o último mês analisado:

```text
Preço médio: R$ 1081,05
```

Variação percentual: **85,9%**

---

# Comportamento do Gráfico

A análise temporal mostra que:

- o aumento ocorre rapidamente entre dezembro e janeiro;
- após a forte alta, os preços entram em um novo patamar;
- posteriormente, os valores passam a apresentar relativa estabilização.

Isso sugere uma possível mudança estrutural do mercado, e não apenas uma oscilação temporária de curto prazo.

---

# Indicadores Econômicos

## Inflação (IGP-M)

Período:
- 11/2025 → 04/2026

Resultado:
- inflação acumulada de aproximadamente **3,19%**

Fonte:
- https://www3.bcb.gov.br/CALCIDADAO/publico/corrigirPorIndice.do?method=corrigirPorIndice

---

## Dólar (USD/BRL)

Cotação:

- 19/11/2025 → R$ 5,33
- 18/05/2026 → R$ 5,00

Variação:
- aproximadamente **-6,6%**

Fonte:
- https://www.bcb.gov.br/conversao

---

# Notícias Relacionadas

# Estrutura do Mercado

Cerca de 73% do mercado global de DRAM é concentrado entre:

- Samsung
- SK hynix
- Micron

Fonte:
- https://finance.yahoo.com/markets/stocks/articles/dram-etf-holds-73-just-184509547.html

---

## Micron deixa parte do mercado doméstico

Em 3 de dezembro de 2025, a Micron anunciou a saída da marca Crucial do mercado doméstico.

Fonte:
- https://investors.micron.com/news-releases/news-release-details/micron-announces-exit-crucial-consumer-business

---

## Crescimento da demanda de memória para IA

Em 22 de dezembro de 2025, surgiram notícias afirmando que a OpenAI teria reservado até 40% do mercado de memória.

Fonte:
- https://globalcio.com/news/16062/

---

## Samsung e SK hynix alertam para escassez

Fonte:
- https://www.tomshardware.com/tech-industry/artificial-intelligence/samsung-and-sk-hynix-warn-ai-driven-memory-shortages-could-last-until-2027-and-beyond-as-hbm-demand-explodes-customers-already-reserving-supply-years-ahead-while-the-wider-dram-market-begins-to-tighten

Principais pontos:
- aumento da demanda por HBM voltada para IA;
- > “Samsung’s memory chief Kim Jaejune warned that “significant shortages” across memory products are expected to continue through at least 2027”
- > “SK Group chairman says memory chip shortage will last until 2030”

---

# Interpretação Inicial dos Resultados

Os dados analisados sugerem que:

- inflação e dólar não explicam a magnitude da alta observada;
- houve forte pressão de demanda relacionada à IA;
- fabricantes passaram a priorizar memória para infraestrutura de IA;
- o mercado entrou em um novo patamar de preços após dezembro de 2025.

O estudo não busca provar causalidade absoluta, mas identificar evidências e padrões consistentes com a hipótese analisada.

---

# Prévia da Visualização

<img width="1509" height="552" alt="image" src="https://github.com/user-attachments/assets/34b32b71-baf5-4f2c-8c78-f92be2aad883" />

O gráfico apresenta:

- evolução temporal dos preços;
- destaque visual para o primeiro e último mês;
- linhas guia relacionadas às principais notícias do período;
- média dos preços no início e no final da análise.
