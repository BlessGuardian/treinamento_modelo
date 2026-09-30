# Relatório de Avaliação de Modelos: Quantizado vs. Base

Este documento apresenta a avaliação comparativa de modelos para detecção de fraudes, dividida em duas baterias de testes: **Modelo Quantizado** e **Modelo Base**. Em cada cenário, foram avaliadas três abordagens: **LLM Puro (OpenAI)**, **Modelo ONNX Puro** e **API Conjunta (LLM + ONNX via HTTP)**.

---

## 1. Modelo Original (PyTorch Antes da Conversão para ONNX)

### 1.1. Modelo PyTorch 

#### Matriz de Confusão

| Realidade \ Previsão | Previsto Legítima (0) | Previsto Fraude (1) | 
| :--- | :--- | :--- | 
| **Realidade Legítima (0)** | **49** *(VN)* | **1** *(FP)* | 
| **Realidade Fraude (1)** | **9** *(FN)* | **41** *(VP)* | 

#### Relatório de Classificação

| Classe / Métrica | Precision | Recall | F1-Score | Support | 
| :--- | :--- | :--- | :--- | :--- | 
| **Legítima (0)** | 0.84 | 0.98 | 0.91 | 50 | 
| **Fraude (1)** | 0.98 | 0.82 | 0.89 | 50 | 
| **Accuracy** | | | **0.90** | **100** | 
| **Macro Avg** | **0.91** | **0.90** | **0.90** | **100** | 
| **Weighted Avg** | **0.91** | **0.90** | **0.90** | **100** |
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

### 2.3. API Conjunta (LLM + ONNX Quantizado)

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

### 3.3. API Conjunta (LLM + ONNX Base)

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
| **PyTorch Original** | **0.90** | **0.82** | **0.89** | **9** | **1** | 
| **ONNX Quantizado** | 0.78 | 0.58 | 0.72 | 21 | 1 |
| **ONNX Base** | **0.85** | **0.72** | **0.83** | **14** | **1** |
| **LLM Puro (Teste 1)** | 0.96 | 0.94 | 0.96 | 3 | 1 |
| **LLM Puro (Teste 2)** | 0.95 | 0.94 | 0.95 | 3 | 2 |
| | | | | | |
| **API Conjunta (Quantizado)** | **0.97** | **0.98** | **0.97** | **1** | **2** |
| **API Conjunta (Base)** | 0.96 | 0.98 | 0.96 | 1 | 3 |

---

