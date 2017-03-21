# Instalación
Aquí encontrarás la manera de instalar el entorno Node.js en tu equipo.
Se muestran los pasos de instalación para los sistemas operativos Ubuntu y
Windows. Ten en cuenta que las instrucciones están orientadas a la descarga de
la versión LTS(Long term support).
## Windows
La forma más sencilla de instalar node.js es descargándose el instalador para
Windows desde la [página oficial](https://nodejs.org/en/download). De este modo simplemente hay que
ejecutarlo y seguir las instrucciones del instalador.
## Ubuntu
A diferencia de la versión para Windows, la de Linux no tiene instalador, por
lo que deberemos de hacerlo manualmente.
Para ello

1. Descargamos el archivo comprimido de la [página oficial](https://nodejs.org/en/download)
2. Lo descomprimimos en la carpeta deseada (Recomendablemente, /opt), nos creará un directorio
con los archivos del programa (en mi caso, en */opt/node-v4.2.6-linux-x86*)
3. A partir de aquí tenemos 2 opciones:
   1. Añadir a nuestra variable de entorno PATH la ruta en la cual se localizan los binarios de
nuestra aplicación (en mi caso */opt/node-v4.2.6-linux-x86/bin*)
   2. Crear enlaces soft a cada uno de los ficheros binarios (en mi caso
*/opt/node-v4.2.6-linux-x86/bin/node* y */opt/node-v4.2.6-linux-x86/bin/npm*) en alguno de los
directorios que ya pertenezcan al PATH (por ejemplo, */bin* o */usr/local/bin*)

En cualquiera de los dos casos, recuerda lo que has elegido para poder poder desinstalarlo sin
problemas.
