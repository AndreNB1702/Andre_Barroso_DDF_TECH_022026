# Desafio Dadosfera - André do Nascimento Barroso

---

## Item 0 - Sobre Agilidade e Planejamento
Foi utilizado um Kanban no Trello para mover os card indicando o que há para fazer (To Do), o que está sendo feito (In Progress) e o que foi feito (Done).
https://trello.com/invite/b/69856710f1368ee27099b4e7/ATTI14302d388b2c79f95dd9f316107eb981C6F484B4/dadosfera
<img width="1067" height="511" alt="image" src="https://github.com/user-attachments/assets/9517de51-f6d2-4e05-8b62-6e876b6460ac" />

---

## Item 1 - Sobre a Base de Dados
Utilizei a base de dados "Comprehensive Diabetes Clinical Dataset" disponível no Kaggle (https://www.kaggle.com/datasets/priyamchoksi/100000-diabetes-clinical-dataset/code).
Deixei apenas uma coluna para "race" e acrescentei 3000 registros novos (https://colab.research.google.com/drive/1U25JJMjBfaB76FTDCvex4ZMuD8piwEJ4?usp=sharing).
Ela representa o dado na Landing Zone.

### Dicionário de dados
| Coluna | Descrição |
| :--- | :--- |
| **year** | Ano de referência do registro clínico |
| **gender** | Gênero do paciente |
| **age** | Idade do paciente (em anos) |
| **location** | Localização geográfica do paciente |
| **race** | Raça/Etnia do paciente (coluna categórica unificada) |
| **hypertension** | Indicador de hipertensão (0 = Não, 1 = Sim) |
| **heart_disease** | Indicador de doença cardíaca (0 = Não, 1 = Sim) |
| **smoking_history** | Histórico de tabagismo do paciente |
| **bmi** | Índice de Massa Corporal (Body Mass Index) |
| **hbA1c_level** | Nível de HbA1c, indicador de controle glicêmico |
| **blood_glucose_level** | Nível de glicose no sangue |
| **diabetes** | Indicador de diagnóstico de diabetes (0 = Não, 1 = Sim) |

---

## Item  2.1 - Sobre a Dadosfera - Integrar
Dataset dentro da Dadosfera (https://app.dadosfera.ai/pt-BR/collect/import-files/adacf9f6-e6d3-4fc6-9930-ffffa331aeb5)
<img width="1802" height="871" alt="image" src="https://github.com/user-attachments/assets/41980707-9f6c-484e-b9c7-c52d67f9e461" />

---

## Item - 3 e 8
Tive meu primeiro contato com a parte de arquitetura de DataLake e Pipelines nesse processo seletivo. Fiz um esboço da minha ideia.
As informações saem do sistema do hospital e chegam "cruas" na Landing Zone, passam por um tratamento para a Standardized Zone e refinadas para a Curated Zone
<img width="1527" height="520" alt="image" src="https://github.com/user-attachments/assets/af29c0e2-81df-4d48-8d9b-6551979fef40" />
Link do dataset na sessão catálogo incluindo uma documentação (https://app.dadosfera.ai/pt-BR/catalog/data-assets/5c2a54de-580c-497c-b4b3-d4e7ed0e6aa7).
<img width="1320" height="785" alt="image" src="https://github.com/user-attachments/assets/a5fdeaaf-dea8-450b-b7ea-7bbe63bb0e79" />

---

## Item 4 - Data Quality
O meu Collab não estava rodando o Great Expectations e o Soda Core.
Fiz essa parte com o próprio Pandas e com isso gerei o dataset da Standardized Zone, que foi enviado para a Dadosfera (https://app.dadosfera.ai/pt-BR/collect/import-files/5af28182-07d7-48a0-8508-bf15ffe38c63).
https://colab.research.google.com/drive/1_KCGbnpshaJQLSns679L8WQf9HV6NCof?usp=sharing

---

## Item 6 - Modelagem
O dataset pequeno não necessita modelagem dos dados. Porém, em um cenário real de produção com vários dados, eu usaria ou o Star Schema ou o Snowflake Schema.
<img width="837" height="498" alt="image" src="https://github.com/user-attachments/assets/d9b3d438-cd83-4cee-bff2-acccef1afa13" />

---

## Item 7 - Análise de Dados
Realizei uma análise no Python para entender melhor o dataset (https://colab.research.google.com/drive/1oKODl0EqXNd1Wcnl-Enq_z2N1doAHfxg?usp=sharing).
Dashboard na Dadosfera: https://metabase-treinamentos.dadosfera.ai/dashboard/279-andre-diabete

Query diabete x ano:
<img width="1083" height="617" alt="image" src="https://github.com/user-attachments/assets/a1fd0f4d-3966-496d-befd-ee89f667d1a6" />

Query diabete x faixa etária:
<img width="1343" height="665" alt="image" src="https://github.com/user-attachments/assets/fbb2cde8-e9ef-41b4-a081-0009460f46eb" />

Query diabete x gênero:
<img width="923" height="537" alt="image" src="https://github.com/user-attachments/assets/f5b7934a-14c8-4bd0-bc9b-de9fe9631d85" />

Query diabete x IMC:
<img width="940" height="705" alt="image" src="https://github.com/user-attachments/assets/a68988e0-b59a-4ad5-9307-cabc19a1dff0" />

Query diabete x tabagismo:
<img width="1151" height="587" alt="image" src="https://github.com/user-attachments/assets/f62d8978-39b5-446d-8420-9519859f20f7" />

Query total de pessoas:
<img width="1035" height="678" alt="image" src="https://github.com/user-attachments/assets/24614368-ef29-472f-87eb-fe01b778c587" />

Query total pessoas com diabete:
<img width="947" height="678" alt="image" src="https://github.com/user-attachments/assets/64149f75-643c-4e67-b9ab-7354601e3d59" />

Query total pessoas sem diabete:
<img width="1021" height="693" alt="image" src="https://github.com/user-attachments/assets/60d6610a-e566-4af1-996a-5a6f779986ca" />

---

## Modelo de Machine Learning
Foi feito um undersampling dos dados e aplicado um modelo de Machine Learning (XGBoost) para classificação de pacientes em diabéticos ou não (https://colab.research.google.com/drive/1sZbFg7lhQxKJBq3K1VO6lsocBLYdHVxz?usp=sharing).
Foi possível atingir boas métricas, tanto a acurácia, como a precisão e recall acima de 85%
<img width="148" height="57" alt="image" src="https://github.com/user-attachments/assets/9702288e-4d66-4831-83c9-ae160d78cb5c" />
