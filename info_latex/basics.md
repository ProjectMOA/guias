#Basicos

Un fichero Latex tiene la extensión *.tex*. A diferencia de los
editores normales, que pertenecen a la familia de programas WYSIWYG
(What you see is what you get) Latex funciona como un lenguaje de
programación cualquiera, en el sentido de que primero se escribe un
fichero fuente, que ha continuación se compila mediante alguno de los
compiladores Latex (pdflatex, xelatex, lualatex...), el cual generara
el fichero final, ya sea pdf, dvi, html...

Por ello podemos elegir utilizar alguno de los programas WYSIWYG, o
editar directamente el texto plano en el *.tex*. Estos tutoriales se
centraran en lo segundo.

El compilador elegido es xelatex. Es algo más complicado que la
alternativa mas antigua pdflatex, pero ofrece bastantes más
características, como Unicode de serie. Otros compiladores (LuaLatex)
sustituyen el lenguaje Tex por otros lenguajes de programación (Lua)
que hacen más simple la programación dentro de Latex. Como se
considera que eso escapa a la cobertura de estos tutoriales, no se
tratará

#Estructura básica de un documento *.tex*
```
\documentclass[11pt]{article}

\begin{document}
  Hello World!
\end{document}
```

Este es el fichero *.tex* más básico posible. Un fichero *.tex* esta
formado de 2 partes diferenciadas

##Preámbulo
Aquí se configuran todos los parametros que pasaremos al compilador, que sin embargo no apareceran en el documento final. Esto incluye:
+ **documentclass**
+ Importados de paquetes
+ Declaraciones de estilos
+ Declaraciones de rutas (imagenes, paquetes extráneos...)
+ Declaraciones de nuevos comandos
+ ...

En el caso anterior, el preambulo esta formado sólo por la línea

```
\documentclass[11pt,a4paper]{article}
```

Esta linea indica que nuestro documento será un articulo, y el tamaño
de letra base será de 11 puntos.

Antes de nada, una puntualización. Los comandos Latex comienzan por
\\, y pueden tomar tanto parámetros obligatorios (encerrados entre {},
solo 1, generalmente es el texto a formatear), como opcionales
(encerrados entre [], pueden ser varios, indican opciones sobre como
se formateará el texto pasado a la función)

###DocumentClass
Una "clase" aporta una plantilla base a un documento, eso incluye la
importación automática de algunos paquetes, la predefinición de
algunos parámetros, el formateado de página...

Algunas de las clases más usadas son:
+  **article**: Articulo científico, documento técnico...
+  **report**: Documentos largos, no necesariamente técnicos
+  **book**: Libros (hehehe)
+  **slides**: Diapositivas
+  **letter**: Cartas
+  **beamer**: Presentaciones

Algunas de las opciones que podemos pasar a estos tipos son:

+  **10pt, 11pt, 12pt**: Tamaño de letra base.
+  **a4paper, letterpaper,...**: Tamaño de papel, muchas
   distribuciones usan A4 como predeterminado, pero no cuesta nada
   especificarlo..
+  **fleqn**: Coloca las formulas alineadas a la izquierda.
+  **leqno**: Numeración de formulas en el lado izquierdo.
+  **titlepage, notitlepage**: Indica si se ha de comenzar página nueva tras el título.
+  **twocolumn**: Distribuye el texto en 2 columnas.
+  **landscape**: Rota las paginas para mostrarlas en horizontal en vez de en vertical.
+  **openright, openany**: Fuerza los capítulos a aparecer solo en las
   paginas derechas o en la primera disponible. Ignorado en el tipo **article**.
+  **draft**: Modo debug, se muestran sangrías y justificados con
   cajas visibles, no se muestran imágenes

Aparte de estos existen muchos más
[esta pagina](http://www.google.com) contiene todos los existentes.

###Paquetes

Los paquetes son conjuntos de funciones precreadas que puedes incluir
en tu documento. Existen paquetes para realizar casi cualquier
tarea. Los paquetes estan escritos en una mezcla de Tex y Latex, y
tienen extensión *.sty*. Se incluyen en un documento con el comando

```
\usepackage[options]{package}
```

##Documento

A diferencia del preambulo, que no requiere indicación particular, el
documento ha de estar encerrado en un ambiente *document*

```
\begin{document}
Hola
\end{document}
```

El documento contiene el grueso del texto.

###Ambientes

Los ambientes (envionments) son zonas del documento que declaramos con
un conjunto de propiedades, y que se interpretan de forma especial.

El ejemplo mas simple es el ambiente *document*, que es obligatorio en
cualquier documento *.tex*, otros ejemplos son *figure*, *center*,
*tabular*, *itemize*...

Un ambiente se declara de la siguiente forma

```
\begin{center}
Hola
\end{center}
```

Ese "Hola" aparecerá centrado en la página, dado que aparece dentro de
un ambiente *center*, que centra todo lo que contiene.
