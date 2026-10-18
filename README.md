# p4_mackenzie_grupo_11

# Monitoramento e Previsão do Emprego Formal no Brasil

## Tema

**Análise e previsão do saldo mensal de empregos formais no Brasil com dados do Novo CAGED, em apoio ao ODS 8 — Trabalho Decente e Crescimento Econômico.**

## Contexto

O emprego formal é um indicador importante da atividade econômica e das condições do mercado de trabalho. O Novo CAGED reúne mensalmente as movimentações de trabalhadores com carteira assinada no Brasil, registrando admissões e desligamentos.

Este projeto utiliza os microdados oficiais do Ministério do Trabalho e Emprego para construir séries temporais do saldo de empregos formais e projetar sua evolução nos meses seguintes. Além da previsão, a análise busca identificar meses com comportamento incomum, como a forte queda observada durante a pandemia de COVID-19.

O trabalho está alinhado ao **Objetivo de Desenvolvimento Sustentável 8 (ODS 8)** da Agenda 2030 da ONU: promover o crescimento econômico sustentado, inclusivo e sustentável, o emprego pleno e produtivo e o trabalho decente para todas as pessoas.

## Pergunta de pesquisa

**Como o saldo mensal de empregos formais evolui no Brasil e qual será sua tendência nos próximos meses, considerando os diferentes setores econômicos ou unidades da federação?**

## Objetivo geral

Analisar e prever o saldo mensal de empregos formais no Brasil a partir dos dados do Novo CAGED.

## Objetivos específicos

- Obter os dados brutos oficiais do Novo CAGED diretamente da fonte governamental por meio de um script próprio.
- Calcular o saldo de empregos mensais: **admissões − desligamentos**.
- Agregar os resultados por setor econômico (CNAE) e/ou unidade da federação.
- Explorar tendência, sazonalidade e variações no mercado formal de trabalho.
- Treinar e comparar modelos de séries temporais, como SARIMA, Prophet ou o modelo definido na disciplina.
- Projetar o saldo de empregos para os próximos meses.
- Detectar e interpretar anomalias, isto é, meses com comportamento muito diferente do esperado.

## Base de dados

- **Fonte:** Novo CAGED — Ministério do Trabalho e Emprego (MTE).
- **Unidade de análise:** movimentações mensais de admissões e desligamentos no emprego formal.
- **Recortes possíveis:** Brasil, unidades da federação, municípios e setores econômicos.
- **Variável principal:** saldo de movimentação, calculado pela diferença entre contratações e demissões.

Os microdados são públicos e podem ser obtidos na página oficial do Ministério do Trabalho e Emprego: <https://www.gov.br/trabalho-e-emprego/pt-br/assuntos/estatisticas-trabalho/microdados-rais-e-caged>.

> **Atenção metodológica:** a partir de janeiro de 2020, o Novo CAGED passou a ser produzido com informações do eSocial, do CAGED e do Empregador Web. Por isso, o projeto deve priorizar a série iniciada em 2020 ou tratar cuidadosamente comparações com períodos anteriores.

## Metodologia proposta

1. **Coleta:** baixar os arquivos brutos do Novo CAGED diretamente da fonte oficial usando um script do projeto.
2. **Preparação:** padronizar colunas, selecionar o período de estudo e validar dados ausentes ou inconsistentes.
3. **Agregação:** calcular, para cada mês e recorte escolhido, o total de admissões, desligamentos e saldo de empregos.
4. **Análise exploratória:** visualizar a série temporal, sua tendência, sazonalidade e possíveis quebras estruturais.
5. **Modelagem:** dividir a série em treino e teste temporal; estimar modelos como SARIMA, Prophet ou outro método solicitado pela disciplina.
6. **Avaliação:** comparar as previsões com os valores reais por métricas como MAE, RMSE ou MAPE.
7. **Previsão:** gerar projeções para os próximos meses com intervalos de incerteza.
8. **Anomalias:** sinalizar meses cujos valores observados se afastem significativamente do comportamento previsto pelo modelo.

## Resultados esperados

- Séries mensais do saldo de empregos formais por setor ou estado.
- Visualizações de tendência e sazonalidade.
- Comparação objetiva entre modelos de previsão.
- Projeção de curto prazo do mercado de trabalho formal.
- Identificação de períodos atípicos, incluindo os efeitos da pandemia, quando presentes no recorte analisado.

## Limitações

- O Novo CAGED retrata o **emprego formal**; não representa integralmente trabalhadores informais, autônomos, MEIs ou trabalho por plataformas.
- Previsões representam tendências condicionadas ao histórico disponível e não garantem eventos econômicos futuros.
- Mudanças de metodologia e revisões na fonte podem afetar a comparabilidade entre períodos.

## Estrutura do repositório

```text
.
├── data/
│   ├── raw/           # arquivos originais baixados da fonte oficial
│   └── processed/     # bases tratadas e agregadas
├── notebooks/         # análise exploratória e modelagem
├── src/               # scripts de coleta, tratamento e previsão
├── outputs/           # gráficos, tabelas e previsões finais
└── README.md
```

## Tecnologias previstas

- Python
- pandas
- statsmodels (SARIMA)
- Prophet, se adotado na disciplina
- matplotlib e/ou seaborn

## Referências

- Ministério do Trabalho e Emprego. Novo CAGED e microdados: <https://www.gov.br/trabalho-e-emprego/pt-br/assuntos/estatisticas-trabalho/microdados-rais-e-caged>.
- Nações Unidas. Objetivo de Desenvolvimento Sustentável 8: <https://brasil.un.org/pt-br/sdgs/8>.
