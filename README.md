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

### 2. Carregar os seguintes datasets no Google Colab: 
* "dataset_iris.csv"
  
* "dataset_winner_15000ex"
>>Ambos estão disponíveis na pasta *Datasets* deste repositório. Faz o upload deles para o ambiente do Google Colab antes de executar as células.

### 3. Executar as células

Depois de executar a célula da *Interface do Jogo PopOut*, já poderás jogar! Podes optar por jogar contra qualquer uma das IA implementadas, ou podes escolher duas IAs para jogarem uma contra a outra. 
Nota que o MCTS (com heurísticas) é o que apresenta a melhor performance, ou seja, é o melhor jogador, enquanto o ID3 tem a pior performance entre as IAs.

## Para que servem estes datasets?
### 1. Dataset Iris (Validação Inicial do ID3)
Antes de enfrentar a complexidade do tabuleiro do jogo PopOut, a implementação personalizada do ID3 é validada utilizando o clássico **Iris Dataset**.

### 2. Dataset do Tabuleiro de Jogo (15.000 Exemplos)
Para treinar a árvore de decisão ID3 a jogar PopOut, é necessária uma matriz que mapeie os estados do jogo para as decisões ideais.

---

##  Resultados dos Jogos e Métricas (Resumo)

* **Ajuste do MCTS:** O MCTS Heurístico superou significativamente o MCTS Puro (**33 contra 17 vitórias**). A constante de exploração ideal foi definida como $C = 1.20$.
* **Acurácia do ID3:** Quando treinado com 15.000 tabuleiros sintéticos, a árvore ID3 personalizada alcançou uma **acurácia sólida de 34.42%** na previsão das melhores jogadas.
 
* **Matriz do Torneio (50 jogos por confronto):**
  * **ID3 vs. Agente Aleatório (Random):** **96% de Taxa de Vitória** (Confirmou que o modelo ID3 aprendeu com sucesso as regras estruturais e posicionais básicas).
  * **ID3 vs. MCTS Puro:** **10% de Taxa de Vitória**.
  * **ID3 vs. MCTS Heurístico:** **2% de Taxa de Vitória** (Evidencia os limites de classificadores estáticos face a motores de simulação dinâmica e de procura em tempo real).

---

##  Autores
* Telma Giovana de Freitas
* Ezequiel Tchimbaya Cachapeu Paulo
* Flávia 
* **Professor da Disciplina:** Francesco Renna (Universidade do Porto)
