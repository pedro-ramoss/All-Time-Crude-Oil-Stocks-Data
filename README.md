# 🛢️ Análise de Dados: All Time Crude Oil Stocks

Este projeto foca na exploração e visualização de dados históricos sobre estoques e preços de petróleo bruto, com registros que acompanham o mercado desde **agosto de 2000** até os dias atuais.

---

## 🛠️ Tecnologias e Ferramentas
<div align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white&style=for-the-badge" height="35" alt="python logo"  />
  <img width="12" />
  <img src="https://img.shields.io/badge/Visual Studio Code-007ACC?logo=visualstudiocode&logoColor=white&style=for-the-badge" height="35" alt="vscode logo"  />
  <img width="12" />
  <img src="https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=black&style=for-the-badge" height="35" alt="jupyter logo"  />
  <img width="12" />
  <img src="https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white&style=for-the-badge" height="35" alt="pandas logo"  />
</div>

<br>

## 📊 Sobre o Dataset
O arquivo CSV contém dados diários que permitem observar flutuações de mercado, crises energéticas e tendências ao longo de mais de duas décadas.

* **Início dos dados:** Agosto de 2000  
* **Frequência:** Diária  
* **Colunas principais:** Date, Open, High, Low, Close, Volume, Daily_Return_% e Intraday_Volatility  

---

## 🧠 Relato do Projeto
Por se tratar da minha **primeira experiência prática** em análise de dados, houve uma dificuldade inicial em definir por onde começar.

Diante disso, optei por focar na base de qualquer projeto de Ciência de Dados: a importação correta dos dados e a compreensão da estrutura do dataset.

---

### 🔍 Primeira Etapa: Visualização dos Dados
Utilizei a biblioteca **Pandas** para carregar o arquivo e o método `.head()` para validar se os dados estavam coerentes e bem estruturados.

```python
import pandas as pd

# Importando os dados do petróleo
dataset = pd.read_csv("Crude_Oil.csv", sep=",")

# Visualizando o topo do arquivo
print(dataset.head())
```   
<br>

<img width="544" height="151" alt="1" src="https://github.com/user-attachments/assets/68556cd1-57f6-47a2-a837-9b121ed381d8" />

<br>

Em seguida, visualizei todas as colunas para entender melhor a estrutura do dataset e padronizar os nomes para facilitar a análise:

```
print(dataset.columns)
```

<br>

<img width="460" height="46" alt="2" src="https://github.com/user-attachments/assets/2399997d-3ecb-4e02-9788-acdb2330ee39" />   
    
 <br>  

 Após isso, realizei a renomeação das colunas para nomes mais descritivos:

 <br>
     
```
dataset.columns = ["Data", "Preco_abertura","Preco_maximo","Preco_baixo", "Preco_fechamento", "contratos", "Variacao", "Media"]

dataset.head()
```   

<br>
   
<img width="579" height="149" alt="3" src="https://github.com/user-attachments/assets/e75f95c1-9a64-43c4-8115-4d56dadb2933" />   

