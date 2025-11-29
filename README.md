# Previsão de Preços de Casas em Boston com Rede Neural (MLP)

## Descrição do Projeto
Este projeto utiliza o **dataset Boston Housing** para prever o **valor médio das casas (MEDV)** com base em características socioeconômicas e estruturais de bairros de Boston.  

Foi implementado um modelo de **Rede Neural Multilayer Perceptron (MLP)** para regressão, e os resultados foram avaliados por métricas como **MSE, MAE e R²**. O objetivo é compreender como diferentes variáveis influenciam o preço das casas e demonstrar a eficácia de redes neurais em problemas de regressão tabular.

---

## Tecnologias Utilizadas
- Python 3.x
- TensorFlow / Keras
- NumPy, Pandas
- Scikit-learn
- Matplotlib, Seaborn

---

## Estrutura do Projeto
```bash
projeto_ia
├── data
│   └── HousingData.csv
├── README.md
├── RedesNeurais.ipynb
└── requisitos.txt
````

---

## Metodologia

1. **Carregamento e análise dos dados**
   - Leitura do arquivo CSV.
   - Tratamento de valores ausentes.
   - Análise exploratória (estatísticas, histogramas, correlações).

2. **Pré-processamento**
   - Remoção de colunas categóricas irrelevantes (`CHAS`).
   - Normalização dos atributos usando `StandardScaler`.
   - Separação dos dados em treino (80%) e teste (20%).

3. **Construção da Rede Neural (MLP)**
   - **Input Layer:** 13 neurônios
   - **Hidden Layers:** 64 → 32 → 16 neurônios, com ativação ReLU
   - **Output Layer:** 1 neurônio (valor previsto)
   - **Optimizer:** Adam, learning rate = 0.001
   - **Loss:** MSE
   - **Métrica:** MAE
   - **Early Stopping:** Pacience=20, restaura melhores pesos

4. **Treinamento**
   - 400 épocas
   - Batch size = 16
   - Validation split = 20% do treino

5. **Avaliação**
   - MSE, MAE e R²
   - Gráficos de **Real vs Predito** e **Resíduos**

---

## Resultados Obtidos
- **MSE:** ~11.4  
- **MAE:** ~2.29  
- **R²:** 0.84  

**Observações:**
- O modelo explica aproximadamente 84% da variância dos preços.
- Erro médio absoluto de 2.29 mil dólares.
- Gráficos mostram predições alinhadas à diagonal e resíduos distribuídos sem padrão sistemático.

---

## Conclusão
A rede neural MLP apresentou boa capacidade de prever o valor médio das casas.  
Aplicações práticas incluem:
- Modelos de avaliação imobiliária
- Planejamento urbano
- Sistemas de recomendação de preços

**Melhorias futuras:**
- Testar outras arquiteturas (Random Forest, XGBoost)
- Aplicar regularização (Dropout, L1/L2)
- Cross-validation mais robusta para validação

---

## Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/DiogoAug16/projeto-ia.git
cd boston_housing_mlp
````
2. Instale as dependencias:
```bash
pip install -r requisitos.txt
```

3. Abra o notebook `BostonHousing_MLP.ipynb` no Jupyter e execute as células. 