# Classificação de Imagens do MNIST - Detectando o Número 5

Este projeto utiliza técnicas de aprendizado de máquina para construir um modelo de classificação binária que identifica se uma imagem do conjunto de dados MNIST contém o número "5" ou não. Foi inspirado no livro **Mãos à Obra: Aprendizado de Máquina com Scikit-Learn, Keras & TensorFlow**.

## Objetivo

Criar um modelo de classificação binária para identificar imagens do dígito "5", avaliando seu desempenho com diferentes métricas de classificação.

---

## Dataset

O **MNIST** é um conjunto de dados de dígitos manuscritos que contém 70.000 imagens, cada uma com 28x28 pixels (784 características). As imagens foram divididas em:
- **60.000 para treinamento**
- **10.000 para teste**

Os rótulos foram processados para criar duas classes:
- **"True" para imagens do número 5.**
- **"False" para todos os outros números.**

---

## Implementação

1. **Divisão do Conjunto de Dados**:
   - O conjunto foi dividido em **treino** e **teste**.
   - Criou-se os rótulos binários: `y_train_5` e `y_test_5`.

2. **Treinamento do Modelo**:
   - O modelo escolhido foi o **SGDClassifier** da biblioteca Scikit-Learn.

3. **Validação Cruzada**:
   - Foi utilizada validação cruzada com 3 folds para garantir que o modelo não fosse superajustado aos dados de treino.

4. **Métricas de Avaliação**:
   - **Precisão**: 84%
   - **Revocação**: 65%
   - **F1-Score**: 73%
   - **ROC AUC**: 96%

---

## Principais Resultados

- **Matriz de Confusão**:
    - **2578 erros totais**:
      - 687 **falsos positivos**: imagens classificadas como "5", mas que não eram.
      - 1891 **falsos negativos**: imagens que eram "5", mas não foram detectadas.

- **Curva Precisão/Revocação**:
    - Mostrou o trade-off entre precisão e revocação. Ao exigir **90% de precisão**, a revocação caiu para **45%**.

- **Curva ROC e AUC**:
    - A curva ROC mostrou que o modelo tem uma excelente capacidade de separação entre as classes "5" e "não 5", com um AUC de **96%**.

---

## Tecnologias Utilizadas

- **Python 3.10**
- **Scikit-Learn**
- **NumPy**
- **Matplotlib**

---

## Lições Aprendidas

- **Métricas de Avaliação**: Foi fundamental ir além da acurácia para entender melhor o desempenho do modelo em um problema desbalanceado.
- **Curva ROC e Precisão/Revocação**: São ferramentas essenciais para entender os trade-offs no ajuste de limiares.
- **Impacto do Desbalanceamento**: Apenas 10% das imagens são do número "5", o que exigiu estratégias cuidadosas para avaliar o desempenho.

---

