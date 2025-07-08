---
layout: post
title: A personal Proof of a special Version of the Spectral Theorem
date: 2025-07-05 16:57:03 +0200
categories: jekyll update
---
## Übungsaufgabe 1
> Zeigen Sie: Für jede Zusammenhangskomponente eines einfachen (endlichen) Graphen mit Maximalgrad 2 (d.h. für alle $v \in V(G)$ gilt $\deg(v) \leq 2$) ist entweder ein Weg oder ein Kreis
### Beweis
Sei $m = \min\{\deg(v): v\ \in V\}$. Wir nennen die Zusammenhangskomponente ab nun $T$. Es gibt 3 Fälle:

Fall 1: $m = 0$
Dann $T$  ein einziger Knoten und das ist trivialerweise ein Weg. 

Fall 2: $m \geq 1$
Wir wählen einen Knoten $v_0$ aus $T$. Nun wählen wir $v_1 \in T$, so dass $\{v_0, v_1\} \in E(T)$. Wir geben einen Algorithmus in pseudo code an:

```
new_graph = (V={v_0,v_1}, E={{v_0,v_1}})
k = 1
while True: 
	if deg(v_k) = 1:
		stop algorithm

	else:
		try:chose randomly v_{k+1} with {v_k,v_{k+1}} not in E(new_graph) 
			and add v_{k+1} & {v_k,v_{k+1}} to new_graph
		else: stop algorithm
```  
 
Wir beobachten: 
Erstens muss der Algorithmus nach endlich vielen Schritten abbrechen, da $|V| < \infty$.

Zweitens: Da $T$ nach Definition zusammenhängend ist, kann man mit dem Algorithmus jeden Knoten von $T$ in einem der erzeugten Teilgraphen von T bekommen.  Da der Algorithmus erst aufhört, wenn es keine neuen Kanten mehr gibt und man jeden Knoten erreichen kann, kann man auch jede Kante von T in einen der erzeugten Teilgraphen bekommen.

Drittens: Es gibt es wegen $\deg(v) \leq 2$ für alle $v \in V$  auch nur maximal zwei Kanten zu jedem Knoten. Zu Schritt $k$ kann es deshalb auch maximal nur eine auswählbare Kante geben, da im Schritt $k$ schon eine Kante, zu der $v_k$ gehört, ausgewählt wurde. Das bedeutet dass der Algorithmus einen eindeutigen zusammenhängenden Teilgraphen in $T$ produziert, der wegen zweitens alle Knoten sowie alle Kanten von $T$ enthält. 

Daraus folgt, dass der eindeutig erzeugte Teilgraph, der immer ein Kreis oder ein Weg ist, schon T sein muss. 

## Aufgabe 2
> Sei $\bar G = \binom{V}{2} \setminus G(E)$. Zeigen Sie: Für alle Graphen $G$ gilt: $G$ oder $\bar G$ ist zusammenhängend. 

### Beweis
Sei $G$ ein Graph. Um ein mathematisches "oder" zu beweisen nehmen wir an, dass $G$nicht zusammenhängend ist. $G$ besteht also aus $k$ zusammenhangskomponenten $T_1,...,T_k$. Um zu zeigen, dass $\bar G$ zusammenhängend ist, müssen wir zeigen, dass je zwei Knoten durch einen Weg verbunden sind. 

Sei $t_i \in T_i, u_j \in T_j$. Nach Konstruktion ist $\{t_i, u_j\} \in \bar G$ für alle $i \neq j \in \{1,...,k\}$. Nehmen wir nun $a,b \in T_i$, dann ist $\{a, u_j\},\{b, u_j\} \in \bar G$ und daraus folgt, dass es einen Weg zwischen $a$ und $b$ gibt, heißt alle Knoten sind durch Kanten verbunden. 