---
title: Unidad 3 - Agentes inteligentes
draft: false
tags:
---

----
# [[Contenido del curso|🏠 Inicio - Sistemas Inteligentes]]

----
# 🤖🧠 Agentes inteligentes 
# Definición

>[!quote] ## Agente inteligente
>Es cualquier cosa capaz de percibir su medioambiente con la ayuda de sensores y actuar en ese medio utilizando actuadores.

![[Agente Inteligente.png]]

## Percepción
Indica que el agente puede recibir entradas en cualquier instante. ==La secuencia de percepciones== de un agente refleja el historial completo de lo que el agente ha recibido.

Un agente tomará una decisión en un momento dado dependiendo de la secuencia completa de percepciones hasta ese instante.

En términos matemáticos se puede decir que el comportamiento del agente viene dado por la función del agente que proyecta una percepción dada de una acción


$$
Percepciones → \text{(función del agente)} → Acciones
$$

>[!example] Ejemplo

| Secuencia de percepciones | Acción          |
| ------------------------- | --------------- |
| A, limpio                 | Mover derecha   |
| A, sucio                  | Aspirar         |
| B, limpio                 | mover izquierda |
| B, sucio                  | aspirar         |

----
## Agentes racionales 

>[!quote] Agente racional
>Un agente racional es aquel que hace lo correcto; es decir, cada elemento de la tabla que define la función del agente se tendría que rellenar correctamente.

>[!info] Agente racional - GPT
>Un agente racional es un concepto utilizado en la inteligencia artificial y la teoría de la decisión para describir un sistema que toma decisiones de manera óptima basándose en la información disponible y sus objetivos. Un agente racional es capaz de percibir su entorno, razonar sobre la información disponible y elegir la acción más adecuada para alcanzar sus objetivos.

>[!question] Qué es hacer lo correcto?

Como primera aproximación, se puede decir que lo correcto es aquello que permite al agente obtener un mejor resultado.

La racionalidad depende de cuatro factores:
1. La medida de rendimiento que define el criterio de éxito.
2. El conocimiento acumulado del medio en el que habita el agente.
3. Las acciones que el agente puede llevar a cabo.
4. La secuencia de percepciones del agente hasta ese momento.

### Agente racional
En cada posible secuencia de percepciones, un agente racional deberá emprender aquella acción que supuestamente maximice su medida de rendimiento, basándose en las evidencias aportadas por la secuencia de percepciones y en el conocimiento que el agente mantiene almacenado.

### Agente omnisciente
Es aquel que conoce el resultado de su acción y actúa de acuerdo con el; sin embargo en realidad la omnisciencia no es posible.

### Aprendizaje
Como no se conoce a priori todo el entorno, se debe percibir y aprender para poder maximizar el rendimiento (memoria).

### Exploración
Recopilación de información, realizando acciones con la intención de modificar percepciones futuras y memorizando el resultado de cada acción.

### Autonomía
Un agente racional debe poder aprender como tiene que compensar la falta de conocimiento que posee. Si no posee ningún conocimiento inicial, debe actuar de forma aleatoria.

>A un agente racional hay que dotarlo de un conocimiento inicial y las capacidades de explorar y aprender

### Entorno de trabajo
Básicamente es el problema del mundo real que tiene que resolver el agente. Este incluye las medidas de rendimiento, el entorno, los actuadores y los sensores; estos son denominados REAS

(Rendimiento, Entorno, Actuadores, Sensores)

En el diseño de un agente racional el primer paso siempre consiste en especificar el entorno de trabajo de la forma más completa posible.

------

>[!example] Ejemplo - Agentes inteligentes

| Agente             | Medidas de rendimiento                                                                                                                                       | Entorno                                                                                                                                        | Actuadores                                                                                                                                                   | Sensores                                                                                                                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Garrotero          | Número de mesas limpias<br><br>Conteo de suministros<br><br>Índice de satisfacción  como encuestas<br><br>Número de platos rotos<br><br>Número de accidentes | Distribución del local<br><br>Materiales o superficie<br><br>Exterior o interior                                                               | Mecanismos de movimiento<br><br>Pinzas<br><br>Insumos para limpieza                                                                                          | Sensores de distancia<br><br>Sensores de humedad o líquidos<br><br>Sensor infrarrojo<br><br>Sensor de batería<br><br>Sensores de temperatura<br><br>Dinamómetro<br><br>Sensor de presión |
| Diagnóstico médico | Precisión y rapidez en el diagnóstico.<br><br>Número de errores médicos<br><br>Satisfacción del paciente<br><br>Eficiencia en el uso de recursos médicos     | Ubicación<br><br>Espacio suficiente<br><br>Conectividad<br><br>Suministro Eléctrico<br><br>Posicionamiento de equipos<br><br>Acceso Controlado | Interfaces de usuario<br><br>Mecanismos para interactuar con el paciente<br><br>Sistema de comunicación para compartir los resultados<br><br>Insumos médicos | Dispositivos de entrada<br><br>Sensores biométricos<br><br>Sensor de batería<br><br>Sensores de temperatura y humedad                                                                    |

----
# Propiedades entornos de trabajo
### Totalmente observable
Se da cuando los sensores del agente saben que basa en todo momento en su mundo (variables relevantes para la toma de decisiones)

### Parcialmente observables
Se refiere a un tipo de entorno en el que el agente no tiene acceso a toda la información relevante en cada momento. Más específicamente, el agente solo puede percibir una porción limitada o censurada del estado total del entorno.

### Determinista
Es cuando el siguiente estado del sistema esta determinado por el estado actual y la  acción que tome el agente.

### Estocástico
Es aquel en el que las acciones del agente inteligente no conducen a resultados deterministas y predecibles con total certeza. En su lugar, el resultado de cada acción está sujeto a cierto grado de incertidumbre o aleatoriedad.

### Episódico
Cuando el agente actúa en episodios atómicos, es decir para cada percepción existe
solo una acción a realizar. Los episodios determinan el comportamiento del agente.

### Secuencial
Las decisiones actuales pueden afectar las decisiones futuras, es decir si se toma en cuenta el historial de estados del medio y acciones del agente.

### Estático
El entorno es el mismo si el agente está presente o no, es decir no es susceptible a cambios.

### Dinámico
Cuando el entorno cambia con el paso de tiempo, incluso es diferente con/sin el agente.

### Discreto
Tiene un número de estados finito y bien definido de estados.

### Continuo
El número de estados y acciones es continuo, se decir el estado del sistema no es el mismo en este momento que 0.0000001 segundos después.

### Agente individual y multiagente
#### Entorno individual
En este tipo de entorno, solo interactúa un agente inteligente. El agente percibe el estado del entorno, selecciona y ejecuta una acción, y recibe una recompensa o retroalimentación en función de los resultados de esa acción. El objetivo del agente en un entorno individual es aprender una política óptima que maximice su recompensa total a lo largo del tiempo.

#### Multiagente
En este tipo de entorno, interactúan múltiples agentes inteligentes, cada uno con su propio objetivo y política de acción. Los agentes pueden colaborar entre sí para lograr un objetivo común o competir por recursos limitados. La complejidad de un entorno multiagente aumenta en comparación con un entorno individual, ya que los agentes deben tener en cuenta las acciones y reacciones de los demás agentes al tomar decisiones.

### Agentes competitivos y cooperativos
#### Entornos con agentes competitivos
En estos entornos, los agentes compiten entre sí por recursos limitados o intentan maximizar sus propias recompensas a expensas de las demás. Cada agente tiene su propia política y objetivo, y las acciones de un agente pueden afectar directamente las recompensas de los demás.

#### Entornos con agentes cooperativos
En estos entornos, los agentes trabajan juntos para lograr un objetivo común o maximizar una recompensa compartida. Los agentes deben colaborar y coordinar sus acciones para tener éxito. 

----
# Estructura de un agente

$$
Agente = arquitectura + programa
$$

## Programas de agente
1. Recibir como entrada las lecturas de los sensores.
2. Procesar estas lecturas y determinar una acción.
3. Enviar la acción a realizar a los actuadores.

Tipos básicos de programas de agente:
1. Agentes reactivos simples.
2. Agentes reactivos basados en modelos.
3. Agentes Basados en objetivos.
4. Agentes basados en utilidad.

----
# Agentes reactivos simples
Seleccionan sus acciones con base a las percepciones actuales, y no toman en cuenta la secuencia de percepciones pasadas.
- Reglas condición-acción
	- ==Si== <condición>, ==entonces== <acción>

>[!example] Ejemplo - Robot aspiradora

![[agenteRobotAsìradora.png]]

```java
funcion aspiradora(ubicación,estado) devuelve acción
	si estad = "Sucio" entonces devolver "Aspirar"
	sino
		si ubicación = "A" entonces devolver "Derecha"
		sino
			si ubicación = "B" entonces devolver "Izquierda"
```

![[agenteReactivoSimple.png]]

```java
funcion Agente_Reactivo_Simple(percepción) devuelve acción
	reglas : conjunto de reglas condición-acción

	estado ← Interpretar(percepción).
	regla ← Regla-conicidencia(estado, reglas).
	acción ← reglas[regla].
	devolver acción.
```

----
# Agentes reactivos basados en modelos

Esos agentes almacenan un estado interno que depende de la historia de percepciones
La actualización del estado interno depende de dos factores:
- Información de cómo evoluciona el mundo independientemente del agente.
- Información de cómo afectan al mundo las acciones del agente

>A estos lo denominamos ==modelo del mundo==

![[agenteReactivoBasadoModelos.png]]

```Java
funcion Agente_Reactivo_Modelos(percepción) devuelve acción
	estado: descripción actual del estado del mundo.
	reglas: conjunto de reglas condición-acción.
	acción: la acción más reciente.
	
	estado ← Actualizar-Estado(estado, acción, percepción).
	regla ← Regla-conicidencia(estado, reglas).
	acción ← Regla-Acción[regla].
	devolver acción.
```

---
# Agentes basados en objetivos

El conocimiento del mundo actual no es suficiente para decidir una acción.

Además de la descripción del estado actual, el agente necesita algún tipo de información sobre su meta que describa las situaciones que son deseables.

Se puede utilizar la información sobre los resultados de las acciones posibles para elegir las acciones que permitan alcanzar el objetivo.

El agente tiene que considerar secuencias complejas para encontrar el camino que le permita alcanzar el objetivo. La búsqueda y la planificación son los sub-campos de la IA centrados en encontrar secuencias de acciones que permitan a los agentes alcanzar sus metas.

![[agenteBasadoObjetivos.png]]

----
# Agentes basados en utilidad

En muchas ocasiones las metas no son suficientes para tener un comportamiento eficiente.
Podemos tener diferentes secuencias de acciones y obtener la misma meta.

Necesitamos una medida de eficiencia, es decir que acción es la más útil.

Una función de utilidad cuantifica un estado o una secuencia de estados.
Una función de utilidad permite tomar decisiones en casos en las que las metas sean inadecuadas:
 - Metas conflictivas
 - Es posible que la meta no se pueda alcanzar

![[agenteBasadoUtilidad.png]]

----
# Agentes que aprenden

Un agente que aprende tiene 4 componentes:
### 1. Elemento de crítica
Es el responsable de realimentar la actuación al agente al elemento de aprendizaje
### 2. Elemento de aprendizaje
Responsable de las mejoras
### 3. Elemento de actuación
Responsable de seleccionar las acciones
### 4. Generador de problemas
Sugiere acciones para alcanzar estados nuevos

----
# [[Contenido del curso|🏠 Inicio - Sistemas Inteligentes]]

----
# [[Unidad 2 - Programacion Logica|⬅️ Anterior: Unidad 2 - Representación del Conocimiento]]

# [[Unidad 4 - Control convencional|Siguiente: Unidad 4 - Control convencional ➡️]]

----