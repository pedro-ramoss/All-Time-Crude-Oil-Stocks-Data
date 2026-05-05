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

## 🔍 Primeira Etapa: Visualização dos Dados
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

---

## 🧹 Verificação de Dados Nulos
Antes de seguir com qualquer análise, achei importante validar se existiam valores nulos no dataset.

```python
dataset.isnull().sum()
```

<img width="129" height="115" alt="4" src="https://github.com/user-attachments/assets/b39ea070-f136-4803-bc6f-d41cdf13a628" />

---

## 📈 Análise de Tendência dos Preços   

Depois de entender a estrutura dos dados, comecei analisando o comportamento dos preços ao longo do tempo.   

Utilizei gráficos de linha para visualizar a evolução das principais variáveis:   

Preço de abertura   
Preço máximo   
Preço mínimo   
Preço de fechamento   

<br> 

```
srn.lineplot(data=dataset, x='Data', y='Preco_abertura')
```

<br>

<img width="482" height="345" alt="5" src="https://github.com/user-attachments/assets/e8238c76-f847-4e66-b8c6-d3c45644ebd6" />

<br>

```
srn.lineplot(data=dataset, x='Data', y='Preco_maximo')
```
<br>

<img width="473" height="326" alt="6" src="https://github.com/user-attachments/assets/be6defef-52fe-43aa-a6d9-4c9006f40f41" />

<br>

```
srn.lineplot(data=dataset, x='Data', y='Preco_baixo')
```
<br>

<img width="493" height="339" alt="7" src="https://github.com/user-attachments/assets/bff41790-bfcf-492f-a14b-b82d4dca933c" />

<br>

```
srn.lineplot(data=dataset, x='Data', y='Preco_fechamento')
```

<br>

<img width="485" height="347" alt="8" src="https://github.com/user-attachments/assets/4cd1ed6c-ef75-4890-bcfb-a4a7beb41328" />

<br>

Ao observar esses gráficos, já é possível perceber que o mercado de petróleo apresenta alta volatilidade ao longo dos anos, com períodos de forte crescimento seguidos por quedas relevantes.   

---

## 🚨 Identificação de Valores Extremos (Outliers)

Durante a análise, quis entender melhor momentos em que o preço do petróleo atingiu valores muito altos.

```
dataset[dataset["Preco_fechamento"] >= 125]
```

<br>

<img width="581" height="394" alt="9" src="https://github.com/user-attachments/assets/56d2a66c-cbdf-4c4e-b049-f886aeb3080a" />

<br>

Os dados mostram que esses picos aconteceram principalmente por volta de 2008, um período conhecido por forte instabilidade econômica global.   

---

## ⚠️ Evento Anômalo (Preço Negativo)

Um ponto que chamou bastante atenção foi a existência de um valor negativo no preço do petróleo:

<br>

```
dataset[dataset["Preco_fechamento"] < 0]
```
<br>

<img width="598" height="69" alt="10" src="https://github.com/user-attachments/assets/5e021eef-64dd-4ad3-b083-251416b50ecc" />

<br>

Esse registro corresponde ao dia 20 de abril de 2020, quando o preço chegou a valores negativos.   

Esse evento está diretamente ligado ao impacto da pandemia de COVID-19, onde houve uma queda brusca na demanda e excesso de oferta, levando o mercado a uma situação atípica.   

---

## 📊 Distribuição dos Dados

Por fim, analisei a distribuição dos preços mínimos para entender melhor o comportamento geral dos dados.   

<br>

```
srn.displot(data=dataset, x="Preco_baixo", kde=True)
```

<br>

<img width="421" height="372" alt="11" src="https://github.com/user-attachments/assets/5c4f88cc-d200-4c36-a31d-7946b7f6df5e" />

---

## 📌 Conclusão

Esse projeto foi fundamental para consolidar conceitos básicos de análise de dados, principalmente na etapa de:   

Importação e leitura de dados   
Entendimento da estrutura do dataset   
Limpeza e padronização   
Visualização de dados   
Identificação de padrões e eventos relevantes   

Além disso, foi possível observar na prática como fatores externos, como crises econômicas e eventos globais, impactam diretamente o comportamento do mercado.   

