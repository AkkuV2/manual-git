# Guia de comandos git

En esta guia se manejara de forma sencilla una explicacion basica de algunos comandos de git con su respectiva sintaxis, en caso de llegar a olvidar como se usa cierto comando o cual es su proposito.

## Git init

Este comando sirve para inicializar la conexion de git en una carpeta en especifica, para esto se usara la terminal y una carpeta de preferencia.

Es importante aclarar que tienes que estar en el directorio de dicha carpeta para inicializarlo correctamente, puedes hacerlo desde la terminal o desde una herramienta externa (visual studio code, atom....etc).

Su sintaxis es:

```
git init
```

Lo que hace este comando es crear un repositorio vacio desde la carpeta en la que te ubicaste anteriormente y genera una carpeta oculta llamada "**.git**" donde git guarda toda la informacion del control de versiones

## Conectar a repositorio

Para lograr subir los archivos y cambios que deseas comodamente, necesitas un repositorio en github y su url, para conectar el repositorio remoto con la carpeta git que creaste, puedes usar el siguiente comando:

```
git remote add origin <URL DEL REPOSITORIO>
```

Un mejor ejemplo seria el siguiente:

```
git remote add origin https://github.com/usuario/nombre-repositorio.git
```
De esta forma conectando exitosamente con el repositorio remoto

## Estado de la carpeta

Para verificar el estado de la carpeta (para ver si hay archivos no añadidos o nuevos que no se han agregado)puedes usar el siguinte comando:

```
git status
```

Esto nos devolvera un output con informacion de estado de la carpeta.

## Resultado esperado

En este apartado hay dos posibles resultados (dependiendo de que hayas hecho o no primeramente).

### Caso 1

Haz ejecutado el comando **`add`** previamente para añadir archivos que hayas creado previamente, lo cual demostrara una insercion correcta de los archivos o carpetas a la preparacion de git.

### Caso 2

Si realizas algun cambio en la carpeta sin haber hecho los demas procedimientos, te deberia de salir "**_untracked files_**"

Este error indica que hay archivos no rastreados anteriormente o no estan agregados al repositorio global, Pueden ser archivos nuevos o archivos modificados que aún no han sido incluidos en el repositorio mediante el comando **`add`**

Los archivos no rastreados ('untracked files') son aquellos que aún no han sido agregados al control de versiones y Git no los está monitoreando para cambios

## Agregar nuevo archivo

Si deseas agregar el archivo de forma correcta,tendras que iniciar una serie de procedimientos para hacerlo, primero agregando el archivo que deseas como un archivo ya reconocido por git, deberas usar el siguiente comando:

```
Git add <nombre del archivo con su extension>
```

Verifica de nuevo con `git status ` y veras que el output es diferente

## Agregar archivo de forma definitiva

Si estas seguro de que quieres enviar el archivo para subirlo por completo,necesitaras realizar un commit

### Commit

Un commit es un mensaje que se enviara a github para detallar informacion de los cambios en el archivo o explicar que version esta basada.

```
git commit -m "Mensaje que debes agregar"
```

El output que te mostrara sera una confirmacion de insercion al repositorio en github del archivo.

Varios ejemplos de descripciones que podrian tener un commit serian las siguientes:

```
git commit -m "Añadir funcionalidad de login"
```

```
git commit -m "Corregir bug en validación de formularios"

```

Para subir el archivo al repositorio, se usara el comando **PUSH** para realizar dicha tarea

### Push

El comando push sube el archivo el cual preparaste previamente con todo el procedimiento, su sintax es:

```
git push - u <nombre u apodo del repositorio (origin)> <nombre de la rama (master viene por defecto)>

```

En caso de pedir una verificacion, tendrias que llenar los datos que te pide.

Para saltarte ese procedimiento (y hacerlo porque en sistemas basados en linux tiende a ser un poco mas complejo el proceso) tendras que usar un token

Luego de haber usado la verificacion (en caso de que no lo hayas hecho antes) puedes usar el comando push.

## Descargar archivos

Git tambien nos permite descargar archivos de proyectos ya creados de forma nativa desde su herramienta, siendo de forma general y especifica las maneras en las que nos permitira hacer dichas descargas de las actualizaciones.

### clone

Git clone es un comando el cual permite clonar archivos de un repositorio de github, esto es util en caso de que necesites descargar la version mas reciente de ciertos archivos o proyectos, permitiendo asi el acceso rapido a este.

```
git clone <URL DEL REPOSITORIO>
```

### pull

Git pull es otro comando el cual nos permite descargar archivos del repositorio de forma especifica; si un compañero u usuario ha realizado algun cambio en algun archivo o a subido un nuevo archivo a cierta rama, nos permitira descargar dicho archivo actualizado sin tener que descargar todo el proyecto de dicha rama nuevamente.

Su sintax es:

```
git pull origin <NOMBRE DE LA RAMA EN LA QUE ESTAN LOS CAMBIOS>

```

## Ramas

En git y github existen las ramas, variaciones de cada proyecto segun su version u usuario, esto nos permite tener un control de versiones mas completo para cada desarrollador que aporte al proyecto, gracias a las ramas, podemos incorporar ciertas actualizaciones al proyecto manteniendo cierto control en diferentes versiones

### Verificar en que rama te ubicas & ver ramas existentes

Para saber en que rama estas ubicado y que ramas existen dentro del repositorio de github, puedes usar el siguiente comando:

```
git branch
```

Con este comando se te devolvera en pantalla la ubicacion exacta de la rama en la que estas y las ramas que existen dentro del mismo repositorio, permitiendo asi evitar confusiones.

Si deseas ver las ramas remotas existentes dentro del repositorio, ejecuta el siguiente comando:

```
git branch -r
```

### Crear rama

Para crear una rama desde git para poder organizar nuestros avances en proyectos, podemos emplear un comando para dicha tarea, el comando es el siguiente:

```
git branch <NOMBRE DE LA RAMA>
```

Con esto ya se creara una rama en el repositorio, puedes verificar si se creo con el comando ` git branch`

### Renombrar rama

Para renombrar una rama ya existente (en caso de equivocaciones o cambios) puedes hacerlo desde git con el siguiente comando:

```
git branch -m <NOMBRE DE LA RAMA> <NUEVO NOMBRE>
```

Con esto se renombrara la rama que especificaste, nuevamente puedes verificar con el comando `git branch ` para asegurarte de que se realizaron los cambios

### Cambiar de rama

Para cambiar la ubicacion en la que te encuentras dentro del repositorio desde git puedes usar el siguiente comando:

```
git checkout <NOMBRE DE LA RAMA>
```

### Eliminar una rama

Para eliminar una rama existente dentro del repositorio de github, puedes usar el siguiente comando:

```
git branch -d <NOMBRE DE LA RAMA>
```

Cabe aclarar que para poder eliminar dicha rama **NO** tienes que estar ubicado en esa misma rama, de lo contrario te dara error

### Diferenciar contenido de ramas

Si deseas ver la diferencia que tienen de archivos ciertas ramas, como la rama main (principal) y una rama secundaria, puedes hacerlo con el siguiente comando:

```
git diff RAMA1 RAMA2

```

### Combinar ramas

Si estas seguro de que tu trabajo ya es funcional y no va a provocar problemas en el proyecto principal,puedes usar el comando merge para combinar los archivos de la rama trabajada con la rama principal de la siguiente manera:

```
git merge <RAMA_INICIO> <RAMA_DESTINO>

```

Lo que hagas en la **RAMA INICIO** (los archivos y cambios que tenga) se combinaran a la **RAMA DESTINO** con el fin de que el trabajo realizado se vuelva parte del proyecto final.

Para hacer este proceso hay que tener en cuenta que debes de estar ubicado en la rama a la que deseas actualizar, para evitar problemas, si deseas actualizar la rama master, debes de estar en la rama master y no en otra.

## Tokens

Desde cierta actualizacion de git se pide un token de acceso (una clave que solo el usuario debe de tener del repositorio) para obtener el token dirigete a la pagina web desde [aqui](https://github.com/settings/tokens).

Luego de generarlo, copialo y guardalo (solo lo veras una vez) los tokens tienen fecha de expiracion, cada cierto tiempo tendras que renovar el token.

Para aplicar el token desde git, deberas usar el siguiente comando con la siguiente estructura:

```
TOKENS
git remote set-url origin https://<TOKEN>@github.com/<NOMBRE DE USUARIO GITHUB>/<NOMBRE U APODO DE LA REPO>
```

## Gitignore

Si deseas evitar el reemplazo de archivos basicos o temporales (que no necesitan ser subidos constantemente al repositorio en github) puedes crear un archivo gitignore.

Este archivo te permitira evitar esa problematica: subir archivos que no son necesarios subir

para hacer esto necesitaras crear un archivo en la carpeta raiz del repositorio local, la cual debe de tener la siguiente estructura:

```
<NOMBRE DEL ARCHIVO>.gitignore
```

Si deseas ignorar solo un archivo dentro de la carpeta raiz, solo bastara con escribir en el archivo de **_gitignore_** la siguiente linea:

```
<NOMBRE DEL ARCHIVO><EXTENSION>

```

Un ejemplo de esto seria:

```
archivo.log
```

Si deseas especificar un archivo en un subdirectorio, podrias poner esto:

```
<NOMBRE DE LA CARPETA>/<NOMBRE DEL ARCHIVO>
```

Otro ejemplo de esto seria:

```
subdirectorio/archivo.log

```

#### ¿Lo haz notado?

La especificacion de los archivos que quieres evitar dentro del gitignore solo manejan su ubicacion especifica dentro de la carpeta

Si deseas evitar archivos con ciertas extensiones, puedes tambien usar este comando:

```
*.<EXTENSION DEL ARCHIVO>
```

Como podras ver, solo necesitas el `*.extension` del archivo, el **\*** simboliza **TODO**, queriendo decir que evitara todo archivo que contenga la extension que le sigue

Un ejemplo de esto es:

```
*.log
*.tmp
```

Si deseas ignorar un directorio (carpeta) por completo, puedes usar lo siguiente:

```
/CARPETA/
```

Aqui le indicas a git que va a ignorar todo el contenido que este dentro de dicha carpeta, un ejemplo de esto seria:

```
/logs/
```

## Tabla de comandos

A continuacion, se enlistaran todos los comandos expuestos en esta documentacion y su funcion para un facil acceso a todos los comandos sin necesidad de leer todo.

| Comandos                               | Descripcion                                            |
| -------------------------------------- | ------------------------------------------------------ |
| git init                               | Inicializa un repositorio vacío.                       |
| git status                             | Muestra el estado de los archivos en el repositorio.   |
| git add <archivo>                      | Agrega archivos al área de preparación para el commit. |
| git commit -m "mensaje"                | Realiza un commit con un mensaje descriptivo.          |
| git push                               | Sube los cambios a un repositorio remoto.              |
| git clone <URL>                        | Clona un repositorio remoto a tu máquina local.        |
| git pull origin <rama>                 | Descarga y fusiona los cambios de una rama remota.     |
| git branch                             | Muestra las ramas locales del repositorio.             |
| git checkout <rama>                    | Cambia de rama.                                        |
| git merge <rama inicio> <rama destino> | Fusiona los cambios de una rama a la rama destino.     |
