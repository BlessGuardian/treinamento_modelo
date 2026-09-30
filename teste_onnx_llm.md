# Relatório de Avaliação de Modelos: Quantizado vs. Base

Este documento apresenta a avaliação comparativa de modelos para detecção de fraudes, dividida em duas baterias de testes: **Modelo Quantizado** e **Modelo Base**. Em cada cenário, foram avaliadas três abordagens: **LLM Puro (OpenAI)**, **Modelo ONNX Puro** e **API Conjunta (LLM + ONNX via HTTP)**.

---

## 1. Convenção e Legenda (Matriz de Confusão)

* **VN (Verdadeiro Negativo):** Realidade Legítima (0) classificada corretamente como Legítima (0).
* **FP (Falso Positivo):** Realidade Legítima (0) classificada incorretamente como Fraude (1).
* **FN (Falso Negativo):** Realidade Fraude (1) classificada incorretamente como Legítima (0).
* **VP (Verdadeiro Positivo):** Realidade Fraude (1) classificada corretamente como Fraude (1).

---

## 2. Bateria de Testes 1: Modelo Quantizado

### 2.1. LLM Puro (OpenAI)

#### Matriz de Confusão
| Realidade \\ Previsão | Previsto Legítima (0) | Previsto Fraude (1) |
| :--- | :---: | :---: |
| **Realidade Legítima (0)** | **49** *(VN)* | **1** *(FP)* |
| **Realidade Fraude (1)** | **3** *(FN)* | **47** *(VP)* |

#### Relatório de Classificação
| Classe / Métrica | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| **Legítima (0)** | 0.94 | 0.98 | 0.96 | 50 |
| **Fraude (1)** | 0.98 | 0.94 | 0.96 | 50 |
| **Accuracy** | | | **0.96** | **100** |
| **Macro Avg** | **0.96** | **0.96** | **0.96** | **100** |
| **Weighted Avg** | **0.96** | **0.96** | **0.96** | **100** |

---

### 2.2. Modelo ONNX Quantizado

#### Matriz de Confusão
| Realidade \\ Previsão | Previsto Legítima (0) | Previsto Fraude (1) |
| :--- | :---: | :---: |
| **Realidade Legítima (0)** | **49** *(VN)* | **1** *(FP)* |
| **Realidade Fraude (1)** | **21** *(FN)* | **29** *(VP)* |

#### Relatório de Classificação
| Classe / Métrica | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| **Legítima (0)** | 0.70 | 0.98 | 0.82 | 50 |
| **Fraude (1)** | 0.97 | 0.58 | 0.72 | 50 |
| **Accuracy** | | | **0.78** | **100** |
| **Macro Avg** | **0.83** | **0.78** | **0.77** | **100** |
| **Weighted Avg** | **0.83** | **0.78** | **0.77** | **100** |

---

### 2.3. API Conjunta (LLM + ONNX Quantizado via HTTP)

#### Matriz de Confusão
| Realidade \\ Previsão | Previsto Legítima (0) | Previsto Fraude (1) |
| :--- | :---: | :---: |
| **Realidade Legítima (0)** | **48** *(VN)* | **2** *(FP)* |
| **Realidade Fraude (1)** | **1** *(FN)* | **49** *(VP)* |

#### Relatório de Classificação
| Classe / Métrica | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| **Legítima (0)** | 0.98 | 0.96 | 0.97 | 50 |
| **Fraude (1)** | 0.96 | 0.98 | 0.97 | 50 |
| **Accuracy** | | | **0.97** | **100** |
| **Macro Avg** | **0.97** | **0.97** | **0.97** | **100** |
| **Weighted Avg** | **0.97** | **0.97** | **0.97** | **100** |

---

## 3. Bateria de Testes 2: Modelo Base

### 3.1. LLM Puro (OpenAI)

#### Matriz de Confusão
| Realidade \\ Previsão | Previsto Legítima (0) | Previsto Fraude (1) |
| :--- | :---: | :---: |
| **Realidade Legítima (0)** | **48** *(VN)* | **2** *(FP)* |
| **Realidade Fraude (1)** | **3** *(FN)* | **47** *(VP)* |

#### Relatório de Classificação
| Classe / Métrica | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| **Legítima (0)** | 0.94 | 0.96 | 0.95 | 50 |
| **Fraude (1)** | 0.96 | 0.94 | 0.95 | 50 |
| **Accuracy** | | | **0.95** | **100** |
| **Macro Avg** | **0.95** | **0.95** | **0.95** | **100** |
| **Weighted Avg** | **0.95** | **0.95** | **0.95** | **100** |

---

### 3.2. Modelo ONNX Base

#### Matriz de Confusão
| Realidade \\ Previsão | Previsto Legítima (0) | Previsto Fraude (1) |
| :--- | :---: | :---: |
| **Realidade Legítima (0)** | **49** *(VN)* | **1** *(FP)* |
| **Realidade Fraude (1)** | **14** *(FN)* | **36** *(VP)* |

#### Relatório de Classificação
| Classe / Métrica | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| **Legítima (0)** | 0.78 | 0.98 | 0.87 | 50 |
| **Fraude (1)** | 0.97 | 0.72 | 0.83 | 50 |
| **Accuracy** | | | **0.85** | **100** |
| **Macro Avg** | **0.88** | **0.85** | **0.85** | **100** |
| **Weighted Avg** | **0.88** | **0.85** | **0.85** | **100** |

---

### 3.3. API Conjunta (LLM + ONNX Base via HTTP)

#### Matriz de Confusão
| Realidade \\ Previsão | Previsto Legítima (0) | Previsto Fraude (1) |
| :--- | :---: | :---: |
| **Realidade Legítima (0)** | **47** *(VN)* | **3** *(FP)* |
| **Realidade Fraude (1)** | **1** *(FN)* | **49** *(VP)* |

#### Relatório de Classificação
| Classe / Métrica | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| **Legítima (0)** | 0.98 | 0.94 | 0.96 | 50 |
| **Fraude (1)** | 0.94 | 0.98 | 0.96 | 50 |
| **Accuracy** | | | **0.96** | **100** |
| **Macro Avg** | **0.96** | **0.96** | **0.96** | **100** |
| **Weighted Avg** | **0.96** | **0.96** | **0.96** | **100** |

---

## 4. Resumo Comparativo Geral

| Configuração | Acurácia | Recall (Fraude) | F1-Score (Fraude) | Falsos Negativos (FN) | Falsos Positivos (FP) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **ONNX Quantizado** | 0.78 | 0.58 | 0.72 | 21 | 1 |
| **ONNX Base** | **0.85** | **0.72** | **0.83** | **14** | **1** |
| *Diferença (ONNX)* | *+0.07* | *+0.14* | *+0.11* | *-7 FN* | *0* |
| | | | | | |
| **LLM Puro (com Quantizado)** | 0.96 | 0.94 | 0.96 | 3 | 1 |
| **LLM Puro (com Base)** | 0.95 | 0.94 | 0.95 | 3 | 2 |
| | | | | | |
| **API Conjunta (Quantizado)** | **0.97** | **0.98** | **0.97** | **1** | **2** |
| **API Conjunta (Base)** | 0.96 | 0.98 | 0.96 | 1 | 3 |

---

## 5. Análise Comparativa dos Resultados

### 1. Impacto Severo da Quantização no Modelo ONNX Standalone
- **Acurácia e Recall:** O modelo ONNX sofreu uma perda significativa de desempenho ao ser quantizado. A acurácia caiu de **85% (Base)** para **78% (Quantizado)**.
- **Detecção de Fraude (Falsos Negativos):** O maior problema da quantização foi a degradação no **Recall de Fraude**, que despencou de **72%** no modelo Base para **58%** no modelo Quantizado. Em termos práticos, o modelo quantizado deixou passar **21 fraudes não detectadas (FN)**, contra **14 FNs** do modelo base (uma piora de 50% nas fraudes perdidas).
- **Conclusão ONNX:** A compressão por quantização retirou do ONNX a capacidade de capturar padrões numéricos/estatísticos mais sutis de fraude.

### 2. Estabilidade do LLM Puro
- O LLM Puro manteve performance estatisticamente idêntica nas duas rodadas de teste (**96% vs 95% de acurácia** e **3 Falsos Negativos** em ambos), o que era esperado, visto que a chamada à API externa da OpenAI permaneceu a mesma. A leve alteração de 1 FP deve-se à estocasticidade normal de geração do modelo.

### 3. Comportamento e Resiliência da API Conjunta (LLM + ONNX)
- **Compensação do LLM:** Na API Conjunta, o componente LLM conseguiu **neutralizar completamente a perda de precisão do ONNX quantizado**. O resultado foi excelente em ambos os cenários (97% de acurácia no Quantizado e 96% no Base).
- **Minimização do Risco Crítico:** Ambas as versões da API Conjunta alcançaram o melhor resultado técnico na métrica mais crítica para prevenção de fraude: **apenas 1 Falso Negativo (Recall de 98%)**.

### 4. Recomendações e Conclusão de Engenharia
- **Uso Standalone (Sem LLM):** Caso o sistema dependa exclusivamente do modelo ONNX para inferência rápida e local, **recomenda-se utilizar o Modelo Base**, pois 21 Falsos Negativos no modelo quantizado representam um risco operacional alto.
- **Uso em Arquitetura Conjunta (LLM + ONNX):** Se a arquitetura final for a API Conjunta, o **ONNX Quantizado é a escolha ideal**. Ele oferece redução substancial no consumo de memória e latência computacional, mantendo métricas do sistema combinando 97% de acurácia e 98% de recall para fraudes.