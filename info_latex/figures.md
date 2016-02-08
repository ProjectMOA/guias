#Figuras

Una figura es un diagrama que deseamos destacar, el cual queremos
remarcar sobre una imagen normal.

Una figura se declara dentro de un ambiente *figure*:

```
\begin{figure}
  %% Contenido de la figura
  \caption{Diagrama}
  \label{fig:fig1}
\end{figure}
```

Ademas, una figura contiene otras etiquetas de valor especial
*\\caption* y *\\label*. Dentro de un *\\caption* se introduce el
texto que se desee que aparezca a pié de página; mientras *\\label*
permite asignar una referencia, de tal forma que en otro punto del
texto se puede utilizar:

```
\ref{fig:fig1}
```

Y eso será automaticamente sustituido por el número de referencia
dado, además de convertirse en un enlace a la figura particular.

Una figura será automáticamente desplazada al punto que Latex
considere más adecuado. Para sobreescribir dicha colocación, podemos
utilizar la siguiente sintaxis:

```
\begin{figure}[<colocacion>]
%%Contenido
\end{figure}
```

Donde colocacion puede tomar los siguientes valores: 
+   **h**: Intenta colocar la figura aproximadamente en la posición
    indicada en el texto.
+   **t**: Intenta colocar en la parte superior de la página.
+   **b**: Intenta colocar en la parte inferior de la página.
+   **p**: Coloca la figura en una pagina especial (separada del
    resto, contentdra tantos *figures* como pueda).
+   **!**: Sobreescribe los estandares internos de colocación de
    figuras.
+   **H**: Obliga a la aparición de la figura en donde aparezca en el
    texto. Requiere el paquete float (*\usepackage{float}*). Equivale
    a !ht.

Mas información en
[Wikibooks](https://en.wikibooks.org/wiki/LaTeX/Floats,_Figures_and_Captions)
