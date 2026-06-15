# 🎓 Análise de Risco de Evasão Acadêmica
**Trabalho Final Prático - Inteligência Artificial: Lógica Fuzzy e Machine Learning**

Este repositório contém a solução computacional desenvolvida para prever e analisar o risco de evasão de estudantes universitários, articulando algoritmos de **Machine Learning** com sistemas de inferência baseados em **Lógica Fuzzy**.

## 📌 Estrutura do Repositório e Entregas

De acordo com as diretrizes do trabalho, foi escolhida a **Abordagem A (Comparação)** como entrega principal e oficial. No entanto, para fins de aprofundamento e estudo de arquiteturas híbridas, a **Abordagem B (Integração)** também foi desenvolvida e documentada como um experimento extra.

### 1. Entrega Oficial (O que deve ser avaliado)
* 📄 **`Trabalho_IA_Entrega_Oficial.ipynb`**: O Notebook principal do projeto. Contém a geração da base de dados simulada, Análise Exploratória (EDA), treinamento da Árvore de Decisão e o Sistema Fuzzy independente (Abordagem A). O código compara criticamente quando as decisões do ML e do Fuzzy concordam ou divergem.
* 📁 **`images/`**: Contém as evidências visuais (gráficos, matriz de confusão e superfícies de controle 3D) geradas pela entrega oficial.

### 2. Experimentos e Extras (Estudo de Integração)
* 📁 **`Experimentos/Trabalho_IA_Estudo_Abordagem_B.ipynb`**: Notebook contendo o "Estado da Arte" do projeto. Aqui, a saída probabilística do Machine Learning é injetada como uma variável linguística dentro do motor Fuzzy, criando uma decisão de risco muito mais holística e interpretável.
* 📁 **`Experimentos/image_comparacao/`**: Imagens e evidências geradas durante os testes da arquitetura integrada.

### 3. Simulador Web Interativo
* 🌐 **`simulador_evasao_comparacao.html`**: Uma interface web desenvolvida em HTML/JS que traduz toda a matemática dos notebooks. Permite simular as notas e frequências de um aluno fictício e ver as barras de risco reagirem em tempo real, evidenciando as diferenças entre o ML puro, a Abordagem A e a Abordagem B.

---

## 🚀 Como Executar o Projeto

O código foi otimizado para rodar de forma fluida no **Google Colab**.

**No Google Colab:**
1. Faça o download do arquivo `Trabalho_IA_Entrega_Oficial.ipynb`.
2. Acesse o [Google Colab](https://colab.research.google.com/) e faça o upload do arquivo (`Arquivo > Fazer upload de notebook`).
3. Vá em `Ambiente de execução > Executar tudo`. 

---

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python 3.12
* **Machine Learning:** `scikit-learn` (DecisionTreeClassifier, métricas de avaliação)
* **Lógica Fuzzy:** `scikit-fuzzy`, `networkx`
* **Análise de Dados e Visualização:** `pandas`, `numpy`, `matplotlib`, `seaborn`

---
