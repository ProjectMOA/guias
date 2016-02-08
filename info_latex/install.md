#Instalación

[Wikibooks](https://en.wikibooks.org/wiki/LaTeX/Installation) contiene
una guia de instalación bastante clara para los sistemas operativos
más usados

Ten en cuenta que si solo deseas probarlo, existen múltiples servicios
online que te permiten usar Latex sin necesidad de instalar nada en tu
ordenador, como [ShareLatex](https://www.sharelatex.com/) u 
[Overleaf](https://www.overleaf.com/).

#Otras librerías

En caso de que desees instalar librerias que no estén en la
instalación basica, tendrás que copiarlas en el directorio asociado a
tu sistema operativo:

+  **Windows XP**: C:\Documents and Settings\\*\<user name\>*\texmf\tex\latex\local
+  **Windows Vista/7**: C:\Users\\*\<user name\>*\texmf\tex\latex\local
+  **Linux**: ~/texmf/tex/latex/local
+  **Mac OS X**: /Users/*\<user name\>*/Library/texmf/tex/latex/local

Para installar una librería, ve a la ruta adecuada dado tu sistema
operativo, y copia el fichero *.sty* en el directorio, por ejemplo, si
deseara instalar una libreria *title.sty* en linux, se colocaría en la
ruta *~/texmf/tex/latex/local/title.sty*. Ten en cuenta que en general
se puede colocar en cualquier subdirectorio de *~/texmf/tex/latex/*
pero se referencia por el nombre del fichero *.sty*, por lo que
asegurate de no tener colisiones de nombre.
