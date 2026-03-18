# Conectividade-das-escolas
Análise do impacto da conectividade das escolas na qualidade da educação

| Fonte | Método | Período |
|-------|--------|---------|
| Microdados Censo Escolar (INEP) | Download automático | 2017–2025 |
| IDEB por Município – Anos Iniciais e Finais | Upload manual (planilhas limpas) | 2015–2023 |

**Arquitetura:** Bronze → Prata → Ouro → EDA → Forecasting 2035

Resumo: Este script realiza uma análise de dados de ponta a ponta para investigar se a conectividade digital das escolas brasileiras contribui para a melhoria da qualidade da educação. O pipeline começa extraindo duas fontes oficiais do INEP: os microdados do Censo Escolar (anos 2017 a 2024), de onde se obtêm indicadores como acesso à internet, banda larga, laboratório de informática e disponibilidade de computadores para alunos, e os resultados do IDEB (anos 2015 a 2023), que medem a qualidade do ensino básico. Os dados passam por uma arquitetura Medallion em três camadas — Bronze (dados brutos persistidos), Silver (dados limpos, tipados e padronizados, com criação de um Índice de Conectividade composto) e Gold (agregações por município, UF e região, com cruzamento entre conectividade e IDEB). Em cada camada, gráficos inline são gerados para permitir inspeção visual progressiva: barras de volume, histogramas, boxplots, heatmaps, violinplots e gráficos radar. Com os dados preparados, o script executa uma análise exploratória que inclui scatter plots com linhas de tendência, análise de correlação de Pearson, comparações urbana versus rural e evolução pareada das duas variáveis ao longo do tempo. Em seguida, realiza uma etapa de forecasting: ajusta um modelo de regressão linear entre conectividade e IDEB, projeta a evolução da conectividade até 2030 usando uma curva logística e simula três cenários — pessimista (estagnação), moderado (tendência atual) e otimista (investimento forte em universalização).

OBSERVAÇÃO: É necessário fazer o upload das duas planilhas juntamente para rodar o código.
