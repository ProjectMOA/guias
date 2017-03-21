# Imagenes

Existen 2 formas de crear imágenes en un documento Latex. La primera
es generarlos proceduralmente mediante alguno de los paquetes
adecuados (tikz, displaymath...). La segunda es generarlos en
cualquier otro programa, exportarlos en alguno de los formatos
soportados por Latex, e insertarlos en el documento.

Latex soporta imagenes vectoriales y rasterizadas, siendo el formato
de las vectoriales EPS; y para las rasterizadas PDF, EPS, PNG y JPEG.

Para todas las tareas que involucren imágenes, es necesaria la
inclusión del paquete *graphicx*:

```
\usepackage{graphicx}
```

### Configuración

Se puede utilizar el comando *graphicspath* para indicar la
localización de las imágenes a usar. En caso de que el documento
incluya pocas, no existe problema por colocar las imagenes en el mismo
directorio que el *.tex*, pero dicho sistema puede hacerse inmanejable
para documentos mayores.

```
\graphicspath{ {directorio_1/}{directorio_2/}{directorio_3/} }
```

Se pueden utilizar rutas relativas (por ejemplo, haciendo que el
directorio del documento contenga un directorio *imagenes/* con todas
las necesarias) o absolutas (en caso de que se trabaje en alguna
asociación, se puede guardar los logos en un repositorio central, en
vez de copiarlos en todos los documentos)

Es importante tener en cuenta que el uso de rutas evita la
portabilidad. Hay que tener en cuenta que las absolutas solo tienen
sentido en el ordenador en el que se crearon (a menos que todo aquel
que use el documento lo sepa), y las relativas pueden dar problemas
por las diferencias entre Sistemas Operativos.


De la misma forma, se puede utilizar la sentencia
*DeclareGraphicsExtensions*, que establece prioridad entre los
distintos formatos que soporta Latex, de tal forma que se puede usar
una imágen de baja resolución para las visualizaciones previas y una
de alta resolución para la impresión final.

```
\DeclareGraphicsExtensions{.pdf,.png,.jpg}
```

Los elementos se eligen primero el de más a la izquierda


### Uso
El comando básico para insertar imagenes es *includegraphics*:

```
\includegraphics[<opciones>]{<imagen>}
```

Las opciones pueden ser:
+  **width=xx**: Especificar la anchura de la imágen.
+  **height=xx**: Especificar la altura de la imágen.
+  **keepaspectratio=true/false**: En caso de que se especifique como
   false, Latex no mantendrá el ratio de la imágen al
   aumentarla/disminuirla.
+  **scale=xx**: Especifica el factor de escala (multiplicativo; 0.5
   para reducir a la mitad, 2 para aumentar al doble).
+  **angle=xx**: Rota la imagen los grados indicados (en sentido
   contrarreloj).
+  **trim=l b r t**: Corta la imagen por los bordes las longitudes
   indicadas (l izquierda, b inferior, r derecha, t superior). l, b, r
   y t son longitudes.
+  **clip=true/false**: Para usar trim, poner a true.
+  **page=x**: Si la imagen indicada es un pdf, indica la página a
   cojer (Indexada por 1).
+  **resolution=x**: Indica la resolución a escojer.


*(En caso de que solo se especifíque width o height, Latex intentará
 mantener el ratio de la imagen.)*

Existe la posibilidad de usar las medidas especiales *\linewidth*,
*\textwidth* y *\textheight*, de tal forma que indiquemos medidas
dependientes del tamaño de línea, de la siguiente forma:

```
\includegraphics[width=0.5\textwidth]{<imagen>}
```

Que insertará la imágen con una anchura la mitad del texto
circundante.
