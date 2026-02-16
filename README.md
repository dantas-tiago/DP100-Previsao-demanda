# DP100-Previsao-demanda
Você é dono da sorveteria Gelato Mágico, em uma cidade litorânea, e percebe que as vendas variam conforme a temperatura. Sem planejamento, pode haver desperdício ou falta de produto. Para evitar prejuízos, você decide usar Machine Learning para prever a demanda com base na temperatura e ajustar a produção de forma eficiente.

Projeto 1 - Evidencias tb no docx na pasta "PastaEvidencias"

1 – criar dataset (ou se tiver já o dataset, garantir que tenha acesso)
 <img width="886" height="627" alt="image" src="https://github.com/user-attachments/assets/f789e593-3de9-4a6f-b843-53481de8b854" />

2 – Criar os recursos no azureML
 <img width="886" height="445" alt="image" src="https://github.com/user-attachments/assets/251a842b-6944-4521-90f9-e461f8f5ea81" />

3 – Criar computação para testar os notebooks e um para rodar o pipeline
 <img width="886" height="373" alt="image" src="https://github.com/user-attachments/assets/6e3837be-e940-489c-b997-3597701e1611" />

4 – adicionar o dataset (tabular)

 <img width="886" height="367" alt="image" src="https://github.com/user-attachments/assets/346e2c0e-5b37-484a-831b-f205ba7f17fa" />


<img width="886" height="284" alt="image" src="https://github.com/user-attachments/assets/6b50f52d-76dd-49f0-b5be-59747e5f81b2" />

 selecionar colunas exluindo data
 <img width="886" height="450" alt="image" src="https://github.com/user-attachments/assets/fe5554da-d64c-424b-842b-331ab2a1d8b6" />

 
5 – Fazer um automl
Selecionar regressão linear com predicao de vendas
 
 <img width="886" height="622" alt="image" src="https://github.com/user-attachments/assets/d3e9b8a8-7cf7-4e0e-b05c-aba706313607" />
<img width="886" height="381" alt="image" src="https://github.com/user-attachments/assets/09149bda-fa02-4a02-aa44-6a6b2246421a" />

 <img width="886" height="450" alt="image" src="https://github.com/user-attachments/assets/dec5b04b-e2c7-41e2-a2f7-cd3e26e0de3e" />

Melhor modelo , considerando a métrica de qualidade Erro quadrático  de media de raiz normalizada, foi o XGBoostRegressor
 <img width="886" height="446" alt="image" src="https://github.com/user-attachments/assets/a2b9bc91-680e-4d4b-8047-6555c6fcf0bd" />

Executar
6 – Criar um designer
 <img width="886" height="300" alt="image" src="https://github.com/user-attachments/assets/71e99aba-bdbb-4f95-9478-41a407ee9efd" />

<img width="886" height="767" alt="image" src="https://github.com/user-attachments/assets/5b4b3826-5e41-41ff-99c4-49f9481c4939" />

 
Resultados modelo via designer:
 <img width="886" height="413" alt="image" src="https://github.com/user-attachments/assets/6d1e5090-69c9-46f8-85f2-a2b80136698c" />

Métricas do modelo usando linear regression:
 <img width="886" height="433" alt="image" src="https://github.com/user-attachments/assets/7221dd4e-8a01-4819-9fab-e973fb6d9641" />


7 - Fazer deploy do end point
 <img width="886" height="393" alt="image" src="https://github.com/user-attachments/assets/1eb19005-3408-428b-b1c5-7cedfa3c090b" />

Testando o enfdpoint:
{
  "input_data": {
    "columns": ["temperatura_cidade"],
    "index": [0, 1, 2],
    "data": [[28.5], [31.0], [25.2]]
  }
}

Resultado:
 <img width="886" height="562" alt="image" src="https://github.com/user-attachments/assets/866a0c83-5f2a-49a9-89e7-917aff563561" />


Teste 2:
{
  "input_data": {
    "columns": ["temperatura_cidade"],
    "index": [0],
    "data": [[28.5]]
  }
}

 <img width="886" height="527" alt="image" src="https://github.com/user-attachments/assets/3a5d75a0-24bf-4361-b133-ed967730666a" />


