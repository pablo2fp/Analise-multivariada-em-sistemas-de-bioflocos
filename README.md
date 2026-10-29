# 🔬 Análise Multivariada & Redes de Correlação em Sistemas de Bioflocos (HBFT vs. QBFT vs. CSW)

Projeto de Ciência de Dados e Estatística Multivariada aplicado à aquicultura intensiva sustentável. O estudo analisa os parâmetros de qualidade de água, microbiologia e desempenho produtivo em tanques experimentais sob diferentes regimes de bioflocos e água salgada clara (HBFT x QBFT x CSW).

---

## 📌 Objetivos do Projeto

- **Triagem de Multicolinearidade:** Mapear pares de variáveis com forte sinergia fisiológica/físico-química.
- **Redução de Dimensionalidade (PCA):** Sintetizar os descritores do ambiente aquático em componentes principais ortogonais para entender a separação dos tratamentos.
- **Agrupamento Hierárquico (HCA) & Heatmap:** Agrupar tanques experimentais e parâmetros por proximidade euclidiana utilizando o método de *Ward*.
- **Análise de Redes Complexas (Network Analysis):** Modelar as interações multivariadas como um grafo de correlação não linear de Spearman ($\vert{}r_s\vert{} \ge 0.85$) para identificar variáveis *hub* (nós centrais do ecossistema de bioflocos).

---

## 🛠️ Tecnologias e Bibliotecas

- **Linguagem:** Python
- **Estruturação e Manipulação:** Pandas, NumPy
- **Estatística Multivariada & Clusterização:** Scikit-Learn (`PCA`, `StandardScaler`), SciPy (`linkage`, `dendrogram`, `spearmanr`)
- **Análise de Redes Complexas:** NetworkX
- **Visualização de Dados:** Seaborn, Matplotlib

---

## 📊 Principais Resultados e Descobertas
### 1. Componentes Principais (PCA):

* Determinação do ponto de corte de variância acumulada via Scree Plot.

* As primeiras componentes principais (PC1 e PC2) segregam com clareza os perfis f*ísico-químicos e biológicos entre os tratamentos HBFT, QBFT e CSW.

* As cargas (loadings) identificam quais parâmetros foram determinantes para a diferenciação dos tanques.

### 2. Clusterização Hierárquica:

* O dendrograma e o mapa de calor confirmam o agrupamento natural de réplicas de mesmo tratamento, evidenciando a homogeneidade intraclasse dos manejos avaliados.

### 3. Grafo de Co-ocorrência e Interação (NetworkX):

* A modelagem por grafos evidenciou nós altamente conectados (centralidade de grau elevada), demonstrando variáveis que atuam como gatilhos em cadeia no equilíbrio dos bioflocos.

---
## 🔬 Metodologia e Etapas da Análise

```text
Dados Experimentais (Tanques x Parâmetros)
     │
     ├──> Análise de Correlação & Filtro de Sinergia (|r| >= 0.80)
     │
     ├──> Padronização (StandardScaler)
     │         │
     │         ├──> PCA (Análise de Autovalores, Scree Plot & Biplot PC1 vs PC2)
     │         │
     │         ├──> Clusterização Hierárquica (Método de Ward & Dendrograma)
     │         │
     │         └──> Clustermap Biclusterizado (Heatmap Tanques x Parâmetros)
     │
     └──> Matriz de Spearman (|r| >= 0.85) -> Grafo de Redes com NetworkX
````

---
## 💻 Como Reproduzir
### 1. Clone o repositório:
```text
git clone [https://github.com/pablo2fp/biofloc-multivariate-analysis.git](https://github.com/pablo2fp/biofloc-multivariate-analysis.git)
cd biofloc-multivariate-analysis
```

### 2. Instale as dependências:
```text
pip install -r requirements.txt
```

### 3. Execute o script de análise:
```text
python dados_mestrado.py
```
