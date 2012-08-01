Ejercicio de programación IV: Estructuras de Control
========================================================

### [IMSER 2012]

Archivos incluidos
-------------------
El [archivo](http://eva.universidad.edu.uy/file.php/1454/ejercicios_de_programacion/ejercicio4.zip) con los ejercicios del práctico debe bajarse y descomprimirse en disco duro, creando la carpeta ejercicio4. Usted deberá abrir el RStudio y seleccionar dicha carpeta como su directorio de trabajo (con el menú **Tools > Set Working Directory > Choose Directory...** o la combinación **Ctrl + Shift + K**). En esta carpeta se encuentran algunos archivos que usted deberá modificar:
* **` fibonacci.R `**
* **` funcion-fibonacci.R `**

Adicionalmente los siguientes archivos son necesarios, pero **no deben ser cambiados**.
* **` evaluar.R `**
* **` notas.csv `**
* **` datos `**

Lo primero que debe hacer es ejecutar el siguiente comando para cargar las funciones de corrección:

```
source("enviar.R")
```
Si usted ha ejecutado todos los pasos anteriores correctamente, la siguiente frase debería verse en la consola:

```

 Código fuente cargado correctamente

```

En caso de que ocurra un error o se vea otro mensaje en la consola, verifique que los archivos se descomprimieron correctamente y que usted está trabajando en la carpeta correspondiente con el comando `getwd()`.

Usted trabajará modificando los contenidos de dichos archivos con RStudio (u otro programa de su preferencia) según las consignas que se describen a continuación. Luego de terminar uno o varios de los ejercicios deberá ejecutar el comando:

```
evaluar()
```

********

Ejercicio 1: secuencia de Fibonacci
-------------------

Ideada por el matemático italiano [Fibonacci](https://es.wikipedia.org/wiki/Fibonacci), la serie homónima se trata de una secuencia de números creada con una regla muy simple. Se trata simplemente de sumar los dos números anteriores para generar el siguiente, comenzando por el 0 y el 1. Así el tercer número es 1 = 1 + 0, el cuarto número es 2 = 1 + 1, el quinto número es 3 = 2 + 1, etc. Matemáticamente se puede describir como una secuencia $S$ que sigue la siguiente ecuación:

$$
  S_i = S_{i - 1} + S_{i - 2}
$$

y agregando la condición de que los valores iniciales $S_0$ y $S_1$ equivalen a 1. Así los primeros 10 números de la secuencia de Fibonacci son: 0, 1, 1, 2, 3, 5, 8, 13, 21 y 34.

### 1a. Calcular los valores del $S_0$ al $S_{20}$.

En este ejercicio usted deberá trabajar modificando el archivo `fibonacci.R`. En el mismo usted encontrará que el vector `fibo` es el designado para guardar los primeros 20 elementos de la secuencia. Para lograr hacer esta secuencia usted tendrá que crear un loop del tipo `for` con el número correcto de iteraciones. No olvide considerar que los primeros dos elementos de la secuencia ya están agregados al vector `fibo` a la hora de determinar el número de iteraciones así como los valores de `i` inicial e `i` final.

Puede comprobar que su resultado es correcto comparando la siguiente imagen, generada con los comandos:




```r
i <- 0:19
plot(fibo ~ i, main = "Secuencia de Fibonacci", ylab = expression(S[i]), xlab = "i")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 


### 1b. Crear una función genérica

En esta parte del ejercicio usted trabajará modificando el archivo `funcion-fibonacci.R`. El objetivo de este archivo es crear una función que calcule la secuencia de Fibonacci para una cantidad de números arbitraria. Tome en cuenta que el código es casi idéntico al contenido en el archivo `fibonacci.R`, pero debe ser modificado estratégicamente para que el argumento `n` modifique el resultado final.

Si usted ha modificado correctamente el archivo `funcion-fibonacci.R` entonces el siguiente comando debería devolver el resultado que se muestra aquí:



```r
funcionFibonacci(13)
```

```
##  [1]   0   1   1   2   3   5   8  13  21  34  55  89 144
```

