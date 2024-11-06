---
title: Unidad 5 - Redes Neuronales
draft: true
tags:
---

----
>[!example] Ejercicio
>Colocar 5 características que tu consideres para comprar un auto y ponerle una ponderación de importancia. La suma de esos factores debe ser 1
## Criterios para comprar un auto 🚗

| Característica           | Ponderación |
| ------------------------ | ----------- |
| Precio (barato)          | 0.4         |
| Facilidad de refacciones | 0.3         |
| Modelo                   | 0.1         |
| Eficiencia               | 0.15        |
| Marca                    | 0.05        |
Elegir una calificación mínima que personalmente consideres para adquirirlo.

## Calificación minima ➡️ 8

Comparar entre estos dos autos siguiendo la ponderación que estableciste.

| x                        | Ponderación | Versa | Mustang |
| ------------------------ | ----------- | ----- | ------- |
| Precio (barato)          | 0.4         | 1     | 0       |
| Facilidad de refacciones | 0.3         | 1     | 0       |
| Modelo                   | 0.1         | 0     | 1       |
| Eficiencia               | 0.15        | 1     | 0       |
| Marca                    | 0.05        | 1     | 1       |
| **Total**                |             | 9     | 1.5     |

----
# Redes neuronales
## Definición

>[!book-blck] ## Red neuronal
>Una Red de Neuronas Artificial podría definirse como un grafo cuyos nodos están constituidos por unidades de proceso idénticas, y que propagan información a través de los arcos.
>
>En este grafo se distinguen tres tipos de nodos: los de entrada, los de salida y los intermedios.

## Fórmula
$$
E = X^TW
$$

>La salida es igual a la transpuesta de la matriz de entradas multiplicando la matriz del peso

Las señales E son procesadas además por una función llamada función de activación o de salida 𝓕, que produce la señal de salida de la neurona S. Dependiendo de la función 𝓕, habrá, distintos modelos de autómatas; por ejemplo:

- Lineal: S = KE con K constante.
- Umbral: S = 1 si E >= 𝜃, S = 0 si E < 𝜃; siendo 𝜃 el umbral constante.
- Cualquier función: S = 𝓕(I), siendo 𝓕 una función cualquiera.

>𝓕  = Función de activación

-----
## Célula McCulloch-Pitts

Diapositiva 151

## Definición - Red neuronal

>[!book-blck] Red Neuronal
>Una red neuronal es una colección de neuronas de McCulloch y Pitts, todas con las mismas escalas de tiempos, donde sus salidas están conectadas a las entradas de otras neuronas.

Una red neuronal de células de McCulloch-Pitts tiene la capacidad de computación universal. 
Es decir, cualquier estructura que pueda ser programada en una computadora, puede ser modelada mediante una red de células de McCulloch-Pitts.

>[!example] Ejercicio
>Comprobar AND


| Entrada (X) | Peso(w) | ∑Xw                      | Umbral | Salida (S) |
| ----------- | ------- | ------------------------ | ------ | ---------- |
| 0,0         | 1       | (0)(1) = 0<br>(0)(1) = 0 | 1      | 0          |
| 0,1         | 1       | (0)(1) = 0<br>(1)(1) = 1 | 1      | 0          |
| 1,0         | 1       | ()                       | 1      | 0          |
| 1,1         | 1       | (1)(1) = 1<br>(1)(1) = 1 | 1      | 1          |

------
## Perceptrón

El modelo se concibió como un sistema capaz de realizar tareas de clasificación de forma automática. 
La idea es disponer de un sistema que, a partir de un conjunto de ejemplos de clases diferentes (patrones), fuera capaz de determinar las ecuaciones de las superficies que hacían de frontera de dichas clases. 

La arquitectura de la **==red==** es  de una estructura ==**monocapa**==, en la que hay **un conjunto de células de entrada**, tantas como sea necesario, según los términos del problema; y **una o varias células de salida**. Cada una de las células de entrada tiene conexiones con todas las células de salida, y son estas conexiones las que determinan las superficies de discriminación del sistema.

$$
𝑦^′=∑(𝑖=1)^𝑛  𝑥_𝑖 𝑤_𝑖 
$$

$$
y=F(y^′,Θ)
$$


----
## Entrenamiento supervisado

>Ejemplo con compuerta AND

Y = valor esperado

| X1     | X2     | Y      |
| ------ | ------ | ------ |
| ==-1== | ==-1== | ==-1== |
| ==-1== | ==1==  | ==-1== |
| 1      | -1     | -1     |
| 1      | 1      | 1      |
W1  = 6
W2 = 8
Θ = 2

∆W1 = 1
∆W2 = -1
∆Θ = -1

W1 = 7
W2 = 7
Θ = 1

| Renglon | Formula    | Salida | 𝓕 = 1 si y>0<br>𝓕 = -1 caso contrario | Esperado<br>𝑑(𝜒) |
| ------- | ---------- | ------ | --------------------------------------- | ------------------ |
| 1       | -7 + -7 +1 | -13    | -1                                      | -1                 |
| 2       | -7 + 7+ 1  | 1      | 1                                       | -1                 |
| 3       |            |        |                                         | -1                 |
| 4       |            |        |                                         | 1                  |

∆W1 = 1
∆W2 = -1
∆Θ = -1

W1 = 8
W2 = -6
Θ = 0

| X1  | X2  | Y   |
| --- | --- | --- |
| -1  | -1  | -1  |
| -1  | 1   | -1  |
| 1   | -1  | -1  |
| 1   | 1   | 1   |

| Renglon | Formula (X1 x W1 + X2 x W2 + Θ) | Salida | 𝓕 = 1 si y>0<br>𝓕 = -1 caso contrario | Esperado<br>𝑑(𝜒) |
| ------- | ------------------------------- | ------ | --------------------------------------- | ------------------ |
| 1       | -8+6                            | -2     | -1                                      | -1                 |
| 2       |                                 |        |                                         | -1                 |
| 3       |                                 |        |                                         | -1                 |
| 4       |                                 |        |                                         | 1                  |

### Pasos a seguir

1. Empezar con valores aleatorios para los pesos y el umbral.
2. Seleccionar un vector de entrada 𝜒 del conjunto de ejemplos de entrenamiento.
3. Si 𝑦≠𝑑(𝜒), la red da una respuesta incorrecta. Modificar $𝑤_𝑖$ de acuerdo con:

$$∆𝑤_𝑖=𝑑(𝜒) 𝑥_𝑖$$

4. Si no se ha cumplido el criterio de finalización, volver a 2.

----
# ADALINE

ADALINE: Adaptive Linear Neuron.
Su estructura es casi idéntica a la del PERCEPTRON.

En este modelo se toman en cuenta el error existente entre la salida obtenida y la salida esperada  $|𝑑^𝑝−𝑦^𝑝 |$ .

A este regla de aprendizaje se le conoce como regla Delta.
Normalmente utilizamos el error cuadrático medio:
(Diapositiva 159)

Dado que necesitamos minimizar el error es decir $∆_𝑝 𝑤_𝑗$ tendremos que hacer uso del calculo diferencial para encontrar ese mínimo.

$$
∆_p w_j=-γ \frac{(∂E^p)}{(∂w_j )}
$$

$$
∆_p w_j=γ(d^p-y^p ) x_j
$$

### Procedimiento de Aprendizaje

1. Iniciar con pesos aleatorios.
2. Introducir un patrón de entrada.
3. Calcular $y^p$, compararla con $d^p$ y obtener su diferencia.
4. Para todos los w encontrar $∆w$ y ponderarla por la tasa de aprendizaje $𝛾$.
5. Modificar los pesos con los deltas obtenidos en el paso 4.
6. Si no se cumple con el criterio de convergencia regresar a 2.


-----
# Machine Learning

Debemos tener datos de
- Entrenamiento
- Validación

![[MachineLearning-IdeaPrincipal.png]]


----
# Numpy

Arreglos
Matrices
Agregar elementos (append) 
Eje 0 → Renglones
Eje 1 → Columnas

>Considerando `numpy` con alias `np`

Insertar elementos en un arreglo

```python
nombre_arreglo = np.insert(nombre_arreglo, posicion, elemento)
```

Buscar información dentro un arreglo en Numpy
Función `where`

```Python
mayores0 = np.where(miArreglo2>0)
```

Operaciones vectoriales con arreglos de Numpy
Afectan a todos los elementos del arreglo

```python
miVector+=1
```

Desviación 

```Python
desviacion = miVector.std()
```


----
# 🐼Pandas

Importar pandas y cargar archivo CSV

```Python
import pandas as pd
datos = pd.read_csv("Ruta_CSV")
print datos
```

Para convertir de CSV a arreglo de Numpy

```Python
datosNumpy = np.array(datos.values)
```

## Filtros

Imprimir fechas con temperatura promedio mayor a 20 ℃

```Python
filtro = fechas [tempProm>20]
```

Transpuesta

```Python
totalDatos = totalDatos.transpose()
```

## Data frame

```
pd.Series
```

>Nos quedamos en introducción de pandas 1

Se puede recorrer con un for

Para acceder al dato por un "apuntador" se usa la función `iloc[<indice>]`
>Ejemplo
>`nombreArreglo.iloc[0]`

Para cambiar el tipo de datos, se puede usar la función `dtype`

Para ordenar los datos, se usa la función `sort`

Medidas de tendencia central (media mediana y moda)

Media ➡️ `.mean()`
Mediana ➡️ `.median()`
Moda ➡️ `.mode()`

Una matriz, se pueden hacer dos arreglos (uno de filas y uno de columnas)

```Python
indices = ["Renglon1","Renglon2","Renglon3"]
columnas = ["Columna1","Columna2","Columna3"]

datos = [[],[],[],[],[],[],[],[],[]]

```

También se puede poner con un diccionario 

`.head()` ➡️ nos pone los primeros 5 renglones
`.tail()` ➡️ nos pone los últimos 5

Para insertar un renglón ➡️

```python
pd.Series(name="", data=<datos>, index =["Columna1","Columna2","Columna3"] )
```

---
# Problemas de Clasificación
## Descenso del gradiente

>[!swords] Ejemplo IBM
>[¿Qué es el descenso del gradiente? | IBM](https://www.ibm.com/mx-es/topics/gradient-descent)

Este método busca los mejores pesos y sesgos que minimizan la pérdida, y elimina los valores atípicos del conjunto de datos. 
El objetivo del descenso de gradiente es reducir el error o la función de costo de un modelo, al realizar pruebas con una variable de entrada y el resultado esperado.

### Descenso del gradiente por lotes  

El descenso del gradiente por lotes suma el error de cada punto en un conjunto de entrenamiento, actualizando el modelo solo después de que se hayan evaluado todos los ejemplos de entrenamiento. Este proceso se conoce como época de entrenamiento.

Si bien este procesamiento por lotes proporciona eficiencia de cálculo, aún puede requerir un tiempo de procesamiento prolongado para grandes conjuntos de datos de entrenamiento, ya que aún necesita almacenar todos los datos en la memoria. El descenso del gradiente por lotes también suele producir un gradiente de error estable y una convergencia, pero a veces ese punto de convergencia no es el más ideal, ya que encuentra el mínimo local frente al global.

### Descenso del gradiente estocástico  

El descenso  del gradiente estocástico (SGD, sigla en inglés de stochastic gradient descent) ejecuta una época de entrenamiento para cada ejemplo dentro del conjunto de datos y actualiza los parámetros de cada ejemplo de entrenamiento uno a la vez. Dado que solo es necesario tener un ejemplo de entrenamiento, son más fáciles de almacenar en la memoria. Si bien estas actualizaciones frecuentes pueden ofrecer más detalles y velocidad, pueden generar pérdidas en la eficiencia computacional en comparación con el descenso del  gradiente por lotes. Sus actualizaciones frecuentes pueden generar gradientes ruidosos, pero esto también puede ser útil para escapar del mínimo local y encontrar el global.

### Descenso del gradiente por mini lotes  

 El descenso del gradiente por mini lotes combina conceptos tanto del descenso del gradiente por lotes como del descenso del gradiente estocástico. Divide el conjunto de datos de entrenamiento en lotes pequeños y realiza actualizaciones en cada uno de esos lotes. Este enfoque logra un equilibrio entre la eficiencia computacional del descenso del gradiente por lotes y la velocidad del descenso del gradiente estocástico.

>[!example] Ejemplo MNNIST
>[El dataset MNIST | Interactive Chaos](https://interactivechaos.com/es/manual/tutorial-de-deep-learning/el-dataset-mnist)

Dataset: MNNIST

-----
## Máquinas de vector soporte (SVM)

>[!cpu-blck] Ejemplo SVM  → IBM
>[Funcionamiento de SVM - Documentación de IBM](https://www.ibm.com/docs/es/spss-modeler/saas?topic=models-how-svm-works)

Puede hacer
- Clasificaciones lineales
- Clasificaciones no lineales
- Regresiones
- Detección de valores atípicos

>[!caution] Se tienen que escalar y normalizar los datos

### Tipos
#### Clasificadores de margen duro
Cuando forzamos al modelo para que todos los datos de entrenamiento quedan fuera del vector soporte
>Ejemplo una calle muy angosta

#### Clasificadores de margen blando
Cuando el margen entre los vectores de soporte es buen aunque algunos datos de entrenamiento caigan en el
>Ejemplo, una avenida más ancha 

### Hiperparametros de un SVM

C: distancia entre los vectores de soporte
- Un valor bajo de C nos da una distancia grande
- Un valor alto de C nos dará una baja distancia

----
## Pasos para crear un Modelo SVM

1. Obtener datos y clase de entrenamiento
2. Escalar los datos de entrenamiento 
	1. Normalmente se usa la función ==StandardScaler==
3. Crear el modelo linear SVC
4. Entrenar el modelo con los datos y las clases de entrenamiento
5. Realizar predicciones con el modelo entrenado.

### StandardScaler
Normaliza todos los datos
- Establece la media en 0
- Establece la desviación estándar en 1

>[!book-blck] Ejemplo
>[LinearSVC — scikit-learn 1.5.2 documentation](https://scikit-learn.org/stable/modules/generated/sklearn.svm.LinearSVC.html)

Nos quedamos en la Diapositiva del SVM del iris (graficación del SVM )

----
## SVM como clasificadores no lineales

Para hacer esto podemos usar un transformador `PolynomialFeatures`; posteriormente se realiza 

Ejemplo:

```Python
polynomial=Pipelenie([("poly_features",PolynomialFeatures(degree=3))
("scaler",StandardScaler()),
("svm_clf",LinearSVC(C-10,loss="hinge"))
])
```

Otra forma de manejar características polinomiales es modificar el kernel del modelo de lineal a polinomial

```Python
poly_kernel_svm=Pipeline([
("scaler",StandardScaler()),
("svm_clf",SVC(kernel="poly",degree=3,coef0=1,C=5))
])
poly_kernel_svm.fit(x,y)
```

Kernel de función de base radial gaussiana

```Python
rbf_kernel_svm_clf=Pipeline([
("scaler",StandardScaler()),

])
```

----
## Regresiones con SVM

Este modelo soporta regresiones lineales y no lineales
En los modelos de regresión la idea es que la mayoría de los datos de entrenamiento queden localizados entre los dos vectores de soporte.
La distancia entres los vectores de soporte esta dada por un hiperparametro llamado ɛ (epsilon)

----

>DataSet de Obesidad
>[Obesity Dataset](https://www.kaggle.com/datasets/suleymansulak/obesity-dataset)


-----
# Árboles de decisión

Son un modelo de ML en donde podemos:
- Clasificación
- Regresión

Son el componente básico de los bosques aleatorios
No requieren escalado ni centrado de datos

Scikit-Learn utiliza el algoritmo `CART` para generar los árboles, por lo que estos solo pueden ser árboles binarios.

## Algoritmos
### Impureza de GINI
Un nodo es puro si gini = 0; es decir, si todas las instancias de entrenamiento de ese nodo pertenecen a la misma clase

>Por default es el algoritmo que se utiliza
### Entropía
La entropía de un nodo es 0 cuando se contienen instancias de una sola clase.

>[!example] Ejemplo
>Se usa el dataset iris

```Python
from sklearn.datasets import load_iris
from sklearn.tree import DecissionTreeClassifier

iris = load_iris()
```

Para calcular las probabilidades de que una instancia pertenezca a una clase en concreto se usa el siguiente comando:

```Python
tree_clf.predict_proba([[5,1.5]])
```

---
## Algoritmo CART (Classification and Regression Tree)

- Divide el conjunto de entrenamiento en dos subconjuntos mediante una sola característica K y un umbral $t_k$ 
- Selecciona los parámetros $k$ y $t_k$ que produzcan los conjuntos más puros
- El algoritmo trabaja de manera ==recursiva== hasta completar la profundidad con la que fue configurado el modelo.
- Este algoritmo da una solución razonablemente buena pero ==**no asegura que sea óptima**== 
- La velocidad para realizar predicciones es buena ya que solo se tiene que recorre el árbol, el cual generalmente está balanceado.

Los árboles de decision, por naturaleza tienden a sobre-ajustar los datos (*overfitting*)

### Hiper-parámetros
- Max depth: profundidad del árbol
- Min samples split número de mínimo de muestras que debe de tener el árbol
- Min samples leaf: número máximo de muestras de un nodo terminal
- Max leaf nodes: numero máximo de nodos terminales
- Max features: número máximo de características a evaluar para dividir un nodo

----
## Regresión con árboles de decisión
Se usa la clase `DecissionTreeRegressor`

- El valor de la predicción es el valor medio de todas las instancias de ese nodo
- El nodo terminal también nos arroja el erro cuadrático medio.
- En el caso de la regresión, el algoritmo CART no intenta minimizar la impureza; sino lo que intenta minimizar es el ECM (error cuadrático medio)

>[!caution] NO es recomendable dejarlo sin restricciones, se recomienda poner un número máximo de hojas

-----
# 🌲🎲 Bosques aleatorios (Random Forest)

- Utilizan el concepto de "sabiduría colectiva"
- Usan algoritmos de ensamblaje.
	- Se utilizará más de un modelo «un grupo de modelos»
- Un grupo de predictores se denomina ensamble.
- Al ensamble de árboles de decisión le llamamos Random Forest.

- Logistic Regression
- SVM Classifier
- Random Forest classifier
- Other

>Un bosque aleatorio es un ensamble de puros arboles de decisión
## 🗳️ 🔨 Voto duro

```mermaid
graph TD
    subgraph Random Forest
        A[Árbol 1] --> Clase_A
        B[Árbol 2] --> Clase_B
        C[Árbol 3] --> Clase_A
        D[Árbol 4] --> Clase_A
        E[Árbol 5] --> Clase_B
    end
    
    subgraph Voto Duro
        Clase_A[Clase A] -- Mayoría de votos --> Predicción_Final
        Clase_B[Clase B] -- Minoría de votos --> Predicción_Final
    end

```

>[!tldr] Ejemplo voto duro

```Python
from sklearn.ensemble import RandomForestClassifier
from sklearn.ensemble import VotingClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.svm import SVC

log_clf = LogisticRegression()
rnd_clf = RandomForestClassifier()
svm_clf = SVC()
voting_clf = VotingClassifier()
estimators = [(lr,log_clf),('rf',rnd_clf),('svc',svm_clf)] , voting = 'hadrd'
voting_clf.fit(X_train, y_train)
```

>[!tldr] Evaluación de modelos

```Python
from sklear.metrics import acuracy_score
for clf in (log_clf,rnd_clf,svm_clf,voting_clf):
	clf.fit(X_train,y_train)
	y_pred = clf.predict(X_test)
	print(clf._class_._name_._,acuracy_score(y_test,y_pred))
```

## 🗳️🪶 Voto suave (Soft Voting)

>[!quote] Definición
>Es cuando la predicción se realiza con la probabilidad más alta promedio de los clasificadores (`predict_proba()`).

>Para poder usar soft voting, tenemos que hacer que el parámetro voting sea igual a soft: `voting = 'soft'`

```Python
from sklearn.ensemble import RandomForestClassifier
from sklearn.ensemble import VotingClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.svm import SVC

log_clf = LogisticRegression()
rnd_clf = RandomForestClassifier()
svm_clf = SVC()
voting_clf = VotingClassifier()
estimators = [(lr,log_clf),('rf',rnd_clf),('svc',svm_clf)] , voting = 'soft'
voting_clf.fit(X_train, y_train)
```

## Bagging y pasting

Otro método para obtener un conjunto de clasificadores es el de usar el mismo algoritmo de entrenamiento con subconjuntos aleatorios distintos.

Cuando el muestreo es con reemplazo, el método se llama *bagging*, en caso contrario se llama *pasting*.

### Bagging

```mermaid
graph TD
    A[Conjunto de datos original] --> B[Muestreo con reemplazo]
    B --> C[Modelo 1]
    B --> D[Modelo 2]
    B --> E[Modelo 3]
    B --> F[Modelo n]
    C --> G[Predicciones]
    D --> G
    E --> G
    F --> G
    G --> H[Votación/Promedio]
    H --> I[Predicción final]
```

### Pasting

```mermaid
graph TD
    A[Conjunto de datos original] --> B[División en subconjuntos]
    B --> C[Modelo 1]
    B --> D[Modelo 2]
    B --> E[Modelo 3]
    B --> F[Modelo n]
    C --> G[Predicciones]
    D --> G
    E --> G
    F --> G
    G --> H[Concatenación]
    H --> I[Predicción final]
```


>[!info]
>Scikit Learn puede hacer bagging y pasting usando las siguientes clases:
>- `BaggingClassifier`
>- `BaggingRegressor`
>- Para diferenciar entre bagging y pasting se tiene que establecer `bootstrap = True` para bagging y `bootstrap = False` para pasting

>[!tldr] Ejemplo bagging

```Python
from sklearn.ensemble import BaggingClassifier
from sklearn.tree import DecissionTreeClassifier
bag_clf = BaggingClassifier(DecissionTreeClassifier(),n_estimators = 500, max_samples = 100, bootstrap = True, n_jobs = -1)
bag_clf.fit(X_train,y_train)
y_pred = bag_clf.predict(X_test)
```

>[!warning] NOTA Si el clasificador tiene un método `predict_proba()` se realiza por default un soft voting

> [!info]
>En Bagging:
>- Algunas instancias se pueden muestrear varias veces para los entrenamientos de los clasificadores.
>- Algunas otras instancias pueden no muestrearse nunca, a estas instancias la llamamos *out-of-bag* `oob`
>- Podemos utilizar estas `oob` como conjunto de prueba, esto lo hacemos haciendo `oob_score = True`

>[!example] Ejemplo

```Python
bag_clf = BaggingClassifier(DecisionTreeClassifier(),n_estimators=500, bootstrap=True, n_jobs-1, oob_score = True)
bag_clf.fit(X_train,y_train)
bag_clf.oob_score_

from sklearn.metrics import accuracy_score
y_pred = bag_clf.predict (X_test)
accuracy_score (y_test,y_pred)
```

>[!warning] NOTA - Este modelo realiza una validación en automático con el conjunto `oob`

### `BaggingClassifier`

- Soporta el submuestreo de características.
- Los hiper-parámetros `max_features` y `Bootstrap_features` controlan esta característica.

>[!example] Ejemplo - generando Bosque Aleatorio

```Python
from sklearn.ensemble import RandomForestClassifier
rnd_clf = RandomForestClassifier(n_estimators=500,max_leaf_nodes=16,n_jobs=1)
rnd_clf.fit(X_train,y_train)
y_pred_rf = rnd_clf.predict(X_test)
```

>[!warning] NOTA
>Un `RandomForestClassifier` cuenta con todos los hiper-parámetros de un `DecissionTreeClassifier` además de todos los hiper-parámetros de un `BaggingClassifier`

