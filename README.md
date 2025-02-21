import statsmodels.formula.api as smf        
import pandas as pd                          
                                             

vendas_regiao = {'Vendas_Trimestrais' : [58, 105, 88, 118, 117, 137, 157, 169, 149, 202],
                 'População_Estudantil' : [2, 6, 8, 8, 12, 16, 20, 20, 22, 26]}


vendas = pd.DataFrame(data = vendas_regiao)       
vendas

reg = smf.ols(formula = 'Vendas_Trimestrais ~ População_Estudantil',data = vendas)


reg = reg.fit()                               
reg.summary()                                
