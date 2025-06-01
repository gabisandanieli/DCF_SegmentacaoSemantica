
# Segmentação Semântica de Displasia Cortical Focal em IRM

Este repositório contém o desenvolvimento completo do Trabalho de Conclusão de Curso:

**"Segmentação Semântica de Displasia Cortical Focal em IRM: Uma Comparação entre Vision Transformers e Arquiteturas CNN"**

Autoria: Gabriela Sandanieli de Aguiar  
Orientação: Prof. Dr. André Carlos Ponce de Leon Ferreira de Carvalho  
Instituto de Ciências Matemáticas e de Computação - ICMC/USP

---

## Objetivo

Aplicação e comparação de arquiteturas de aprendizado profundo (U-Net e SegFormer) para segmentação automática de lesões de Displasia Cortical Focal tipo II (DCF II) em exames de ressonância magnética.

---

## Estrutura do Projeto

| Arquivo | Descrição |
| ------- | --------- |
| **11913509_TCC_Dataset.ipynb** | Pré-processamento: conversão NIfTI → PNG, seleção de slices, redimensionamento, balanceamento de classes. |
| **11913509_TCC_SegFormer.ipynb** | Implementação e avaliação do modelo SegFormer (Vision Transformers). |
| **11913509_TCC_Unet.ipynb** | Implementação e avaliação do modelo U-Net (CNN). |

---

## Conjunto de Dados

- **Fonte:** University Hospital Bonn - OpenNeuro
- **Composição:**
  - 85 pacientes com DCF tipo II
  - 85 indivíduos saudáveis
  - Sequência FLAIR axial
- Máscaras de lesão rotuladas por especialistas.

---

## Tecnologias e Bibliotecas

- Google Colab (execução com GPU A100)
- Python 3
- TensorFlow / PyTorch
- Hugging Face Transformers (SegFormer)
- Numpy, Pandas, Scikit-Learn, Matplotlib

---

## Fluxo de Execução

1. Pré-processamento dos dados (`11913509_TCC_Dataset.ipynb`)
2. Treinamento e avaliação do modelo U-Net (`11913509_TCC_Unet.ipynb`)
3. Treinamento e avaliação do modelo SegFormer (`11913509_TCC_SegFormer.ipynb`)
4. Análise comparativa dos resultados

---

## Resultados Finais (Teste Final)

| Modelo   | Dice Score | IoU | Recall | Precision |
| -------- | ---------- | ---- | ------ | --------- |
| **U-Net**    | 82.67%     | 70.45% | 80.47% | 84.99% |
| **SegFormer** | 81.24%    | 68.41% | 77.45% | 85.43% |

**Observação Comparativa:**

- O SegFormer apresentou maior precisão e menor número de falsos positivos, sendo mais conservador nas detecções.
- A U-Net obteve maior sensibilidade (recall), detectando mais lesões, porém com maior risco de falsos positivos.
- A escolha entre modelos depende do cenário de aplicação e dos recursos computacionais disponíveis.

---

## Execução

Antes de executar os notebooks `TCC_SegFormer` e `TCC_Unet`, execute primeiro o notebook `TCC_Dataset` para garantir o pré-processamento correto das imagens.

---

## Observação Importante

Para execução dos notebooks, é necessário realizar o download prévio do conjunto de dados utilizado no projeto.  
O dataset está disponível publicamente na plataforma **OpenNeuro** no seguinte link:

- [OpenNeuro - University Hospital Bonn Dataset](https://openneuro.org/datasets/ds004199/versions/1.0.5).

Após o download, as imagens devem ser organizadas conforme o esperado no notebook de pré-processamento (`11913509_TCC_Dataset.ipynb`).

---
