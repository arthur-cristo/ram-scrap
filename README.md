<img width="1508" height="552" alt="image" src="https://github.com/user-attachments/assets/a13b1fd0-2d90-46ea-bb0b-be01975c5409" /># O aumento no preço das memórias RAM entre 2025 e 2026 foi causado pela demanda de IA?

## UC Análise de Dados e Big Data

UNIFACS — 2026.1

**Aluno:** Arthur Cristo e Silva
**RA:** 1272323659

---

# Objetivo do Estudo

Este projeto investiga possíveis causas para o aumento expressivo no preço das memórias RAM entre novembro de 2025 e maio de 2026, analisando fatores econômicos, estruturais e tecnológicos relacionados ao crescimento da Inteligência Artificial (IA).

---

# Base de Dados

Os dados foram coletados por meio de um sistema de **web scraping em Python** desenvolvido especificamente para o projeto.

Fonte utilizada:

* [MeuPC.net](https://meupc.net?utm_source=chatgpt.com)

O site reúne preços de diversos varejistas brasileiros de hardware, permitindo acompanhar a evolução do mercado nacional de memórias RAM.

---

# Período Analisado

* **21/11/2025 → 20/05/2026**

---

# Recorte do Estudo

O estudo analisou:

* memórias DDR4 3200MHz;
* capacidade total de 16GB;
* produtos vendidos no varejo digital brasileiro.

Também foi realizada uma análise complementar com memórias **DDR5**, que apresentaram aumentos ainda mais agressivos durante o período.

A escolha da DDR4 ocorreu por:

* maior presença no mercado brasileiro;
* maior volume de dados disponíveis;
* maior representatividade no segmento consumer.

---

# Metodologia

## Coleta de Dados

* web scraping automatizado em Python;
* coleta histórica diária de preços;
* armazenamento em CSV;
* monitoramento dos modelos mais populares do varejo nacional.

## Tratamento dos Dados

Foram realizadas:

* conversão de preços para formato numérico;
* padronização de datas;
* tratamento de valores ausentes;
* organização temporal;
* remoção de outliers.

Os outliers removidos incluíam:

* anúncios incorretos;
* modelos premium/extremos;
* memórias com preços incompatíveis com o mercado.

Após os filtros:

* **DDR4:** 38 modelos válidos;
* **DDR5:** 19 modelos válidos.

---

# Estrutura da Base de Dados

| Coluna         | Descrição                          |
| -------------- | ---------------------------------- |
| `nome`         | Modelo da memória RAM              |
| `preco`        | Preço atual                        |
| `preco_pix`    | Preço à vista                      |
| `preco_por_gb` | Relação preço/capacidade           |
| `modulos`      | Quantidade de módulos              |
| `capacidade`   | Capacidade total                   |
| `popularidade` | Indicador de relevância do anúncio |
| `datas`        | Histórico temporal dos preços      |

---

# Técnicas Utilizadas

* análise temporal;
* médias móveis;
* comparação percentual;
* visualização gráfica;
* agrupamento mensal;
* análise contextual com notícias e indicadores econômicos.

---

# Resultados Observados

## DDR4

<img width="1655" height="552" alt="image" src="https://github.com/user-attachments/assets/de6490cd-65a4-4143-b1d0-f520e68ba891" />

A análise mostra que o aumento acelera fortemente entre dezembro de 2025 e janeiro de 2026, seguido por estabilização em um novo patamar de preços, mas com tendencia a aumentar.

---

## DDR5

As memórias DDR5 apresentaram comportamento ainda mais agressivo.

<img width="1508" height="552" alt="image" src="https://github.com/user-attachments/assets/cb794642-1b03-4600-adc5-892d8ef39caf" />

A análise mostra que o crescimento muito maior, com aumento percentual de 235% no pico, mas com estabilização e tendencia a diminuir.

---

# Indicadores Econômicos

## Inflação (IGP-M)

Período:

* 11/2025 → 04/2026

Resultado acumulado:

```text
≈ 3,19%
```

Fonte:

* [Banco Central do Brasil - Calculadora do Cidadão](https://www3.bcb.gov.br/CALCIDADAO/publico/corrigirPorIndice.do?method=corrigirPorIndice)

---

## Dólar (USD/BRL)

Cotação:

* 21/11/2025 → R$ 5,39
* 20/05/2026 → R$ 5,00

Variação:

```text
≈ -7,23%
```

Fonte:

* [Banco Central do Brasil - Conversão de Moedas](https://www.bcb.gov.br/conversao)

Os dados indicam que nem inflação nem dólar explicam a magnitude da alta observada.

---

# Estrutura do Mercado

O mercado global de DRAM é altamente concentrado.

Aproximadamente 73% da produção mundial pertence a:

* Samsung;
* SK hynix;
* Micron.

Fonte:

* [Yahoo Finance - DRAM Market Share](https://finance.yahoo.com/markets/stocks/articles/dram-etf-holds-73-just-184509547.html)

---

# Eventos Relevantes do Período

## Micron reduz presença no mercado doméstico

Em dezembro de 2025, a Micron anunciou mudanças envolvendo a marca Crucial no mercado consumidor.

Fonte:

* [Micron Investor Relations](https://investors.micron.com/news-releases/news-release-details/micron-announces-exit-crucial-consumer-business)

---

## Crescimento da demanda de IA

Notícias do período indicavam aumento extremo da demanda por memória para IA e servidores.

Uma das reportagens afirmava que a OpenAI teria reservado grande parte da produção futura de memória.

Fonte:

* [Global CIO - OpenAI reservando mercado de memória](https://globalcio.com/news/16062/)

---

## Alertas de escassez

Samsung e SK hynix alertaram para possíveis shortages prolongados de memória devido ao crescimento da IA e da demanda por HBM (High Bandwidth Memory).

Fonte:

* [Tom's Hardware - AI-driven memory shortages](https://www.tomshardware.com/tech-industry/artificial-intelligence/samsung-and-sk-hynix-warn-ai-driven-memory-shortages-could-last-until-2027-and-beyond-as-hbm-demand-explodes-customers-already-reserving-supply-years-ahead-while-the-wider-dram-market-begins-to-tighten)

Principais pontos:

* aumento da demanda por HBM para IA;
* reserva antecipada de produção;
* previsão de escassez até 2027 ou além.

---

# Comparação Internacional (Estados Unidos)

Para validar se o fenômeno também ocorreu fora do Brasil, foram analisados históricos de preços no mercado norte-americano utilizando o:

* [PCPartPicker](https://pcpartpicker.com)

## Caso DDR5

### Patriot Viper Elite 5 DDR5-6000 16GB

Preço em 01/11/2025:

```text
US$ 69,99
```

Preço em 24/05/2026:

```text
US$ 199,99
```

Variação aproximada:

```text
+185,7%
```
<img width="927" height="303" alt="image" src="https://github.com/user-attachments/assets/257624ae-5a2a-4238-b116-4479dbcb79df" />

O gráfico mostra comportamento semelhante ao observado no Brasil:

* início da alta em novembro;
* explosão de preços em dezembro;
* estabilização em patamar elevado.

* Fonte: [PcPartPicker](https://pcpartpicker.com/product/G79nTW/patriot-viper-elite-5-16-gb-1-x-16-gb-ddr5-6000-cl30-memory-veb516g6030w?history_days=365)

---

## Caso DDR4

### Kingston Fury Beast DDR4-3200 16GB

Preço em 01/11/2025:

```text
US$ 100,18
```

Preço em 20/05/2026:

```text
US$ 214,26
```

Variação aproximada:

```text
+113,87%
```
<img width="929" height="309" alt="image" src="https://github.com/user-attachments/assets/c878dff8-cecd-4601-9835-2253f55d8e30" />

Assim como no Brasil, o DDR4 apresentou crescimento mais lento e menos explosivo que o DDR5, mas ainda assim extremamente elevado.
* Fonte: [PcPartPicker](https://pcpartpicker.com/product/6YfnTW/kingston-fury-beast-16-gb-2-x-8-gb-ddr4-3200-cl16-memory-kf432c16bbk216?history_days=365)
---

# Conclusão

Os dados analisados sugerem forte correlação entre o crescimento da demanda por infraestrutura de IA e o aumento global no preço das memórias RAM.

Os principais indícios encontrados foram:

* inflação baixa no período;
* queda do dólar frente ao real;
* aumento simultâneo em diferentes países;
* concentração extrema da produção mundial;
* crescimento acelerado da demanda por HBM e IA;
* alertas públicos de escassez emitidos pelos fabricantes.

O estudo não busca provar causalidade absoluta, mas apresenta evidências consistentes de que a expansão da Inteligência Artificial contribuiu significativamente para a mudança estrutural observada no mercado de memórias entre 2025 e 2026.
