# PopOut_Game_AI_Project
Algoritmos de Monte Carlo Tree Search e ID3 treinados para jogar o jogo PopOut. Consegues vencê-los?

# Jogo PopOut: MCTS vs ID3

Um projeto de Inteligência Artificial desenvolvido para a unidade curricular de IA na **Universidade do Porto (FCUP)**.

##  Visão Geral do Projeto
Este projeto implementa o jogo **PopOut** (uma variante dinâmica do Connect-4 onde os jogadores podem colocar uma peça a partir do topo ou remover/fazer "pop" de uma peça da sua cor na linha inferior) e compara dois paradigmas distintos de IA:
1. **Monte Carlo Tree Search (MCTS):** Motor de pesquisa adversarial em tempo real que funciona através de estatísticas e simulações de jogadas (UCT).
2. **Árvore de Decisão ID3:** Um classificador indutivo treinado offline utilizando um conjunto de dados sintético especialista gerado pelo motor MCTS.

---

##  Como Executar no Google Colab e Requisitos dos Datasets


### 1. Abrir o Projeto no Google Colab:
Disponível no link: https://colab.research.google.com/drive/13wMIT2_4kRB82vC8Cebwo5VCSuocLxDh?usp=sharing

### 2. Fazer download dos seguintes datasets: 
* dataset_iris.csv
  
* dataset_winner_15000ex
  
*Ambos estão disponíveis na pasta **Datasets** deste repositório. Faça o upload deles para o ambiente do Google Colab antes de executar as células.*

## Como fazer upload dos datasets no Colab

No menu lateral esquerdo do Google Colab:

* clicar em Files
* clicar em Upload
* arrastar os datasets(após ter feito o download):
dataset_iris.csv
dataset_winner_15000ex.csv

### 3. Executar todas as células

Após executar a célula da *Interface do Jogo PopOut*, já poderás jogar! 
## Modos disponíveis

É possível:
 
* jogar contra a IA MCTS pura;
* jogar contra a IA MCTS com heurística;
* jogar contra a IA ID3;
* colocar duas IAs a jogar entre si.

O agente MCTS com heurística apresenta a melhor performance global, enquanto o ID3 funciona como aproximação supervisionada baseada no dataset gerado a partir do MCTS com heurística.

## Para que servem os  datasets?
### 1. Dataset Iris (Validação Inicial do ID3)
Antes de enfrentar a complexidade do tabuleiro do jogo PopOut, a implementação personalizada do ID3 é validada utilizando o clássico **Iris Dataset**.

### 2. Dataset do Tabuleiro de Jogo (15.000 Exemplos)
Para treinar a árvore de decisão ID3 para jogar PopOut, é necessária uma matriz que mapeie os estados do jogo para as decisões ideais.

---

##  Resultados dos Jogos e Métricas (Resumo)

* **Ajuste do MCTS:** O MCTS Heurístico superou significativamente o MCTS Puro (**33 contra 17 vitórias**). A constante de exploração ideal foi definida como $C = 1.20$.
* **Acurácia do ID3:** Quando treinado com 15.000 tabuleiros sintéticos, a árvore ID3 personalizada alcançou uma **acurácia de 34.42%** na previsão das melhores jogadas (considerado razoável para um algoritmo que não é comumento utilizado para este tipo de jogo).
 
* **Matriz do Torneio (50 jogos por confronto):**
  * **ID3 vs. Agente Aleatório (Random):** **96% de Taxa de Vitória** (Confirmou que o modelo ID3 aprendeu com sucesso as regras estruturais e posicionais básicas).
  * **ID3 vs. MCTS Puro:** **10% de Taxa de Vitória**.
  * **ID3 vs. MCTS Heurístico:** **2% de Taxa de Vitória** (Evidencia os limites de classificadores estáticos face a motores de simulação dinâmica e de procura em tempo real).

---

##  Autores
* Telma Giovana de Freitas
* Ezequiel Tchimbaya Cachapeu Paulo
* Flávia Figueredo
* **Professor da Disciplina:** Francesco Renna (Universidade do Porto)
