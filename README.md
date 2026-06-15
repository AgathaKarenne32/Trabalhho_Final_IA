# 📘 README – Trabalho Final de IA: Risco de Evasão Acadêmica

**Disciplina:** Inteligência Artificial – Lógica Fuzzy e Machine Learning  
**Professor:** William Malvezzi  
**Tema:** Risco de Evasão Acadêmica com Machine Learning e Lógica Fuzzy

---

## 🚀 Como Executar no Google Colab (Recomendado)

### Passo 1 – Abrir o Colab
Acesse [colab.research.google.com](https://colab.research.google.com) e faça login com sua conta Google.

### Passo 2 – Criar novo notebook
Clique em **"Novo notebook"**.

### Passo 3 – Instalar dependências
Na primeira célula, cole e execute:
```python
!pip install scikit-fuzzy pandas numpy matplotlib seaborn scikit-learn
```
Aguarde a instalação terminar (~1-2 minutos).

### Passo 4 – Carregar o código
Cole o conteúdo do arquivo `evasao_academica_IA.py` a partir da **CÉLULA 2** (pule a célula de instalação, já feita no passo 3).

### Passo 5 – Executar tudo
Vá em **Runtime → Run all** (ou Ctrl+F9).  
O código inteiro leva em torno de **2-4 minutos** para rodar (a superfície 3D fuzzy é a parte mais lenta).

---

## 🗂️ Estrutura do Código (Células)

| Célula | Conteúdo |
|--------|----------|
| 1 | Instalação de dependências |
| 2 | Importações das bibliotecas |
| 3 | Geração da base de dados simulada (200 registros) |
| 4 | Análise Exploratória dos Dados (EDA) |
| 5 | Pré-processamento e divisão treino/teste |
| 6 | Treinamento e avaliação da Árvore de Decisão |
| 7 | Construção do Sistema Fuzzy (variáveis, pertinências, regras) |
| 8 | Testes do sistema fuzzy com casos concretos |
| 9 | Superfície de controle 3D do sistema fuzzy |
| 10 | Integração e comparação ML vs Fuzzy |
| 11 | Função interativa de consulta por aluno |
| 12 | Resumo final e conclusões |

---

## 🧪 Como Testar um Aluno Específico

No final do notebook, use a função `consultar_aluno()`:

```python
consultar_aluno(
    frequencia=45,           # % de presença (0–100)
    media_notas=4.5,         # média das notas (0–10)
    atividades_entregues=50, # % de atividades entregues (0–100)
    acessos_ava=10,          # acessos ao AVA por mês (0–50)
    reprovacoes_ant=2        # número de reprovações anteriores (0–4)
)
```

O sistema retorna automaticamente:
- Classificação da Árvore de Decisão (Baixo / Médio / Alto)
- Score contínuo do sistema Fuzzy (0 a 100)
- Classificação do sistema Fuzzy
- Indicação de concordância ou divergência entre os métodos

---

## 📊 Arquivos Gerados

Após a execução, os seguintes gráficos são salvos automaticamente:

| Arquivo | Descrição |
|---------|-----------|
| `eda_variaveis.png` | Distribuição das variáveis por classe de risco |
| `correlacao.png` | Mapa de correlação entre variáveis |
| `matriz_confusao.png` | Matriz de confusão da Árvore de Decisão |
| `importancia_variaveis.png` | Importância de cada variável no modelo ML |
| `arvore_decisao.png` | Estrutura visual da Árvore de Decisão |
| `funcoes_pertinencia.png` | Funções de pertinência do sistema fuzzy |
| `superficie_fuzzy.png` | Superfície de controle 3D do sistema fuzzy |
| `comparacao_ml_fuzzy.png` | Comparação entre predições ML e Fuzzy |

Para baixar no Colab: painel lateral esquerdo → ícone de pasta → clique com botão direito no arquivo → Download.

---

## 📋 Requisitos Atendidos

| Requisito do Trabalho | Implementado |
|----------------------|:------------:|
| Problema definido claramente | ✅ |
| Justificativa do uso de IA | ✅ |
| Base com ≥ 100 registros | ✅ (200 registros) |
| Análise exploratória (EDA) | ✅ |
| Tratamento de dados | ✅ |
| Separação treino/teste | ✅ (80/20 estratificado) |
| Modelo de Machine Learning | ✅ (Árvore de Decisão) |
| Métricas de avaliação (acurácia, F1, etc.) | ✅ |
| Sistema fuzzy completo | ✅ |
| ≥ 2 variáveis de entrada fuzzy | ✅ (frequência + nota) |
| ≥ 1 variável de saída fuzzy | ✅ (risco de evasão) |
| ≥ 3 termos linguísticos por variável | ✅ (baixa/média/alta) |
| ≥ 6 regras fuzzy | ✅ (9 regras) |
| Fuzzificação, inferência, defuzzificação | ✅ |
| Comparação/integração ML + Fuzzy | ✅ (Abordagem B) |
| Análise crítica e limitações | ✅ |
| Código comentado | ✅ |

---

## 📐 Variáveis do Sistema

### Base de Dados
| Variável | Tipo | Intervalo | Papel |
|----------|------|-----------|-------|
| `frequencia` | Numérica | 0 – 100% | Entrada (ML e Fuzzy) |
| `media_notas` | Numérica | 0 – 10 | Entrada (ML e Fuzzy) |
| `atividades_entregues` | Numérica | 0 – 100% | Entrada (ML) |
| `acessos_ava` | Inteira | 0 – 50 | Entrada (ML) |
| `reprovacoes_ant` | Inteira | 0 – 4 | Entrada (ML) |
| `risco_evasao` | Categórica | Baixo/Médio/Alto | Saída (target) |

### Regras Fuzzy
```
R1: SE frequência é BAIXA  E nota é BAIXA  → risco é ALTO
R2: SE frequência é BAIXA  E nota é MÉDIA  → risco é ALTO
R3: SE frequência é MÉDIA  E nota é BAIXA  → risco é MÉDIO
R4: SE frequência é MÉDIA  E nota é MÉDIA  → risco é MÉDIO
R5: SE frequência é ALTA   E nota é MÉDIA  → risco é BAIXO
R6: SE frequência é ALTA   E nota é ALTA   → risco é BAIXO
R7: SE frequência é BAIXA  E nota é ALTA   → risco é MÉDIO
R8: SE frequência é MÉDIA  E nota é ALTA   → risco é BAIXO
R9: SE frequência é ALTA   E nota é BAIXA  → risco é MÉDIO
```

---

## 🎤 Roteiro para Apresentação (10–15 min)

1. **[2 min]** Apresentação do problema – por que evasão é importante?
2. **[2 min]** Base de dados: variáveis, distribuição, análise exploratória
3. **[3 min]** Árvore de Decisão: como funciona, métricas obtidas, matriz de confusão
4. **[3 min]** Sistema Fuzzy: variáveis linguísticas, funções de pertinência, regras, superfície 3D
5. **[2 min]** Comparação ML vs Fuzzy: concordância, divergências, pontos fortes de cada
6. **[2 min]** Demonstração ao vivo da função `consultar_aluno()` com um aluno inventado
7. **[1 min]** Conclusão: limitações e melhorias futuras

---

## ⚠️ Possíveis Erros e Soluções

| Erro | Solução |
|------|---------|
| `ModuleNotFoundError: skfuzzy` | Execute `!pip install scikit-fuzzy` |
| Superfície 3D demora muito | Aguarde, é normal (~60s no Colab) |
| `KeyError` nas variáveis fuzzy | Certifique-se de usar as entradas corretas: `'frequencia'` e `'nota'` |
| Gráficos não aparecem | Execute `%matplotlib inline` na primeira célula |

---

## 📚 Referências

- RUSSELL, S.; NORVIG, P. *Inteligência Artificial*. 3. ed. Elsevier, 2013.
- ZADEH, L. A. Fuzzy Sets. *Information and Control*, v. 8, n. 3, p. 338–353, 1965.
- Scikit-learn: https://scikit-learn.org/stable/user_guide.html
- Scikit-fuzzy: https://pythonhosted.org/scikit-fuzzy/
- Malvezzi, W. Slides da disciplina de IA. Material interno, 2025.
