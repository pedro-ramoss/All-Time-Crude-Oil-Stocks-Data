
# 🛢️ Análise de Dados: All Time Crude Oil Stocks

Este projeto foca na exploração e visualização de dados históricos sobre estoques e valores de petróleo bruto, com registros que acompanham o mercado desde **agosto de 2000** até os dias atuais.

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
O arquivo CSV contém dados diários que permitem observar flutuações de mercado, crises energéticas e tendências de consumo ao longo de mais de duas décadas.

* **Início dos dados:** Agosto de 2000
* **Frequência:** Diária
* **Colunas Principais:** Date, Open, High, Low, Close, Volume, Daily_Return_% e Intraday_Volatility.

---

## 🧠 Relato do Projeto
Como esta foi a minha **primeira experiência real** de análise de dados, senti uma certa dificuldade inicial, principalmente sobre como dar o primeiro passo. 

Por conta disso, decidi focar primeiro na base de qualquer projeto de Ciência de Dados: a importação correta e a visualização das colunas para entender a estrutura do que eu estava analisando.

### 🔍 Primeira Etapa: Visualização dos Dados
Utilizei a biblioteca **Pandas** para carregar o arquivo e o método `.head()` para conferir se os dados estavam lógicos e bem formatados.

```python
import pandas as pd

# Importando os dados do petróleo
dataset = pd.read_csv("Crude_Oil.csv", sep=",")

# Visualizando o topo do arquivo
dataset.head()
