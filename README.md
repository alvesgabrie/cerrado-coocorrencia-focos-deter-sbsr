# cerrado-coocorrencia-focos-deter-sbsr
Este repositório inclui todos os scripts python para análise da coocorrência de focos de calor e alertas DETER no Cerrado, nos anos PRODES 2018/2019 à 2025/2026, em grids de 1 km × 1 km. Inclui processamento espacial, análise por ecorregião e geração de tabelas, gráficos e mapas.
# Coocorrência de focos de calor e DETER no Cerrado

Este repositório reúne os notebooks Python utilizados na análise
da coocorrência de focos de calor do Programa Queimadas e alertas
DETER/INPE no bioma Cerrado, entre os anos PRODES 2018/2019 e
2025/2026.

## Objetivo

Analisar a evolução anual da coocorrência no Cerrado e em suas
vinte ecorregiões, utilizando células de 1 km × 1 km.

## Metodologia

- Sistema de referência: EPSG:5880.
- Período: oito anos PRODES, de 2018/2019 a 2025/2026.
- Ano PRODES: 1º de agosto a 31 de julho do ano seguinte.
- Coocorrência: presença de focos e DETER na mesma célula
  e no mesmo ano PRODES.
- Indicador: número de células com focos e DETER dividido
  pelo número de células com DETER, multiplicado por 100.
- Células associadas a várias ecorregiões são contabilizadas
  uma vez em cada uma delas.

O indicador representa ocorrência conjunta na célula e no ano.
Não corresponde à área queimada ou desmatada e não estabelece relação causal entre os registros.

## Notebooks

Execute os notebooks na seguinte ordem:

1. `[coocorrencia_deter_focos_sbsr.ipynb]`: verifica se a célula possui presença de polígono Deter e foco de calor, se sim, retorna essa informação em campos da tabela de atributos, esse processo se repete para cada ano Prodes, são 8 arquivos .geojson de saída.
2. `[analise_estatistica_sbsr.ipynb]`: gera a tabela .csv com as informações estatísticas dos arquivos .geojson, quantos % de coocorrência para cado ano Prodes, dados por ecorregião, gráficos de linha mostrando a evolução anual destes dados.

## Dados de entrada

São utilizados quatro arquivos GeoJSON:

- Grade do Cerrado: campos `grid_id` e `borda`.
- Focos de calor: campo `DataHora`.
- Polígonos DETER: campo `VIEW_DATE`.
- Ecorregiões: campo `NAME`.

Fontes e arquivos para download: [https://1drv.ms/f/c/eb5d6c9634463ea0/IgCAPIrkFIguQI_xjHbXlQksATlSh8ud7KrlcUDiMUmJ81o?e=lJUY4a].

## Como executar

1. Baixe os notebooks e os dados de entrada.
2. Abra os notebooks no Jupyter.
3. Instale as bibliotecas indicadas em cada notebook.
4. Ajuste os caminhos dos arquivos na seção de configuração.
5. Execute as células na ordem apresentada.

## Resultados

Os notebooks geram arquivos GeoJSON anuais, tabelas CSV,
gráficos e mapas.

## Autoria

[Gabriel Alves - Projeto Prodes Cerrado - Instituto Nacional de Pesquisas Espaciais.]
