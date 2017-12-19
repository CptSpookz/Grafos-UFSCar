# Grafos-UFSCar
Repositório para o trabalho final de grafos - UFSCar 2017-2

## PROJETO 1: SNAKES AND LADDERS

Snakes and Ladders é um famoso jogo de tabuleiro em que a cada rodada um jogador joga uma moeda não viciada e avança 1 casa se obtiver cara ou avança 2 casas se obtiver coroa. Se o jogador para no pé da escada, então ele imediatamente sobe para o topo da escada. Se o jogador cai na boca de um cobra então ele imediatamente escorrega para o rabo. O jogador sempre inicia no quadrado de número 1. O jogo termina quando ele atinge o quadrado de número 36.

Tabuleiro de Snakes and Ladders

![alt text](https://github.com/CptSpookz/Grafos-UFSCar/tree/master/pages/img/snakesladders.jpg "Snakes and Ladders")

Com base nas informações, responda:

a) Especifique o diagrama de estados da cadeia de Markov que representa o jogo, computando para isso a matriz de transição de estados P

b) Desenvolva um script em Python para calcular a distribuição estacionária da cadeia de Markov homogênea em questão. Qual é a probabilidade de um jogador vencer o jogo, ou seja, qual a probabilidade de se atingir o estado 36 no longo prazo? Considere k = 100 um número suficiente de iterações no Power Method. Quais os estados mais prováveis de serem acessados?

c) Especifique a matriz P_ (P_barra) referente ao modelo Pagerank considerando alpha = 0.1. Considerando k = 100, aplique o Power method e compare o resultado com o obtido no item b). As distribuições estacionárias obtidas em b) e c) são iguais ou diferentes?

## PROJETO 2: ÁRVORE GERADORA MÍNIMA

A partir de um dataset específico (grafo ponderado armazenado em arquivo .gml, .graphml, .txt, .net, etc) implementar o algoritmo de Prim para extrair uma Minimum Spanning Tree (MST) de G.

Grafo HA30 com 30 cidades do mundo

![alt text](https://github.com/CptSpookz/Grafos-UFSCar/tree/master/pages/img/ha30.png "30 cidades do mundo")

OBS: Para ler e transformar uma matriz de adjacências em um grafo

`import numpy as np
import networkx as nx

A = np.loadtxt('matriz.txt')
G = nx.from_numpy_matrix(A)`

## PROJETO 3: BUSCA EM LARGURA E PROFUNDIDADE

Implementar os algoritmos BFS e DFS para extrair as árvores BFS-tree e DFS-tree dos grafos a seguir:

Zachary's Karate Club

![alt text](https://github.com/CptSpookz/Grafos-UFSCar/blob/master/pages/img/zach_layout3.jpg "Zachary karate club")

Dolphins Social Network

![alt text](https://github.com/CptSpookz/Grafos-UFSCar/blob/master/pages/img/dolphins.png "Dolphins social network")

OBS: Para ler um grafo no formato .paj 

`import networkx as nx

G = nx.read_pajek('karate.paj')`

## PROJETO 4: ÁRVORES DE CAMINHOS MÍNIMOS E AGRUPAMENTO DE DADOS
A partir de um dataset específico (grafo ponderado armazenado em arquivo .gml, .graphml, .txt, .net, etc) e implementar o algoritmo de Dijkstra para extrair uma árvore de caminhos mínimos de G.

### METODOLOGIA

Após a implementação do algoritmo, uma forma de crescer várias subárvores de caminhos mínimos é inicializar várias sources, ou seja, atribuir custo inicial zero a um número K de vértices. O restante do algoritmo permanece intacto. O que irá acontecer é um processo de disputa entre cada uma das raízes para verificar qual delas irá conquistar cada vértice de G. Ao final da execução um vértice estará "pendurado" apenas a uma única subárvore, fazendo com que tenhamos vários grupos de nós, similar ao que acontecia com as MST's. Porém aqui há supervisão no processo de formação dos grupos, uma vez que o usuário pode definir de onde as subárvores irão iniciar o crescimento (esses pontos devem ser escolhidos de forma a definir o centro dos agrupamentos).

### QUESTIONAMENTOS

Considerando o grafo em questão, mostre os resultados (plote graficamente) obtidos para:
a) 2 agrupamentos (K = 2) 
b) 3 agrupamentos (K = 3)
59 cidades da Alemanha Ocidental

Grafo com 59 cidades da Alemanha ocidental e suas distâncias

![alt text](https://github.com/CptSpookz/Grafos-UFSCar/blob/master/pages/img/wg59.png "5 cidades da Alemanha ocidental e suas distâncias")


OBS: Para ler e transformar uma matriz de adjacências em um grafo

`import numpy as np
import networkx as nx

A = np.loadtxt('matriz.txt')
G = nx.from_numpy_matrix(A)`

## PROJETO 5 - OPÇÃO A: O PROBLEMA DO CAIXEIRO VIAJANTE
Desenvolver um programa que deve ler um grafo Hamiltoniano ponderado a partir de um arquivo qualquer e através de um algoritmo visto em sala (2-otimal ou Twice-Around) obter 10 soluções diferentes para o problema do caixeiro-viajante.

### METODOLOGIA

Para obter soluções distintas para o problema há algumas heurísticas comumente adotadas na prática: utilizar diferentes inicializações, ou seja, soluções iniciais. Elas podem ser geradas simplesmente aleatoriamente (selecionando vértices quaisquer) ou utilizando alguma heurística, como por exemplo a escolha do vizinho mais próximo por exemplo. Dessa forma, escolhe-se aleatoriamente apenas o primeiro vértice do ciclo (v0) e depois sempre é escolhido como próximo elemento da sequência o vizinho mais próximo do vértice atual, até que o ciclo Hamiltoniano seja formado (não sobre mais vértices). 

### QUESTIONAMENTOS

Liste as 3 melhores soluções e as 3 piores obtidas. Qual a diferença de custo entre a melhor e a pior? Discuta como a diferença pode ser significativa.

Considere o grafo a seguir de 30 vértices (HA30)

![alt text](https://github.com/CptSpookz/Grafos-UFSCar/tree/master/pages/img/ha30.png "30 cidades do mundo")


