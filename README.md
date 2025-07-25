## Relatório Bancário


### 🔧 Ferramentas
Excel

Power BI

### 📝 Competências Utilizadas
Limpeza de Dados

Tratamento de Dados

Coleta de Informações

Transformação das Informações em Insights

Visualização de Dados

### 🔗 Etapas

### 🔗 Extração
Os dados foram extraídos diretamente do Power BI.

### 🔗 Transformação / Limpeza
Nas planilhas do Excel, foram realizadas exclusões de linhas e colunas em branco para garantir a integridade dos dados.

### 🔗 Análise
Iniciei o processo de análise exploratória para obter uma visão geral dos dados, verificando a presença de dados faltantes ou duplicados, a distribuição e os tipos de dados.

Depois dessa análise inicial, criei medidas DAX para auxiliar na construção das visualizações. As medidas foram:

### DAX
Transações PIX = CALCULATE(COUNTROWS('movimentações'), 'movimentações'[Forma Pagamento] = "Pix")

Transações = COUNTROWS('movimentações')

Receita = CALCULATE(SUM('movimentações'[Valor da Movimentação]), 'movimentações'[Tipo] = "recebimento")

Imposto = [Receita] * 0.15 

Despesas = -CALCULATE(SUM('movimentações'[Valor da Movimentação]), 'movimentações'[Tipo] = "Pagamento") 

Lucro = [Receita] - [Despesas] - 'movimentações'[Imposto]

margem = [Lucro] / [Receita]

Margem Auxiliar = 1 - 'movimentações'[margem]

Desvio Margem = 'movimentações'[margem] - 0.3

1 % Pix = 'movimentações'[Transações PIX] / [Transações]


🔗 Construção das Visualizações
Após criar as medidas, construí os seguintes gráficos:

Scroller: Criado para exibir informações em tempo real.

Enlighten Data Story: Adicionado para mostrar a porcentagem das movimentações com um texto explicativo.

Além disso, quatro cartões foram criados para exibir as principais métricas:

Receita: Total de dinheiro gerado pelas operações da empresa. Um aumento ou diminuição significativa na receita pode indicar tendências de mercado ou a eficácia das estratégias de vendas.

Despesas: Reflete os custos incorridos pela empresa para gerar a receita. Identificar áreas onde os custos estão aumentando pode ajudar na tomada de decisões sobre redução de gastos.

Imposto: Mostra a carga tributária da empresa. Pode ser útil para entender como os impostos afetam a lucratividade e para planejar estratégias fiscais.

Lucro: Resultado final após deduzir todas as despesas, incluindo impostos, da receita. Um dos indicadores mais importantes, pois mostra a saúde financeira da empresa.

### 🔗 Principais Insights
Gráfico de Rosca: Criado para mostrar a margem de lucro.

Gráfico de Cascata: Criado para mostrar o lucro mensal.

Cartão de Lucro: Destaca o lucro final, essencial para entender a saúde financeira da empresa.

### 🔗 Resultados das Análises
Finalizamos a construção de um dashboard financeiro bancário, que permite um acompanhamento detalhado das movimentações tanto mensais quanto anuais dos principais bancos: Nu Bank, Safra, Santander, Bradesco e Itaú. Com esse dashboard, é possível verificar:

Receita: Total de dinheiro gerado pelas operações de cada banco.

Despesas: Custos incorridos pelas instituições financeiras.

Imposto: Carga tributária sobre a receita.

Lucro: Resultado final após deduzir todas as despesas, incluindo impostos, da receita.

O dashboard fornece uma visão abrangente e clara da saúde financeira e eficiência operacional dos bancos, facilitando a análise e tomada de decisões estratégicas.

### 🔗 Teste as funções online:https://app.powerbi.com/view?r=eyJrIjoiOGUzMmU2MjgtZDJhZC00NWQ3LWE0ZWUtMTdmMjY4NTBhN2Q1IiwidCI6ImQ1NTZmMWRlLTA1ZDMtNDNiZC1iMGMyLTIzODY4ZWEyNGFlNSJ9


