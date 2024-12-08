# Programación de Computadores - UNAL

# Tabla de Contenido

- [Programación de Computadores - UNAL](#programación-de-computadores---unal)
- [Bucles 2](#bucles-2)
   - [Ciclo for](#ciclo-for)
   - [Listas](#listas)
   - [Operador de pertenencia (membership)](#operador-de-pertenencia-membership)
   - [Colección Rango (range)](#colección-rango-range)
   - [Colecciones de rango y ciclos for](#colecciones-de-rango-y-ciclos-for)
- [Reto 7](#reto-7)

## Bucles 2

### Ciclo for
Un ciclo *para* (`for`) puede ser usado (y en Python es su principal uso) para obtener uno a uno los elementos de una colección de elementos y poder realizar con cada uno de ellos el mismo bloque de operaciones.

Un esquema textual que en Python representa dicho ciclo para (for) es:

```python
<bloque_prev>
# Forma pythonic del ciclo for
for <elemento> in <coleccion>:
	<bloque>
<bloque_sigui>
```

 + El fragmento \<bloque_prev\> es el bloque de instrucciones previas que han sido ejecutadas antes del ciclo.
 + El fragmento \<elemento\> es la variable que se usa para ir recorriendo (iterando) sobre los elementos de la colección (tomará como valor cada uno de ellos en cada iteración).
 + El fragmento \<coleccion\> es la colección de elementos que será recorrida (iterada) con el ciclo.
 + El fragmento \<bloque\> es el bloque de instrucciones principal del ciclo que se ejecuta con cada uno de los elementos de la colección. 
 + El fragmento \<bloque_sigui\> es el bloque de instrucciones que se ejecutan después de terminar de ejecutar el ciclo.

<table cellspacing="1" bgcolor="">
	<tr bgcolor="#252582">
		<th><b>Definición</b></th>
	</tr>
	<tr bgcolor="#e4e4ed">
		<td style="color:#141414">El ciclo para (for) se puede leer en español como: <i>Para cada elemento en la colección realice las instrucciones en el bloque</i>.</td>
	</tr>
</table>

### Listas*

Una *lista* es un tipo de dato en Python que permite almacenar una colección de *objetos* (variables - de momento) a los que se puede acceder a través de un índice.

**Disclaimer:** Las listas de verán en profundidad en la sección de arreglos y matrices.

**Ejemplo 1:**
```python
frutas = ["Tomate de arbol", "Maracuya", "Guayaba"] # Lista con tres cadenas
```

### Operador de pertenencia (*membership*)
La palabra reservada *in* permite validar si un elemento hacer parte de una colección.

**Ejemplo 2:**
```python
frutas = ["Tomate de arbol", "Maracuya", "Guayaba"] 
print("Maracuya" in frutas) 
print("Fresa" in frutas) 
```

**Ejemplo 3:** Dada la lista de frutas imprimir todas.
```python
frutas = ["Tomate de arbol", "Maracuya", "Guayaba"] 
for f in frutas: # para cada elemento f en la lista de frutas
  print(f)
```

Alternativamente usando un ciclo *while* es necesario conocer la cantidad de elementos de la lista e ir accediendo a cada uno.

```python
frutas = ["Tomate de arbol", "Maracuya", "Guayaba"] 
i : int = 0
while i < len(frutas):
  print(frutas[i])
  i += 1
```

**Ejemplo 4:** Dada la lista de frutas imprimir sus elementos hasta encontrar la fruta "Guayaba".
```python
frutas = ["Pera", "Maracuya", "Guayaba", "Lulo", "Granadilla"]
for f in frutas: # para cada elemento f en la lista de frutas
  print(f)
  if f == "Guayaba": break # Termina el ciclo
```

### Colección Rango - `range`
Existen varias colecciones que se pueden iterar en Python, una de ellas es la colección Rango (range). 

Una colección Rango (range) es una colección de números en un intervalo (rango) semi-abierto, definido por valor inicial (el lado cerrado del intervalo), un valor final (que no se incluye en el rango, es decir el lado abierto del intervalo), y un valor de incremento/decremento usado a partir del valor inicial para determinar que valores quedan en el rango. Si no se da el valor de inicio, éste se fija en cero (0) y si no se da valor de incremento/decremento, éste se fija en uno (1).

Puede verse como un intervalo definido de esta manera:

$$Intervalo: [a,b)$$

Formas de crear un rango:

 + *range(N)*: La colección de enteros 0, 1, 2, . . . , N − 1, ésta es la colección de enteros empezando en cero (0), y llegando hasta N − 1 (no incluye N) incrementando de uno en uno. Si N no es positivo genera el rango vac´ıo.

 + *range(C,F):* La colección de enteros C, C + 1, C + 2, . . . ,F − 1, ésta es la colección de enteros empezando en C, y llegando hasta F − 1 (no incluye F) incrementando de uno en uno. Si F ≤ C genera el rango vac´ıo.

 + *range(C,F,I):* La colección de enteros C, C + I, C + 2I, . . . , C + kI, hasta el k tal que C + (k + 1)I ≥ F si I > 0 o C + (k + 1)I ≤ F si I < 0. Esta es la colección de enteros empezando en C, y llegando hasta el más cercano C + kI a F (no incluye F) incrementando/decrementando de I en I. Dependiendo de los valores dados se puede generar el rango vac´ıo.

**Disclaimer:** C, F, I deben ser valores enteros.

**Ejemplo 5:** Uso de *range*.

```python
range(6) # genera la secuencia [0, 1, 2, 3, 4, 5]
for num in range(6): print(num)
```

```python
range(-7, 8) # [-7, -6, -5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5, 6, 7]
for num in range(-7, 8): print(num)
```

```python
range(11,20,2) # [11, 13, 15, 17, 19]
for num in range(11,20,2): print(num)
```

**Ejercicio:** Qué se genera con *range(-2)*?

### Colecciones de rango y ciclos for
Los rangos se combinan perfectamente con la instrucción para (for):

<table cellspacing="1" bgcolor="">
	<tr bgcolor="#252582">
		<th><b>Definición</b></th>
	</tr>
	<tr bgcolor="#e4e4ed">
		<td style="color:#141414">Se define una variable que se utilizará para recorrer cada número en el rango. En español se podr´ıa pensar como: <i>Para cada número i en el rango dado</i>.</td>
	</tr>
</table>

**Ejemplo 6:** 
```python
for i in range(-5, 6, 1): print(i)
```

```python
for i in range(10, 0, -1): print(i)
```

```python
for i in range(0, 55, 5): print(i)
```

**Ejemplo 7:** Programa para hacer la suma de los naturales hasta un *n* dado:

$$1 +2 +3 + \dots + (n-1)+ n \longrightarrow \sum_{i=1}^{n}i = \frac{n(n+1)}{2}$$

```python
n = int(input("Ingrese numero final: "))
suma : int = 0
for i in range(1, n+1):
  suma += i
print("La suma hasta " + str(n) + " es " + str(suma)) 
```

Alternativamente se puede usar un ciclo *while*:
```python
n = int(input("Ingrese numero final: "))
suma : int = 0
i : int = 1
while i <= n:
  suma += i
  i += 1
print("La suma hasta " + str(n) + " es " + str(suma)) 
```

## Reto 7
Desarrolle la mayoría de ejercicios en clase. Para cada punto cree un programa individual asimismo cree un notebook con la solución a todos los problemas. Al finalizar suba todo a un repo y subalo al canal reto_7 en slack.

**Nota:** Todo el código de aquí en adelante debe ir debidamente documentado.

1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.
2.  Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.
3.  Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
4. Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial
5. Calcular el valor de 2 elevado a la potencia n usando ciclos *for*.
6. Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for. **Disclaimer:** Trate de no utilizar el operador de potencia (**).
7. Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.
8. Diseñar una función que permita calcular una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Taylor. **Nota:** use *math* para traer la función exponencial y mostrar la diferencia entre el valor real y la aproximación.
$$e^x \approx exp(x,n) \approx \sum_{i=0}^{n}\frac{x^i}{i!}$$
9. Diseñar una función que permita calcular una aproximación de la función seno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. **Nota:** use *math* para traer la función seno y mostrar la diferencia entre el valor real y la aproximación.
$$sin(x) \approx sin(x,n) \approx \sum_{i=0}^{n} (-1)^i \frac{x^{2i+1}}{(2i+1)!}$$



