#Tablas

Las tablas son la forma de expresar información tabulada de manera
clara

El interior de una tabla se contiene dentro de un ambiente *tabular*

```
\begin{tabular}{ | r | r | }
  a & b\\
  a & b\\
\end{tabular}
```

Un ambiente tabular toma 1 argumento, que consiste en una cadena de
texto que indica cuantas columnas tiene la tabla, como se alinean, que
separación tienen...

En este caso:

```
\begin{tabular}{ | r | r | }
```

Indica 2 columnas, ambas alineadas a la derecha, con líneas en todas
las verticales en todas las columnas.

En caso de que deseáramos eliminar la linea sepuratoria entre las
columnas, podemos eliminar la barra vertical.

```
\begin{tabular}{ | r r | }
```

En caso de que deseáramos añadir una barra doble:

```
\begin{tabular}{ | r || r | }
```

Nótese como no hay espacio separador entre |.

De la misma forma es posible alinear cada columna como se desee:
+   **r**: Alineado a la derecha.
+   **l**: Alineado a la izquierda.
+   **c**: Centrado.
+   **p{''anchura''}**: columna párrafo (gran cantidad de texto) alineado arriba
+   **m{''anchura''}**: columna párrafo alineado centrado (requiere paquete array)
+   **b{''anchura''}**: columna párrafo alineado abajo (requiere paquete array)

Para separar las columnas en el texto se utiliza el carácter "&", para
finalizar una linea de la tabla el comando \\\\. Es importante notar
que si una linea contiene más columnas de las definidas en el
*tabular* el documento dará error de compilación, mientras que si
contiene menos simplemente quedarán cuadros vacíos.

Ninguno de los ejemplos dados contiene lineas horizontales, esto es
porque Latex fuerza a ponerlos explícitamente utilizando 2 posibles
comandos:
+ **\hline**: Linea horizontal que recorre toda la tabla
+ **\cline{i-j}**: Linea horizontal que comienza en la columna i y se
  extiende hasta la j (Ambos inclusive). En Latex las columnas se
  indexan por 1 (Es decir la primera columna es la 1)

#Multielementos

Una multicolumna es el resultado de unir varias columnas juntas dentro
de una fila, mientras que una multifila es el resultado de unir
varias filas juntas dentro de una columna.

La signatura de ambos comandos es:

```
\multicolumn{''numero''}{''alineamiento''}{''contenido''}
```
+  **numero**: Cuantas columnas se combinarán.
+  **alineamiento**: Como se alineará el nuevo cuadro creado al
   combinar. Usa la misma sintaxis que *tabular* (aunque solo se
   permite una columna) y esta permitido redefinir los bordes.
+  **contenido**: Texto del cuadro.

```
\multirow{''numero''}{''anchura''}{''contenido''}
```
+  **numero**: Cuantas filas se combinarán.
+  **anchura**: Anchura de la nueva columna. Generalmente se usa *\**,
   que indica el predeterminado.
+  **contenido**: Texto del cuadro.

\\multirow requiere el paquete multirow, por lo que se ha de incluir
\usepackage{multirow} en tu preámbulo.

Si se combinan columnas, no hay que poner todas las columnas, dado que
dará error de compilación.

Expliquémoslo mejor con un ejemplo:

```
1.\begin{tabular}{ | c | l | p{1cm} | r | }\cline{3-4}
2.  \multicolumn{2}{c|}{}            & \multicolumn{2}{|c|}{Predicho} \\ \cline{3-4}
3.  \multicolumn{2}{c|}{}            & Ham  & Spam \\ \hline
4.  \multirow{2}{*}{Objetivo} & Ham  & 1649 &    4 \\ \cline{2-4}
5.                            & Spam &    7 & 1709 \\ \hline
6.\end{tabular}
```

Se puede observar como en las líneas 2 y 3 se ha utilizado
*multicolumn*, por lo que no se incluyen todas las columnas. También
se ha usado el formateado de ambos comandos para sobre escribir la
configuración de la tabla y evitar que aparezcan lineas en la esquina
superior-izquierda. De la misma forma, se puede ver como en la línea 5
el primer cuadro de la tabla esta vacío, para evitar que aparezca el
texto descentrado.

Esta estructura nos permite generar los diccionarios 2x2, muy usados
al comparar conjuntos de datos.

En caso de necesitar más información, esta puede encontrarse
[aquí](https://en.wikibooks.org/wiki/LaTeX/Tables)
