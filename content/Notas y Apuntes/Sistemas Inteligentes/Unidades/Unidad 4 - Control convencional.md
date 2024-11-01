---
Fecha: 2024-09-24
Tipo: Notas
cssclasses:
  - justify.css
  - calllouts.css
aliases:
  - Sist.Inteligentes Control convencional
---
-----
## Modelo matemático
Simplicidad contra precisión (ecuación diferencial)
## Sistema lineal
Cumple con el ==principio de superposición==
## Sistemas invariantes
Describen mediante ecuaciones diferenciales lineales (coeficientes constantes) ➡️ Debe ser invariante en el tiempo.

## Función de transferencia
La función de transferencia de un sistema descrito mediante una ecuación diferencial lineal e invariante en el tiempo se define como el cociente entre la transformada de Laplace de la salida (función de respuesta) y la transformada de Laplace de la entrada (función de excitación) bajo la suposición de que todas las condiciones iniciales son cero.

$$
a_0 y+a_1y+ ... + a_{n-1} y + a_ny = b_1x+...+b_{m-1}x + b_mx
$$

$$
n \geq m
$$

$$
G(s) = \frac{\mathcal{L}[salida]}{\mathcal{L}[Entrada]}
$$

$$
G(s) = \frac{b_0s^m + b_1a^{m-1}+...+b_{m-1}a+b_m}
{a_0s^n + a_1s^{n-1}+...+a_{n-1}s+a_n}
$$

## Diagrama de bloques

Es una representación gráfica de las funciones que lleva a cabo cada componente del sistema y el flujo de las señales.

![[funcionTransferencia.png]]

![[diagramaBloques.png]]

![[diagramaBloques2.png]]

![[diagramaBloques3.png]]

----
>[!example] Ejemplo Circuito RLC serie

![[RLC-1.png]]

![[RLC-2.png]]

![[RLC-3.png]]

![[RLC-4.png]]


----
## Análisis de respuesta
Señales de prueba típicas para realizar análisis matemáticos y experimentales de sistemas:
1. Escalón
2. Rampa
3. Parábola
4. Impulso

La respuesta en el tiempo de un sistema de control consta de dos partes: la respuesta transitoria y la respuesta en estado estacionario.

La respuesta transitoria se refiere a la que va del estado inicial al estado final. Por respuesta en estado estacionario se entiende la manera como se comporta la salida del sistema conforme t tiende a infinito.

$$c( t ) = c_{tr} + c_{ss} (t )$$

Un sistema de control está en equilibrio si, en ausencia de cualquier perturbación o entrada, la salida permanece en el mismo estado. 

Un sistema de control lineal e invariante con el tiempo es estable si la salida termina por regresar a su estado de equilibrio cuando el sistema está sujeto a una condición inicial. 

Un sistema de control ==lineal e invariante con el tiempo== es críticamente estable si las oscilaciones de la salida continúan de forma indefinida. 

Es inestable si la salida diverge sin límite a partir de su estado de equilibrio cuando el sistema está sujeto a una condición inicial.

>[!example] Ejemplo - Sistemas de primer orden

Si $E(s)$ es un escalón

![[SistemasPrimerOrden.png]]

![[SistemasPrimerOrden2.png]]

![[SistemasPrimerOrden3.png]]

----
>[!example] Ejemplo - Sistemas de segundo orden

![[SistemasSegundoOrden1.png]]

![[SistemasSegundoOrden2.png]]

----
## Análisis de respuesta: Sistemas de orden superior
La respuesta de sistemas de orden superior es igual a la suma de las respuestas de sistemas de primer orden y segundo orden

![[diagramaBloques3.png]]

----
## Estabilidad

Polos: Raíces del polinomio del denominador de la función de transferencia
Ceros: Raíces del polinomio del numerador de la función de transferencia

### Inestabilidad
La estabilidad de un sistema lineal en lazo cerrado se determina a partir de la ubicación de los polos en lazo cerrado en el plano **s**. Si alguno de los polos se encuentra en el semiplano derecho del plano **s**, entonces conforme aumenta el tiempo, producirá de forma monótona u oscilará con una amplitud creciente. Esto representa un sistema inestable.

### Estabilidad
Si todos los polos en lazo cerrado se encuentran a la izquierda del eje $jw$, cualquier respuesta transitoria termina por alcanzar el equilibrio. Esto representa un sistema estable.

----
## Acción del control integral
En el control proporcional de una planta, cuya función de transferencia no posee un integrador 1/s, hay un error en estado estacionario, o desplazamiento (offset), en la respuesta para una entrada escalón. Tal offset se elimina si se incluye la acción de control integral en el controlador.

![[controlIntegral.png]]

![[controlIntegral-2.png]]

---
## Acción del control derivativo
Cuando una acción de control derivativa se agrega a un controlador proporcional, aporta un modo de obtener un controlador con alta sensibilidad. Una ventaja de usar una acción de control derivativa es que responde a la velocidad del cambio del error y produce una corrección significativa antes de que la magnitud del error se vuelva demasiado grande. Por lo tanto, el control derivativo prevé el error, inicia una acción correctiva oportuna y tiende a aumentar la estabilidad del sistema.

![[controlDerivativo.png]]

![[controlDerivativo-2.png]]

----
## Acción del control proporcional

![[controlProporcional.png]]

![[controlProporcional-2.png]]

----
## Control PID

![[controlPID.png]]

El proceso de seleccionar los parámetros del controlador que cumplan con las especificaciones de comportamiento dadas se conoce como sintonía del controlador.

Ziegler y Nichols sugirieron reglas para sintonizar los controladores PID (esto significa dar valores a $Kp$, $Ti$ y $Td$) basándose en las respuestas escalón experimentales o en el valor de $Kp$ que produce estabilidad marginal cuando sólo se usa la acción de control proporcional.

>[!grafica-blck] Control PID - Método experimental

| Tipo de controlador | $Kp$      | $Ti$    | $Td$    |
| ------------------- | --------- | ------- | ------- |
| P                   | $T/L$     | ∞       | $0$     |
| PI                  | $0.9 T/L$ | $L/0.3$ | $0$     |
| PID                 | $1.2 T/L$ | $2L$    | $0.5 L$ |
>[!grafica-blck] Control PID - Método analítico

| Tipo de controlador | $Kp$          | $Ti$          | $Td$         |
| ------------------- | ------------- | ------------- | ------------ |
| P                   | $0.5K_{cr}$   | ∞             | $0$          |
| PI                  | $0.45 K_{cr}$ | $1/1.2 P{cr}$ | $0$          |
| PID                 | $0.6K_{cr}$   | $0.5P{cr}$    | $0.125P{cr}$ |

----
>[!tip] # 📺 Video - Sistemas de control

![Respuesta en el Tiempo | Sistemas de Control 1](https://www.youtube.com/watch?v=MXsroKE7zGU)

