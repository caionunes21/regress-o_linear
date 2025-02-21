# REGRESSÃO PARA UM DATAFRAME

# Importação das bibliotecas necessárias.

import statsmodels.formula.api as smf        # STATSMODELS.FORMULA.API as SMF - Criar e ajustar os modelos.
import pandas as pd                          # PANDAS as PD - Manipulação de Dados.
                                             # OLS - Especifica o modelo utlizado (Método dos Mínimos Quadrados).

# Criação do Dicionário.

vendas_regiao = {'Vendas_Trimestrais' : [58, 105, 88, 118, 117, 137, 157, 169, 149, 202],
                 'População_Estudantil' : [2, 6, 8, 8, 12, 16, 20, 20, 22, 26]}


# Criação do DataFrame.
vendas = pd.DataFrame(data = vendas_regiao)         # PD.DATAFRAME( DATA ) - Cria o DataFrame.
vendas

# Realizando a Regressão Linear Simples
reg = smf.ols(formula = 'Vendas_Trimestrais ~ População_Estudantil',data = vendas)

# (Variável Dependente = Vendas Trimestrais)
# (Variável Independente = População Estudantil)


reg = reg.fit()                               # Realizamos a regressão e atribuímos o resultado à variável "REG".
reg.summary()                                 # Gera um relatório do resultado da regressão.
