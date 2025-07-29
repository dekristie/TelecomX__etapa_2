# TelecomX__etapa_2

# 🤖 Projeto TelecomX_BR – Modelagem Preditiva de Evasão de Clientes

Este repositório apresenta a segunda etapa do projeto **TelecomX_BR**, desenvolvido no contexto do desafio da plataforma Alura. O foco aqui é a **construção e avaliação de modelos preditivos de churn**, com o objetivo de apoiar a tomada de decisões estratégicas no setor de telecomunicações.

---

## 📌 Descrição Geral

A modelagem preditiva é uma das ferramentas mais valiosas para mitigar a evasão de clientes (churn). A partir de uma base de dados previamente tratada e explorada na etapa anterior, este notebook avança para a aplicação prática de algoritmos supervisionados, avaliando sua performance e interpretabilidade.

---

## 🎯 Objetivos

### Objetivo Geral
Construir modelos preditivos capazes de antecipar a evasão de clientes da operadora fictícia **TelecomX**, contribuindo com ações proativas de retenção e redução do churn.

### Objetivos Específicos

- Aplicar técnicas de engenharia de atributos para potencializar a capacidade preditiva dos modelos.
- Utilizar algoritmos supervisionados (classificação binária) com validação cruzada.
- Avaliar a performance dos modelos com métricas apropriadas: acurácia, recall, precisão, F1-score e AUC-ROC.
- Interpretar os resultados para fins estratégicos.
- Gerar recomendações práticas a partir da modelagem.

---

## 🧪 Pipeline Executado

### 1. **Carregamento e Preparação dos Dados**
- Dataset: `telecomx_data_gold.csv` (pré-tratado)
- Ajustes finais e redefinição de variáveis categóricas.
- Criação de dummies para variáveis nominais.

### 2. **Separação em Variáveis Previsoras e Alvo**
- Variável alvo: `Churn`
- Exclusão de colunas redundantes (como `customerID`) e transformação do target.

### 3. **Divisão Treino-Teste**
- Técnica de hold-out: 70% para treino e 30% para teste.
- Balanceamento realizado com **SMOTE** (Synthetic Minority Over-sampling Technique), garantindo maior robustez do modelo.

### 4. **Modelagem com Algoritmos Supervisionados**
- Modelos utilizados:
  - Regressão Logística
  - Random Forest
  - XGBoost
  - LightGBM
- Métricas de avaliação comparadas por meio de uma função personalizada.
- Apresentação dos principais resultados em DataFrame sintético com destaque para recall e ROC-AUC.

### 5. **Curva ROC**
- Curvas ROC geradas para cada modelo.
- Análise comparativa da capacidade discriminativa (área sob a curva - AUC).

### 6. **Análise Direcionada de Variáveis**
- Visualização da importância das features em modelos baseados em árvores.
- Interpretação dos fatores mais influentes na previsão de churn.

---

## 📊 Principais Resultados

| Modelo            | Acurácia | Recall | Precisão | F1-Score | ROC AUC |
|------------------|----------|--------|----------|----------|---------|
| Random Forest     | 83.2%    | **79.5%** | 71.8%    | 75.4%    | 0.89    |
| LightGBM          | 84.1%    | 77.2% | **75.9%** | **76.5%** | **0.91** |
| Regressão Logística | 80.2%    | 74.3% | 68.0%    | 71.0%    | 0.85    |
| XGBoost           | 83.6%    | 78.1% | 73.0%    | 75.4%    | 0.90    |

> Observação: os resultados podem variar de acordo com o random state utilizado na divisão dos dados e no balanceamento.

---

## ✅ Conclusão

Os modelos preditivos desenvolvidos foram eficazes na detecção de clientes com alta propensão ao churn. O **LightGBM** se destacou, combinando alta AUC com bom equilíbrio entre precisão e recall.

As variáveis mais relevantes para previsão de churn foram:

- **Contract (tipo de contrato)**
- **Tenure (tempo de permanência)**
- **MonthlyCharges (valor mensal pago)**
- **TechSupport (uso de suporte técnico)**
- **InternetService (tipo de serviço de internet)**

---

## 📌 Recomendações Estratégicas

A partir da modelagem e dos fatores explicativos identificados, recomenda-se:

1. **Segmentar campanhas de retenção** com base nas variáveis mais influentes do modelo.
2. **Monitorar clientes com contratos mensais e curto tempo de permanência**.
3. **Oferecer pacotes com suporte técnico incluso**, agregando valor percebido.
4. **Aplicar o modelo em tempo real**, com alertas automáticos para o time de CRM sobre perfis em risco.
5. **Reavaliar práticas de cobrança**, já que valores elevados estão associados ao churn.

---

## 🔧 Tecnologias Utilizadas

- Python 3.10+
- Pandas, NumPy
- Scikit-learn
- XGBoost, LightGBM
- Imbalanced-learn (SMOTE)
- Seaborn, Matplotlib

---

## 📁 Estrutura do Repositório

```
├── TelecomX__etapa_2_TERMINADO.ipynb   # Notebook com análise preditiva
├── telecomx_data_gold.csv              # Base de dados tratada
├── requirements.txt                    # Lista de dependências
└── README.md                           # Documentação do projeto
```

---

## 🔄 Como Reproduzir

```bash
git clone https://github.com/seuusuario/Challenge_TelecomX_BR.git
cd Challenge_TelecomX_BR
python -m venv venv
source venv/bin/activate      # Linux/macOS
venv\Scripts\activate         # Windows
pip install -r requirements.txt
jupyter notebook
```

---

## 👩‍💻 Autoria

Projeto desenvolvido por **Denise Cristine Brandão Leite**, como parte de sua formação em Data Science, com foco em soluções orientadas por dados para problemas reais de negócio.

---

## 📄 Licença

Este projeto está licenciado sob os termos da **Licença MIT**.
