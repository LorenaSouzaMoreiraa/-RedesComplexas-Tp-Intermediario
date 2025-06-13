# Trabalho Prático Intermediário: Análise de Redes Complexas

## Disciplina: INF 791 / INF 493 - Tópicos Especiais II: Redes Complexas
**Instituição:** Universidade Federal de Viçosa (UFV)  
**Professor:** Julio Cesar Soares dos Reis  
**Semestre:** 1º Semestre de 2025

---

### 1. Descrição do Projeto

Este repositório contém o desenvolvimento do Trabalho Prático Intermediário da disciplina de Redes Complexas. O objetivo do trabalho foi aplicar os conceitos teóricos da área em um cenário prático, envolvendo as etapas de coleta de dados, construção de um grafo, análise de suas propriedades e visualização.

O projeto focou na análise de um conjunto de dados de textos para construir e examinar uma rede de coocorrência de palavras, revelando a estrutura e as relações do léxico contido nos dados.

---

### 2. Estrutura do Repositório

O projeto está organizado da seguinte forma:

```
.
├── 📁 dados/
│   ├── mol.csv                                                                # Léxico de palavras de referência
│   └── 2019-05-28_portuguese_hate_speech_binary_classification.csv            # Conjunto de dados brutos com as mensagens
│
├──📁 relatorio/
│   ├── latex/           # Arquivos-fonte em LaTeX
│   └── Relatorio.pdf    # Relatório final do trabalho em formato PDF
│
└── 📓 Analise.ipynb     # Notebook Jupyter/Colab com todo o código e análise
```

* **`/dados/`**: Contém os arquivos `.csv` utilizados como fonte de dados para a análise.
* **`/relatorio/Relatorio.pdf`**: O documento final com a descrição detalhada do trabalho, as análises realizadas e a discussão dos resultados, conforme solicitado nas diretrizes.
* **`Analise_Redes_Complexas.ipynb`**: O notebook auto-contido que centraliza todo o fluxo de trabalho, desde a leitura e pré-processamento dos dados até a construção, análise e visualização do grafo de palavras.

---

### 3. Metodologia

O fluxo de trabalho seguido neste projeto pode ser resumido nas seguintes etapas:

1.  **Leitura e Preparação dos Dados**: Carregamento dos datasets a partir dos arquivos `.csv`.
2.  **Pré-processamento de Texto**: Aplicação de uma pipeline de limpeza nos textos das mensagens, incluindo:
    * Remoção de menções, hashtags, URLs e pontuações.
    * Remoção de *stop words* da língua portuguesa utilizando a biblioteca NLTK.
    * Lematização das palavras para reduzi-las à sua forma base (lema) utilizando a biblioteca spaCy.
3.  **Construção do Grafo**: Criação de um grafo de coocorrência de palavras com a biblioteca `networkx`, onde:
    * **Nós**: Representam as palavras únicas (lemas). O tamanho de cada nó na visualização é proporcional à sua frequência total no corpus.
    * **Arestas**: Conectam duas palavras que aparecem em sequência nos textos. O peso de cada aresta é proporcional à frequência com que o par de palavras aparece junto.
4.  **Análise da Rede**: Cálculo e interpretação de métricas fundamentais de redes complexas, incluindo:
    * Distribuição de Grau e Grau Médio.
    * Número e tamanho dos Componentes Conectados.
    * Coeficiente de Clusterização (Global e Local).
    * Análise de Distâncias e Overlap de Vizinhança.

---

### 4. Como Executar

O notebook `Analise_Redes_Complexas.ipynb` foi desenvolvido para ser executado em um ambiente como o Google Colab ou Jupyter Notebook. Ele é auto-contido e as células devem ser executadas sequencialmente.

#### Dependências

As principais bibliotecas utilizadas estão listadas abaixo. As células de instalação (`!pip install`) estão incluídas no início do notebook.

- `pandas`
- `numpy`
- `networkx`
- `matplotlib`
- `seaborn`
- `nltk`
- `spacy` (com o modelo `pt_core_news_lg`)
- `re` (módulo padrão do Python)
- `collections` (módulo padrão do Python)

---

### Licença
Todo o conteúdo deste repositório é de propriedade exclusiva dos autores e foi desenvolvido com fins acadêmicos.
Não é permitida a reprodução, redistribuição ou modificação sem autorização expressa dos responsáveis pelo projeto.
