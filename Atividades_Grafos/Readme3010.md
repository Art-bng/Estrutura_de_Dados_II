# Projeto: Contingência de Rotas Aéreas com Grafos (BFS e DFS)

## 1. Descrição do Problema
Este projeto modela uma malha de aviação civil regional com 7 aeroportos principais (vértices) e suas rotas diretas (arestas). O objetivo é simular o comportamento de buscas estruturadas em grafos para encontrar caminhos alternativos quando ocorrem falhas de navegação (como pane de GPS em hubs estratégicos).

## 2. Modelagem do Grafo
* **Vértices (V = 7):** 
  * `BSB` (Brasília)
  * `BHZ` (Belo Horizonte)
  * `GIG` (Rio de Janeiro)
  * `GRU` (São Paulo)
  * `CWB` (Curitiba)
  * `CGB` (Cuiabá)
  * `GYN` (Goiânia)
* **Arestas (E):** Conexões bilaterais simulando os trechos de voo disponíveis na malha.

## 3. Estrutura e Algoritmos Utilizados
* **Lista de Adjacência:** Armazenada em um dicionário Python para eficiência de mapeamento $O(V + E)$.
* **BFS (Busca em Largura):** Utiliza uma Fila (`deque`) em ordem FIFO para encontrar o caminho com a **menor quantidade de conexões/escalas**.
* **DFS (Busca em Profundidade):** Utiliza uma Pilha (LIFO) para explorar ramos em profundidade, encontrando um caminho viável alternativo, sem garantia de ser o mais curto.

## 4. Análise dos Testes
* **Cenário A (Rede Normal):** Ambos os algoritmos encontram com sucesso rotas viáveis de Brasília (`BSB`) para Curitiba (`CWB`). O BFS prioriza o menor número de saltos.
* **Cenário B (Com Bloqueio):** Ao indisponibilizar a rota entre Goiânia (`GYN`) e São Paulo (`GRU`), o sistema recalcula as rotas de contingência contornando o bloqueio por meio de nós adjacentes remanescentes.
