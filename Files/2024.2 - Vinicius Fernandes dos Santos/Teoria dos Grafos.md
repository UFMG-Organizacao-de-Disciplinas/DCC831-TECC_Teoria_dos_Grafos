# Teoria dos Grafos

Livro: Graph Theory, Boundy x Murty, 2008

## Aula 1 - 23/09/2024

## Aula 2 - 24/09/2024

A parte inicial da disciplina é o que tem no início dos quatro primeiros capítulos.

G = (V, E) [Graph = (Vertices, Edges)]
V: Vértices
V(G1), V(G2)
Grau do vértice: grau = d(v), ou seja, a cardinalidade da vizinhança

$\sigma(G), \triangle(G)$ [Não sei o que é]

Um vértice V1 conectados a outros 4, teria d(V1)=4;

Teorema: $\sum^{}_{v \in V} d(v) = 2|E|$ [Faz sentido pois cada aresta é constituída por dois vértices.]

Representar um grafo como uma matriz de adjacências. Poderia também pensar numa matriz de incidência, onde Linhas = Vértices e Colunas = arestas.
No caso do matriz de incidência, se eu somar os 1's das linhas, encontro o grau do vértice. Somando tudo, dá 2|E|.

Um grafo é regular se todos os vértices têm o mesmo grau.

Um grafo é **k-regular** se $\forall v\in V(G), d(v) = k$

- Grafo 0-reg: Vértices soltos
- Grafo 1-reg: vários cotonetes
  - g(G) = inexistente/$\inf$
- Grafo 2-reg: Vários ciclos
  - Img: um triângulo e um quadrado
    - g(G) = 3
- Grafo 3-ref: [HMM 🤯] São também conhecidos como **grafos cúbicos**
  - Exemplos:
    - o Cubo
      - g(G) = 4
    - Grafo de Petersen
      - ![Grafo](https://upload.wikimedia.org/wikipedia/commons/9/91/Petersen1_tiny.svg)
      - Menor ciclo = 5
- $g(G) = min|C| \forall ciclo C \in E$

Se ele sublinha é porque ele está definindo aquela coisa.

A **Cintura** de um Grafo G é denotada por g(G) [g = girth], é o tamanho do menor ciclo de G

---

Exercícios:

1. Mostre que o número de vértices de grau ímpar em um grafo G é par.
2. Forneça um exemplo de grafo com todos os graus distintos ou mostre que não existe tal grafo. (Com |V(G)| >=2)
   1. Menor: 0
   2. Maior: n-1

- 1. Resolução

Teorema: $\sum^{}_{v \in V} d(v) = 2|E|$ [Faz sentido pois cada aresta é constituída por dois vértices.]

Par: $\sum_{v \in V} d(v)$ d(v) é par
Ímpar: $\sum_{v \in V} d(v)$ é ímpar

Par + Ímpar = 2|E|; Como o da direita é par e o da esquerda também, sabemos que o do meio será par também.

- 2. Resolução

Ele explicou mas eu não captei. É alguma coisa sobre não ter como ter o menor e o maior ao mesmo tempo.

---

Teorema da casa dos pombos.

---

Definições:

- Grafo **completo** é um grafo onde todo par de vértices é adjacente. Denotamos o completo de n vértices por $K_n$ [K de completo em alemão]
  - Exemplo: $K_4$ = (imagem de um quadrado todo interligado) ![grafo k4](https://miro.medium.com/v2/resize:fit:1400/1*UP1Xjw8JvepDoAxtux81tQ.png)
- Grafo **Ciclo** de n vértices é denotado por $C_n$
  - Exemplo: Imagem de um pentágono
- Grafo **Caminho** de n vértices é denotado por $P_n$
  - Exemplo: Uma sequência de carbono simples

Caminho: Uma sequência de vértices distintos que são adjacentes entre si.

Um **caminho** (P) em grafo G é uma sequência $v_1, v_2, ..., v_k$ de vértices distintos $(k \geq 1)$ tal que $(v_i, v_{i+1}) \in E(G), 1 \leq i \leq k-1$

Ciclo: um caminho que sai de um vértice percorre vértices e chega no vértice inicial

Um **Ciclo** (C) em um grafo G é uma sequência é uma sequência $v_1, v_2, ..., v_k$ de vértices distintos $(k \geq 3)$ tal que $(v_i, v_{i+1}) \in E(G), 1 \leq i \leq k-1$ e $(v_1, v_k \in E(G))$. [Poderia usar módulo para dizer que o i=k retorna no 1]

<!-- Esse cara tem uma vibe de Tio Rodolfo -->

[Às vezes faz-se uma alternância entre os termos ciclo, caminho, grafo, para se referir aos seus vértices ou arestas.]

- Um ciclo é um caminho?
  - Segundo ele, não. Segundo o livro, sim.
  - Depois ele começou a limitar matematicamente os limites do grafo.

Eu mencionei sobre a limitação dos graus dos vértices das bordas (v1 e vk) como sendo 1, mas ele comentou que pode acabar confundindo entre a definição do grau do grafo vs a definição do grau no grafo caminho.

Multi-grafo é um grafo que permite uma aresta de um vértice que leva a si mesmo.

[Fiquei com vontade de definir um sigma-álgebra de um grafo]

Um subgrafo H de um grafo G é um grafo tal que $V(H) \subseteq V(G)$ e $E(H) \subseteq E(G)$ Se $V(G) = V(H)$ dizemos que V(H) é um subgrafo gerador. (spanning)

Subgrafo induzido: usamos todos os vértices de um subconjunto de arestas, ou vice-versa.

Seja $X \subseteq V(G)$. Dizemos que H é o **subgrafo induzido** por X se $V(H) = X$ e $E(H) = {uv \in E(G)| u, v \in X}$.

[Preciso ter todas as arestas que existiam no grafo original]

Podemos denotar o subgrafo de G induzido por X como G[X]. Se $Y = V(G) - X$, podemos também escrever $G[X] = G - Y$

[Isso daqui seria a ideia de ir apagando alguns vértices do grafo original.]

Seja $F \subseteq E(G)$. Dizemos que H é o **subgrafo induzido** por F se $V(H) = \cup_{e \in F} e = {v \in V(G)| \exist e \in F com v extremidade de e}$ se $E(H) = F$

[A gente usa matemática só pra ser mais preciso ou escrever menos. Mas quando há perda de legibilidade, aí já não faz tanto sentido]

---

Dois grafos G e H são **isomorfos** se $\exist$ função bijetora $\phi: V(G) \cond V(H)$ tal que $uv \in E(G) \bicond \phi(u)\phi(v) \in E(H).$

---

Exercício:

Dados 2 grafos, como defino se eles são isomorfos ou não? Grande problema é saber se é NP-Completo e se dá pra resolver em tempo polinomial.
