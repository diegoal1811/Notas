---
title: Unidad 2 - Representación del Conocimiento
draft: false
tags:
---
-----
# [[Contenido del curso|🏠 Inicio - Sistemas Inteligentes]]

-----
# Programación Lógica

Modela problemas por medio de la abstracción utilizando un sistema de lógica formal que permite obtener una conclusión con base a hechos y reglas.

Estudia el uso de la lógica para plantear problemas y el control sobre las reglas de inferencia para alcanzar una solución de manera automática.

## La programación lógica intenta resolver lo siguiente:

Dado un problema S, saber si la afirmación A es solución o no del problema o en que casos lo es. Además queremos que los métodos sean implantados en maquinas de forma que la resolución del problema se haga de forma automática

- La programación lógica construye una base de conocimientos mediante reglas y hechos.
- Lógica es el estudio del razonamiento; se refiere específicamente a si el razonamiento es correcto. 
- La lógica se centra en la relación entre las afirmaciones y no en el contenido de una afirmación en particular.

>[!example] Ejemplo
> 1. Todos los ingenieros usan camisas a cuadros.
> 2. Cualquier persona que usa camisa a cuadros es ingeniero en sistemas.
> 3. Por lo tanto, todos los ingenieros son ingenieros en sistemas.

## Proposiciones
- Una oración que es verdadera o falsa, pero no ambas.
- Es común que se expresen como una oración declarativa (no como pregunta, orden exclamación, etc.)
- Son los bloques básicos de la construcción de la teoría de lógica
- Se usan variables como `p, q, r`, etc.

>Ejemplos
>1. Los únicos enteros positivos que dividen a 7 son 1 y el 7.
>2. Alfred Hitchcock ganó un premio por la dirección de "Rebeca"
>3. Para todo entero positivo n, existe un número primero mayor que n.
>4. La Tierra es el único planeta en el universo que tiene vida.


Se usará la siguiente notación:
>p: 2+2=5

Sean p y q proposiciones
Se llama conjunción de p y q y se escribe:
`p ∧ q`

Se llama disyunción de p y q y se escribe

`p ∨ q`

La proposición resultante de la combinación de conjunciones y disyunciones se llama proposición compuesta.

Existen dos tipos de proposiciones
- Simples o atómicas
- Compuestas o moleculares

Las atómicas están compuestas por una sola oración.
La moleculares son las que están estructuradas por dos o más proposiciones simples unidas por los operadores lógicos: ∧, ∨, ⟹, ⟺.

----
## Tabla de verdad
Los valores de verdad de las proposiciones tales como conjunciones o disyunciones, se pueden describir por las ==**tablas de verdad**==

La tabla de verdad de una proposición `P`, formada por las proposiciones individuales `p1, . . . , pn`, enumera todas las posibles combinaciones de los valores de verdad para `p1, . . . , pn`, donde `V` denota verdadero y `F` denota falso, y da la lista de valores de verdad de `P` para cada combinación.

>Ejemplo `p ∧ q`


| P   | Q   | S   |
| --- | --- | --- |
| F   | F   | F   |
| F   | V   | F   |
| V   | F   | F   |
| V   | V   | V   |

>Ejemplo `p ∨ q`

| P   | Q   | S   |
| --- | --- | --- |
| F   | F   | F   |
| F   | V   | V   |
| V   | F   | V   |
| V   | V   | V   |

>[!tldr] Ejercicios

### 1. p ∧ ¬q

| p   | q   | ¬q  | p∧ ¬q |
| --- | --- | --- | ----- |
| V   | V   | F   | F     |
| V   | F   | V   | V     |
| F   | V   | F   | F     |
| F   | F   | V   | F     |

### 2. (¬p ∨ ¬q) ∨ p

| p   | ¬p  | q   | ¬q  | ¬p ∨ ¬q | (¬p ∨ ¬q) ∨ p |
| --- | --- | --- | --- | ------- | ------------- |
| V   | F   | V   | F   | F       | V             |
| V   | F   | F   | V   | V       | V             |
| F   | V   | V   | F   | V       | V             |
| F   | V   | F   | V   | V       | V             |

### 3. (p ∨ q) ∧ ¬p

| p   | ¬p  | q   | p ∨ q | (p ∨ q) ∧ ¬p |
| --- | --- | --- | ----- | ------------ |
| V   | F   | V   | V     | F            |
| V   | F   | F   | V     | F            |
| F   | V   | V   | V     | V            |
| F   | V   | F   | F     | F            |

### 4. (p ∧ q ) ∧¬p

| p   | ¬p  | q   | p ∧ q | (p ∧ q ) ∧¬p |
| --- | --- | --- | ----- | ------------ |
| V   | F   | V   | V     | F            |
| V   | F   | F   | F     | F            |
| F   | V   | V   | F     | F            |
| F   | V   | F   | F     | F            |

### 5. (p ∧ q) ∨ (¬p ∨ q)

| p   | q   | ¬p  | p ∧ q | ¬p ∨ q | (p ∧ q) ∨ (¬p ∨ q) |
| --- | --- | --- | ----- | ------ | ------------------ |
| V   | V   | F   | V     | V      | V                  |
| V   | F   | F   | F     | F      | F                  |
| F   | V   | V   | F     | V      | V                  |
| F   | F   | V   | F     | V      | V                  |

### 6. ¬(p ∧ q) ∨ (r ∧ ¬p)

| p   | q   | r   | ¬p  | p ∧ q | r ∧ ¬p | ¬(p ∧ q) | ¬(p ∧ q) ∨ (r ∧ ¬p) |
| --- | --- | --- | --- | ----- | ------ | -------- | ------------------- |
| V   | V   | V   | F   | V     | F      | F        | F                   |
| V   | V   | F   | F   | V     | F      | F        | F                   |
| V   | F   | V   | F   | F     | F      | V        | V                   |
| V   | F   | F   | F   | F     | F      | V        | V                   |
| F   | V   | V   | V   | F     | V      | V        | V                   |
| F   | V   | F   | V   | F     | F      | V        | V                   |
| F   | F   | V   | V   | F     | V      | V        | V                   |
| F   | F   | F   | V   | F     | F      | V        | V                   |

### 7. (p ∨ q) ∧ (¬p ∨ q) ∧ (p ∨ ¬q)  ∧ (¬p ∨ ¬q)

| p   | q   | ¬p  | ¬q  | p ∨ q | ¬p ∨ q | p ∨ ¬q | ¬p ∨ ¬q |
| --- | --- | --- | --- | ----- | ------ | ------ | ------- |
| V   | V   | F   | F   | V     | V      | V      | F       |
| V   | F   | F   | V   | V     | F      | V      | V       |
| F   | V   | V   | F   | V     | V      | F      | V       |
| F   | F   | V   | V   | F     | V      | V      | V       |

#### 7.1 (p ∨ q) ∧ (¬p ∨ q)

| p ∨ q | ¬p ∨ q | (p ∨ q) ∧ (¬p ∨ q) |
| ----- | ------ | ------------------ |
| V     | V      | V                  |
| V     | F      | F                  |
| V     | V      | V                  |
| F     | V      | F                  |
#### 7.2 (p ∨ ¬q)  ∧ (¬p ∨ ¬q)

| p ∨ ¬q | ¬p ∨ ¬q | (p ∨ ¬q)  ∧ (¬p ∨ ¬q) |
| ------ | ------- | --------------------- |
| V      | F       | F                     |
| V      | V       | V                     |
| F      | V       | F                     |
| V      | V       | V                     |

| (p ∨ q) ∧ (¬p ∨ q) | (p ∨ ¬q)  ∧ (¬p ∨ ¬q) | ==(p ∨ q) ∧ (¬p ∨ q)== ∧ ==(p ∨ ¬q)  ∧ (¬p ∨ ¬q)== |
| ------------------ | --------------------- | -------------------------------------------------- |
| V                  | F                     | F                                                  |
| F                  | V                     | F                                                  |
| V                  | F                     | F                                                  |
| F                  | V                     | F                                                  |
### 8. ¬(p ∨ q) ∨ (¬q ∨ r)

| p   | q   | r   | p ∨ q | ¬p  | ¬q  | ¬q ∨ r | ¬(p ∨ q) | ¬(p ∨ q) ∨ (¬q ∨ r) |
| --- | --- | --- | ----- | --- | --- | ------ | -------- | ------------------- |
| V   | V   | V   | V     | F   | F   | V      | F        | V                   |
| V   | V   | F   | V     | F   | F   | F      | F        | F                   |
| V   | F   | V   | V     | F   | V   | V      | F        | V                   |
| V   | F   | F   | V     | F   | V   | V      | F        | V                   |
| F   | V   | V   | V     | V   | F   | V      | F        | V                   |
| F   | V   | F   | V     | V   | F   | F      | F        | F                   |
| F   | F   | V   | F     | V   | V   | V      | V        | V                   |
| F   | F   | F   | F     | V   | V   | V      | V        | V                   |

----
## Condicional o implicación ⇒
- p: antecedente o hipótesis
- q: consecuente o conclusión
- Lo podemos leer como: 
	- Si... entonces, se sigue, por tanto, etc.
- p⇒q ≠q ⇒p

## Bicondicional o equivalencia ⇔

Lo podemos leer como: si y solo si, entonces y solo entonces, es idéntico, equivale a, etc...

p⇔q =q ⇔p

| p   | q   | p⇒q |
| --- | --- | --- |
| V   | V   | V   |
| V   | F   | F   |
| F   | V   | F   |
| F   | F   | V   |

----
## Argumentos: razonamientos que estudia la lógica

Es un conjunto de una o más proposiciones, la última de las cuales es la conclusión; las anteriores se llaman premisas
De manera intuitiva, las premisas son la evidencia que deben convencernos de la veracidad de la conclusión y el argumento es la concatenación de las premisas y la conclusión.

>Ejemplo
>Si Alfredo es elegido presidente de la asociación de colonos, entonces Bernardo es elegido vicepresidente y Carlos es elegido como tesorero, Bernardo no es elegido vicepresidente, por lo tanto Alfredo no es elegido presidente de la asociación de colonos.

p: Alfredo es elegido presidente de la asociación de colonos
q: Bernardo es elegido vicepresidente
r: Carlos es elegido tesorero

1. (p ⇒ q) ∧ r
2. ~q
- ∴~p

{ (p ⇒ q) ∧ r } ∧ ~q ⇒ ~p

### Clasificación de argumentos
- Tautología: proposición que es verdadera para todos los posibles valores de verdad de sus componentes simples:  
- Contradicción o absurdo: si tiene un valor falso para todos los posibles valores de verdad de sus componentes simples.
- Contingencia: cuando puede ser verdadera o falsa, dependiendo de los valores de verdad de sus componentes simples.

(diapositiva 56)

### Lógica proposicional

También llamada lógica de enunciados: toma como elemento básico las frases declarativas simples o proposiciones. Su estructura está dada por

```Haskell
𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎→𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎 𝐴𝑡ó𝑚𝑖𝑐𝑎|𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎 𝐶𝑜𝑚𝑝𝑙𝑒𝑗𝑎.
𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎 𝐴𝑡ó𝑚𝑖𝑐𝑎→𝑉𝑒𝑟𝑑𝑎𝑑𝑒𝑟𝑜|𝐹𝑎𝑙𝑠𝑜|𝑆í𝑚𝑏𝑜𝑙𝑜.
𝑆í𝑚𝑏𝑜𝑙𝑜→𝑃|𝑄|𝑅|…
𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎 𝐶𝑜𝑚𝑝𝑙𝑒𝑗𝑎  →¬𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎 | (𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎⋀𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎)  |  (𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎∨𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎)
					 | (𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎⟹𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎)  |(𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎⟺𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎)
```

### Lógica de Primer Orden
También llamada lógica de predicados: es un sistema deductivo basado en un Lenguaje Lógico Matemático Formal. Su estructura esta dada por:

```Haskell
𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎→𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎 𝐴𝑡ó𝑚𝑖𝑐𝑎 | (𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎 𝐶𝑜𝑛𝑒𝑐𝑡𝑖𝑣𝑎 𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎)|  
                     𝐶𝑢𝑎𝑛𝑡𝑖𝑓𝑖𝑐𝑎𝑑𝑜𝑟 𝑉𝑎𝑟𝑖𝑎𝑏𝑙𝑒 …𝑆𝑒𝑡𝑛𝑒𝑐𝑖𝑎 | ¬𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎
𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎 𝐴𝑡ó𝑚𝑖𝑐𝑎 →𝑃𝑟𝑒𝑑𝑖𝑐𝑎𝑑𝑜(𝑇é𝑟𝑚𝑖𝑛𝑜 …)| 𝑇é𝑟𝑚𝑖𝑛𝑜=𝑇é𝑟𝑚𝑖𝑛𝑜
𝑇é𝑟𝑚𝑖𝑛𝑜 →𝐹𝑢𝑛𝑐𝑖ó𝑛(𝑇é𝑟𝑚𝑖𝑛𝑜)|𝐶𝑜𝑛𝑠𝑡𝑎𝑛𝑡𝑒|𝑉𝑎𝑟𝑖𝑎𝑏𝑙𝑒
𝐶𝑜𝑛𝑒𝑐𝑡𝑖𝑣𝑎 → ∧| ∨|  ⟹| ⟺
𝐶𝑢𝑎𝑛𝑡𝑖𝑓𝑖𝑐𝑎𝑑𝑜𝑟→ ¬𝑆𝑒𝑛𝑡𝑒𝑛𝑐𝑖𝑎
𝑉𝑎𝑟𝑖𝑎𝑏𝑙𝑒→𝑎|𝑏|𝑐|…
```

## Cláusulas de Horn

En lógica proposicional, una fórmula lógica es una cláusula de Horn si es una cláusula (disyunción de literales) con, como máximo, un literal positivo.

```Haskell
¬𝑝 ∨ ¬𝑞 ∨ ⋯ ∨ ¬𝑡 ∨ 𝑢
(𝑝 ∧ 𝑞 ∧ ⋯∧ 𝑡) → 𝑢
```

Cláusula definite: Cláusula de Horn con exactamente un literal positivo.

Hecho: Cláusula definite sin literales negativos.

Cláusula objetivo: no tiene literales positivos (consulta)

$\text{antecedente} \text{ → } \text{consecuente}$

>Si es verdad el antecedente, entonces es verdad el consecuente

----
# [[Contenido del curso|🏠 Inicio - Sistemas Inteligentes]]

----
# [[Unidad 1 - Fundamentos de sistemas inteligentes|⬅️Anterior: Unidad 1 - Fundamentos de sistemas inteligentes]]

# [[Unidad 3 - Agentes inteligentes|Siguiente: Unidad 3 - Agentes inteligentes ➡️]]
---
