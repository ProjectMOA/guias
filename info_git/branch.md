# Branches
Qué es un branch?

Como desarrollador y usuario de Git, puedes imaginar un branch como
una copia paralela de tu proyecto, que te permite realizar cambios
inestables a tu proyecto, manteniendo siempre una copia estable de tu
trabajo preparada para entregar en caso de que sea necesario.

Para comprobar los branch que tienes, se utiliza el comando

```
git branch
```

Que nos produce una salida como la siguiente:

```
* master
```

Esto significa que en el repositorio actual solo tenemos un branch,
denominado master, y el asterisco nos indica cual tenemos
seleccionado.

Ahora, creamos un nuevo branch con los comandos:

```
git branch test
git checkout test
```

El primer comando nos crea el branch, y el segundo nos cambia a
el. Existe la forma resumida:

```
git checkout -b test
```

Que creará un branch y cambiará a él, siendo el nuevo estado:

```
$> git branch
     master
   * test
```

Que indica que ahora tenemos seleccionado el nuevo branch test.
Una vez que estemos en un branch, trabajaremos normalmente, pero
recordemos que los cambios que realizamos solo afectan al branch en el
que estemos, incluidos todos los commit que hagamos, esto permite que
si en algun momento queremos recuperar la version no experimental, no
tenemos mas que hacer:

```
git checkout master
```

Y eso devolvera a nuestro directorio de trabajo al estado en el que
empezamos.

Una vez estemos contentos con nuestro trabajo, no queda más que hacer un

```
git merge <fuente> <destino>
```

Que aplica a nuestro branch destino los cambios de fuente, en el caso
trabajado, la fuente sería el branch experimental y el destino el
branch estable master.

Ten en cuenta que se pueden tener tantos branches abiertos como se
desee en un momento dado; como ejemplo, el proyecto Git tiene abiertos
siempre 5 branch (master, next, maint, pu y todo), y se crean y
destruyen varios al día.

Esta información se expande en el capítulo 3 del libro adjunto
