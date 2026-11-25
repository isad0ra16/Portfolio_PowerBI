<div align="center">

![Portfolio Power BI — Dados que orientam decisões](assets/01-capa.png)

![Status](https://img.shields.io/badge/status-em%20andamento-E7B545?style=flat-square) ![Área](https://img.shields.io/badge/%C3%A1rea-Business%20Intelligence-102A3A?style=flat-square) ![Power BI](https://img.shields.io/badge/Power%20BI-visualiza%C3%A7%C3%A3o-E7B545?style=flat-square) ![Power Query](https://img.shields.io/badge/Power%20Query-ETL-102A3A?style=flat-square) ![DAX](https://img.shields.io/badge/DAX-indicadores-E7B545?style=flat-square) ![Figma](https://img.shields.io/badge/Figma-UX%2FUI-102A3A?style=flat-square)

[Marketing](#campanhas-de-marketing) · [Vendas](#análise-de-vendas) · [Preparação](#preparação-dos-dados) · [Indicadores](#indicadores-e-análise) · [Design](#design-e-experiência) · [Arquivos](#como-explorar-os-projetos)

</div>

## Dados que orientam decisões

> **Status: em andamento.** Ainda estou concluindo minha formação em Power BI. Os dashboards apresentados são entregas dos estudos realizados até o momento, e novos projetos serão acrescentados progressivamente.

Reuni neste repositório dois estudos de Business Intelligence desenvolvidos durante minha formação em Power BI. Minha proposta foi trabalhar não apenas a apresentação dos indicadores, mas também as etapas que permitem construir um painel útil: compreender as perguntas de negócio, preparar os dados, definir métricas e organizar a experiência de leitura.

Os dois projetos abordam problemas diferentes. O primeiro investiga clientes, comportamento de compra e campanhas de marketing. O segundo concentra-se no desempenho comercial, na distribuição das vendas e nos descontos. Em ambos, utilizei Power Query, Power BI e Figma, com atenção à comunicação visual; os cálculos combinam agregações do Power BI e, no estudo de marketing, uma medida DAX explícita.

| Estudo | Questão central | Entrega |
| --- | --- | --- |
| Campanhas de marketing | Como compreender o perfil dos clientes e a resposta às campanhas? | Painel com quatro visões analíticas |
| Análise de vendas | Como acompanhar vendas, descontos e distribuição geográfica? | Dashboard de indicadores comerciais |

Os arquivos `.pbix` e a documentação de cada estudo estão nas respectivas pastas. São projetos de formação, não trabalhos de consultoria para empresas reais.

## Campanhas de marketing

![Campanhas de marketing — conhecer o cliente para entender a resposta](assets/02-campanhas-marketing.png)

Desenvolvi este estudo durante o curso de Power BI da Data Science Academy, que ainda estou concluindo. O objetivo foi organizar as informações de clientes e campanhas para investigar padrões de consumo e comparar a resposta de diferentes grupos às ações de marketing.

Uma análise de campanhas precisa ir além de apresentar a quantidade de respostas positivas. É importante compreender quem respondeu, como o comportamento de compra varia entre perfis e quais canais concentram as compras. Organizei o painel em quatro perspectivas complementares.

### Quatro visões, quatro formas de investigar

| Visão | O que explorei | Pergunta de negócio |
| --- | --- | --- |
| Perfil do cliente | Escolaridade, estado civil, distribuição geográfica e compras por canal (loja, web e catálogo), incluindo compras com desconto | Quem são os clientes e por quais canais compram? |
| Comportamento de compra | Renda, gastos e composição familiar, incluindo filhos e adolescentes | Como o perfil familiar e econômico se relaciona com o consumo? |
| Performance das campanhas | Efetividade das campanhas: comparação entre clientes que compraram e os que não compraram após as campanhas, considerando perfil e renda | Que diferenças aparecem entre os grupos de resposta? |
| Padrões por país | Distribuição geográfica, gastos por ano e categorias de produto | Como os padrões de consumo variam entre países e períodos? |

### Da leitura ao uso dos indicadores

A separação das quatro visões permite começar pelo perfil dos clientes e avançar para o comportamento e a resposta às campanhas. Por exemplo, comparar compras em loja, web e catálogo ajuda a investigar os canais utilizados; cruzar características familiares com gastos permite explorar diferenças de comportamento.

Essas comparações podem orientar hipóteses de segmentação, mas não demonstram, por si só, que uma campanha ou característica familiar causou o resultado observado. A documentação atual não registra valores consolidados de conversão, retorno de investimento ou impacto comercial; por isso, não atribuo ganhos financeiros ao painel.

**Explore o projeto:** [documentação de campanhas de marketing](.Dashboards/Analise%20de%20Campanhas%20de%20marketing/Analise%20de%20Campanhas%20de%20marketing.md) · [pasta com o PBIX](.Dashboards/Analise%20de%20Campanhas%20de%20marketing/).

## Análise de vendas

![Análise de vendas — do desempenho comercial às oportunidades](assets/03-analise-vendas.png)

Neste projeto, construí um painel para acompanhar o desempenho comercial e apliquei conceitos de UX/UI estudados no curso de Sayuri Valente (Xperiun). Desenvolvi a identidade visual e a estrutura da interface no Figma, buscando uma leitura rápida e organizada das métricas.

### Perguntas que orientaram o painel

| Pergunta | Indicador ou recorte |
| --- | --- |
| Qual é o valor total de vendas? | Valor total vendido |
| Quantas vendas houve por categoria? | Quantidade de vendas por categoria de produto |
| Como as vendas se distribuem geograficamente? | Quantidade de vendas por país e prioridade de entrega |
| Como os descontos variam entre produtos? | Média de desconto por subcategoria |
| Quais países têm maior valor total de vendas? | Valor total de vendas por país, em mapa |

### Como interpretar as métricas

Os visuais deste dashboard utilizam agregações automáticas do Power BI, aplicadas diretamente às colunas da tabela. Não identifiquei medidas DAX personalizadas nos visuais:

| Operação identificada no PBIX | Visuais em que aparece |
| --- | --- |
| Soma de `Total_Vendas` | Cartão de valor total e mapa por país |
| Contagem de `ID_Pedido` | Vendas por categoria e vendas por país e prioridade de entrega |
| Média de `Desconto` | Desconto médio por subcategoria |

O painel também inclui filtros de país, segmento e ano.

A quantidade de vendas corresponde à contagem de valores não vazios de `ID_Pedido`. Ela não deve ser confundida automaticamente com quantidade de unidades vendidas nem com pedidos distintos, já que um mesmo pedido pode ocupar mais de uma linha. Da mesma forma, o valor total de vendas descreve o volume monetário agregado e não equivale a uma média por pedido ou por país.

A análise por país, categoria e prioridade de entrega oferece formas de investigar o desempenho comercial. A leitura dos descontos pode indicar diferenças entre grupos de produtos, mas, sem medidas complementares de margem e custo, não permite concluir que descontos maiores aumentam a lucratividade.

**Explore o projeto:** [documentação de análise de vendas](.Dashboards/Dashboard%20de%20Vendas/Dashboard%20de%20Vendas.md) · [pasta com o PBIX](.Dashboards/Dashboard%20de%20Vendas/).

## Preparação dos dados

![Preparação dos dados — Power Query e modelagem](assets/04-preparacao-dados.png)

A construção de um dashboard começa antes da escolha dos gráficos. Entendo o painel como uma camada de apresentação de dados preparados para responder às perguntas analíticas, e não apenas como um conjunto de visuais.

No estudo de marketing, apliquei limpeza e padronização, remoção de duplicidades, modelagem dimensional, criação de relacionamentos e definição de cardinalidades. No estudo de vendas, trabalhei o tratamento dos dados no Power Query e a preparação do modelo para os indicadores comerciais.

| Etapa | Papel na construção do painel |
| --- | --- |
| Power Query | Tratar inconsistências e preparar os dados para análise |
| Modelagem | Organizar as tabelas e os campos relevantes às perguntas de negócio |
| Relacionamentos | Permitir que informações de diferentes tabelas sejam analisadas em conjunto |
| Cardinalidade | Definir a multiplicidade das relações de modo coerente com as chaves e a granularidade |
| Camada analítica | Disponibilizar uma estrutura sobre a qual as medidas e os visuais possam operar |

### Por que essa etapa importa?

A qualidade da visualização depende da qualidade do modelo. Uma relação inadequada entre tabelas pode produzir totais incorretos; registros duplicados podem inflar indicadores; categorias inconsistentes podem fragmentar uma análise. Por isso, o tratamento e a modelagem são partes essenciais do processo, não apenas uma preparação estética.

As consultas M, as tabelas e as cardinalidades específicas estão nos projetos Power BI. Esta documentação não afirma uma arquitetura física ou uma lista de transformações além do que está registrado nos estudos originais.

## Indicadores e análise

![Indicadores e análise — DAX e métricas de negócio](assets/05-indicadores-analise.png)

A função dessa camada é traduzir as perguntas de negócio em cálculos que possam ser apresentados e explorados no relatório. Nos dois projetos, distingo dois tipos de cálculo:

- **Agregações automáticas:** somas, médias e contagens que o Power BI aplica diretamente a uma coluna quando ela é colocada em um visual. São a base dos dois dashboards.
- **Medidas DAX explícitas:** cálculos definidos no modelo com uma expressão própria. No estudo de marketing, os visuais de comportamento de compra e de gastos por ano utilizam a medida `Total de Gastos`. No Dashboard de Vendas, não identifiquei medidas personalizadas nos visuais.

DAX é uma das competências que continuo desenvolvendo durante minha formação em Power BI.

| Dimensão analítica | Marketing | Vendas |
| --- | --- | --- |
| Volume | Compras por canal | Valor total e quantidade de vendas |
| Perfil e segmentação | Renda, escolaridade, estado civil e composição familiar | Categoria e subcategoria |
| Comparação | Respostas às campanhas e padrões de consumo por país | Valor total de vendas por país |
| Contexto | Gastos por período e perfil | Descontos e prioridade de entrega |

Ao definir indicadores, é importante distinguir uma soma, uma média, uma contagem e uma proporção. Cada uma tem um significado diferente e pode exigir denominadores, filtros e critérios de inclusão próprios. Em Power BI, agregações e medidas também precisam ser interpretadas no contexto de filtro dos visuais.

Por exemplo, uma taxa de resposta a campanhas exigiria definir a população de referência; a média de desconto depende de quais linhas entram no cálculo; a contagem de pedidos depende da granularidade da tabela. Estes são cuidados de interpretação, não fórmulas afirmadas como implementadas. A expressão da medida `Total de Gastos` e as demais definições do modelo podem ser inspecionadas no arquivo PBIX de cada estudo.

## Design e experiência

![Design e experiência — Figma, UX/UI e Power BI](assets/06-design-experiencia.png)

A interface também faz parte da solução analítica. Utilizei o Figma para trabalhar a identidade visual, a distribuição dos elementos, as cores e a tipografia. No projeto de vendas, desenvolvi uma identidade visual pessoal e apliquei conceitos de UX/UI estudados com Sayuri Valente.

Meu objetivo foi favorecer a leitura dos indicadores e evitar que a aparência do painel competisse com as informações que ele apresenta.

| Elemento | Intenção de design |
| --- | --- |
| Hierarquia visual | Destacar indicadores importantes antes dos detalhes |
| Organização dos elementos | Aproximar informações relacionadas e facilitar a comparação |
| Cores e tipografia | Criar consistência e estabelecer prioridades visuais |
| Distribuição por visões | Separar perguntas de negócio sem perder a unidade do relatório |
| Interatividade | Permitir a exploração dos dados no Power BI Desktop |

As artes deste README são ilustrações editoriais; não representam capturas dos dashboards nem valores medidos. Os painéis reais estão nos arquivos PBIX disponíveis no repositório.

## Como explorar os projetos

1. Acesse a pasta do estudo de interesse pelos links abaixo.
2. Baixe o arquivo `.pbix` correspondente.
3. Abra-o no Power BI Desktop para explorar as páginas, os visuais, o modelo e as medidas disponíveis.

| Projeto | Arquivos e documentação |
| --- | --- |
| Campanhas de marketing | [Abrir pasta](.Dashboards/Analise%20de%20Campanhas%20de%20marketing/) |
| Análise de vendas | [Abrir pasta](.Dashboards/Dashboard%20de%20Vendas/) |

A atualização dos dados pode depender das fontes originais utilizadas durante os cursos. A disponibilidade e a licença dessas bases não estão documentadas integralmente no repositório; não prometo reprodução completa da ingestão sem elas.

## Competências demonstradas

| Ferramenta ou competência | Aplicação |
| --- | --- |
| Power Query | Tratamento, limpeza e transformação dos dados |
| Modelagem de dados | Organização de tabelas e relacionamentos |
| DAX | Medidas e indicadores; competência em desenvolvimento durante a formação |
| Power BI | Visualização, relatórios e exploração interativa |
| Figma e UX/UI | Identidade visual e organização das interfaces |
| Business Intelligence | Tradução de perguntas de negócio em análises |

## Limites dos estudos

Os projetos foram desenvolvidos em contexto educacional. As fontes exatas, a abrangência dos dados e as fórmulas das medidas devem ser verificadas nos respectivos arquivos antes de reutilizar os indicadores em outro contexto. Não apresento efeitos causais, retornos financeiros ou resultados de empresas que não foram documentados.

---

<div align="center">

**PORTFOLIO POWER BI · DADOS QUE ORIENTAM DECISÕES.**

*Isadora Veiga · Análise de Dados e Business Intelligence*

[Perfil GitHub](https://github.com/isad0ra16) · [IMDb Analytics](https://github.com/isad0ra16/analise-imdb) · [Hospital Analytics](https://github.com/isad0ra16/Hospital-Analytics) · [AutoTech Analytics](https://github.com/isad0ra16/AutoTech-Analytics)

</div>
