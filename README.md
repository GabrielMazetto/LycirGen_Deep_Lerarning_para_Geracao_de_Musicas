# LyricGen: Geração de Letras de Música com LSTMs e Fine-Tuning

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=Kaggle&logoColor=white)

Este repositório contém o código e a documentação do projeto **LyricGen**, focado na geração automática de letras de música com o estilo de um artista específico utilizando Deep Learning.

O projeto foi desenvolvido para a disciplina de Processamento de Linguagem Natural do curso de Ciência de Dados e Inteligência Artificial da PUC-Campinas, sob orientação do Prof. Dr. Wemerson D. Parreira.

## 🎯 O Desafio

A composição musical é um processo criativo que frequentemente esbarra em desafios como bloqueios criativos e limitações técnicas. Ferramentas de IA podem atuar como assistentes de co-criação, oferecendo inspiração e acelerando a prototipação de ideias.

## ✨ A Abordagem: Pré-treinamento e Fine-Tuning

Inspirado pelo trabalho de Ilakiyaselvan N. et al. (2023), nosso método principal consistiu em uma estratégia de duas fases para especializar o modelo no estilo da artista Ariana Grande:

1. **Pré-treinamento:** Um modelo de 4 camadas de LSTM Bidirecional foi treinado em um corpus geral com mais de 5.400 letras de diversos artistas, aprendendo padrões gerais da linguagem musical.
2. **Fine-Tuning:** O modelo pré-treinado foi então ajustado (fine-tuned) utilizando apenas as 294 letras de Ariana Grande, adaptando-o para capturar seu vocabulário, estrutura e tom específicos.

## 🚀 Resultados Principais

O modelo que passou pelo processo de **pré-treinamento e fine-tuning superou significativamente** os modelos treinados apenas com os dados da artista.

| Métrica | Modelo Inicial (Sem Dropout) | **Modelo Fine-Tuned** |
| :--- | :---: | :---: |
| Acurácia de Teste (Caractere) | 0.7288 | **0.7932** |
| Diversidade Lexical (TTR) | 0.4961 | **0.8900** |
| Taxa de Repetição (Bigramas) | 0.1568 | **0.0174** |

#### Análise Qualitativa

A melhoria também é visível na qualidade do texto gerado. Usando a mesma frase inicial (seed), a diferença é clara:

* **Letra do Modelo Inicial:** *"to you ou does it just like it when we were the one you to know that we got that's a liw can my soul is christmas is yo"* (baixa coerência).
* **Letra do Modelo Fine-Tuned:** *"love i just want to break your heart right back yeah all this time i was blind running 'round telling everybody my baby"* (maior coerência local e similaridade estilística).

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python
* **Framework:** PyTorch
* **Arquitetura:** LSTM Bidirecional (4 camadas de 256 unidades)
* **Dataset:** [Song Lyrics Dataset](https://www.kaggle.com/datasets/neisse/song-lyrics-dataset) do Kaggle
