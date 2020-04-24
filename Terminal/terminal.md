# TERMINAL Y LINEA DE COMANDOS 
### Tabla de contenido
- [Introduccion](#introduccion)
- [comandos](#comandos)
- [Manejo de directorios y archivos](#introduccion)
- [Herramientas básicas](#Herramientas-básicas)
- [Crea llaves SSH](#Crea-llaves-SSH)
- [Alias para comandos](#Alias-para-comandos)
- [Ver ejecucion de procesos](#Ver-ejecucion-de-procesos)
  - [Ejecutar en 2do plano](#Ejecutar-en-2do-plano)
  - [Ejecutar varios procesos](#Ejecutar-varios-procesos)
  - [Mostrar cantidad de procesos](#Mostrar-cantidad-de-procesos)
- [Tiempo de prendida de la computadora](#Tiempo-de-prendida-de-la-computadora)
- [Uso del disco](#Uso-del-disco)
- [Links](#Links)
- [Nombre de usuario](#Nombre-de-usuario)
- [Streams](#Streams)
- [Herramientas avanzadas](#Herramientas-avanzadas)
  - [Buscar cadenas de caracteres](#Buscar-cadenas-de-caracteres)
  - [Buscar archivos](#Buscar-archivos)
  - [Emular un navegador](#Emular-un-navegador)
  - [Comprimir archivos](#Comprimir-archivos)
  - [Pipe](#Pipe)
  - [Crontab](#Crontab)
  - [Permisos](#Pipe)
  - [Ejecutar como super user](#Ejecutar-como-super-user)

## Introduccion

La línea de comandos te permite hacer de todo: configuraciones, editar texto, compilar código y utilizar las herramientas que existen dentro de tu sistema operativo, tambien consume muy pocos recursos y es sumamente rapida.

## Comandos

Los comandos, en su mayor parte, no son realmente más que pequeños programas incorporados en el sistema operativo.

Los `flags` (o banderas) sirven para decirle al comando cómo queremos que realice la acción en particular.

**Puntos a tener en cuenta**

* Los comandos se pueden poner todos con un solo `-`. Por ejemplo, estos dos comandos hacen lo mismo:
    ```bash
    $ ls -l -h 
    $ ls -lh 
    ```
* El punto `.` es el directorio actual.
* El doble punto `..` es el directorio padre.
* El sombrerito de eñe `~` sirve para ir a mi carpeta personal (home).

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Manejo de archivos y directorios 
 
- `ls`: Nos permite listar los archivos y directorios que se encuentren dentro de la carpeta en la que estamos ubicados, podemos pasarle distintos parámetros a este comando:
  * `-a`podemos ver los archivos ocultos.
  * `-l`nos lista los contenidos mostrando sus permisos y propietarios.
  * `-t`nos lista los contenidos según su fecha.
  * `-h`ver de forma que sea facil de entender (para humanos )

- `pwd`: Nos retorna la ruta absoluta en la cual nos encontramos.

- `cd [ruta]`: Nos mueve a alguna carpeta que le indiquemos, dentro de los archivos ocultos vimos que existe:
  * ` .`: Refiere a la carpeta en la cual estamos ubicados.
  * ` ..`: Se refiere a la carpeta padre en la cual nos encontramos.
  * ` ~` nos mueve al home

- `clear`: Nos limpia la pantalla.

- `mkdir [directorio]`: Crea una carpeta.

- `touch [archivo]`: Crea un archivo vacío con el nombre que le indiquemos.
  * `touch {1, 2, 3}.txt` permite crear varios archivos

- `mv [origen] [destino]`: Permite mover archivos entre distintas carpetas, solamente debemos indicarle el nombre del archivo y la ruta de destino.
  * `mv archivo.txt C:/` cambiamos el archivo de lugar entre carpetas
  * `mv archivo.txt nuevo.txt` si movemos dentro de la misma carpeta, solo cambiamos el nombre del archivo

- `cp [archivo/carpeta] [ruta]`: copia un archivo a otro directorio 

- `rm [archivo]`: Elimina únicamente un archivo, añadiendo el parámetro
  * `-rf` podemos eliminar directorios también.

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Herramientas básicas

- `cat [archivo]`: permite visualizar un archivo completo en la terminal.

- `more [archivo]`: muestra por partes un archivo dentro de la terminal.
    * Para ver la siguiente página utilizamos espacio, Enter para pasar línea por línea, b para regresar.

- `tail [archivo]`: muestra las últimas 10 líneas de cada archivo.
    * `-[numero]` puedes agregarle un número con el - y pedir más que 10 líneas. 
    * `-f` muestra en tiempo real las ultimas lineas del archivo.

- `open [archivo]`: abre un archivo con el programa que tengamos por defecto.

- `nano [archivo]`: Es un editor dentro de la consola, podemos abrir cualquier archivo y modificarlo.

- `man [comando]`: Es el manual de la terminal, puedes utilizarlo para entender qué hace un comando y sus banderas. Con espacio pasas una página, - con b te regresas una página y con q sales del manual. es equivalente a `--help`
 
- `history`: Muestra el histórico de todos los comandos que hemos ejecutado.

- `which [comando]`  Especifica donde se encuentra el ejecutable del comando

```bash
$ which ls
output: /usr/bin/ls
```

- `date` Muestra la fecha actual.

- `date; [proceso]; date`:Con este comando se puede evaluar cuánto se demora en ejecutar un proceso

- `time` Muestra tiempo del procesador

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Crea llaves SSH

Las llaves SSH nos van a ayudar para autentificarnos con servidores. SSH utiliza criptografía asimétrica, o sea, tenemos dos llaves:

- Pública: la llave pública la podemos compartir por internet.
- Privada: debes tenerla en un sitio seguro y no debe ser compartida.

Tener una llave SSH nos permitirá una conexión fácil y segura con servidores, en el caso de la escuela de JavaScript nos va a servir para conectarnos con GitHub.

Para crear una llave SSH utilizamos el siguiente comando:

```bash
ssh-keygen -t rsa -b 4096 -C llave, puede ser tu correo> 
```

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>


## Alias para comandos

`alias [comando_alias]='[comando]'`

Crea un alias para un comando definido. 

```bash
$ alias ll='ls -lh'
```
En este ejemplo se está creando el comando `ll` que ejecutará `ls -lh`. 

Todo lo que se agregue después del alias se agrega automáticamente luego del comando.

```bash
$ ll -a
$ ls -lh -a
```

En el ejemplo, los 2 comandos hacen lo mismo.

Cada vez que abrimos la terminal se ejecuta un programa llamado `.bash_profile` que es una serie de comandos que da de alta unas variables.

En el `.bash_profile` se guardan los alias.

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Ver ejecucion de procesos

- `top` Ver todos los procesos que están corriendo en la computadora de manera interactiva. Es decir, la lista de procesos se va actualizando.

- `ps -wA` Muestra todos los procesos que se están ejecutando y desde donde vienen. Este comando no es interactivo.

- `kill -9 [proceso id]` Mata un proceso.

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>


### Ejecutar en 2do plano

` &` espacio y amberson para dejar un proceso en background. Esto quiere decir que el usuario va a seguir teniendo el control de la terminal.

```bash
$ npm start &
output: [1] 23954 (Id del proceso)
```
<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Ejecutar varios procesos

`;` con un punto y coma puedo separar procesos para que se ejecuten en una misma linea. El segundo proceso se ejecuta cuando termine el anterior.

```bash
$ ls; echo "hola"
```
<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>


### Mostrar cantidad de procesos

`ps -wA | wc -l`

Muestra la cantidad de procesos que se están ejecutando actualmente.

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Tiempo de prendida de la computadora

`uptime` 

* Muestra cuánto tiempo lleva prendida la computadora
* Cuántos usuarios se han logueado
* La carga promedio

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Uso del disco

`du` muestra la cantidad de espacio usado por los archivos en un directorio. 
* `-h` muestra el output de una manera que se pueda leer mejor.
* `-d [numero]` nivel de profundidad. Cuántos niveles baja de carpeta.

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Links

`ln -s [ruta del directorio] [alias]` Crea un alias que apunta a un directorio.
* `-s` link simbolico. Si se usa este parámetro con `rm` solo se elimina el acceso directo.

```bash
ls -s C:/carpeta alias_file 
cd alias_file
```

La terminal está interpretando `cd C:/carpeta`.

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Nombre de usuario

`whoami` 

Te dice cual es el usuario que esta operando

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Streams

Los streams son una forma de enviar datos a un comando y recibir un output de salida.

* `STDIN` Standard Input. Parametro de entrada.
* `STDOUT` Standard Output. Es la salida por defecto.
* `STDERR` Standard Error. Es la salida en caso suceda un error.

```php
<?php 
echo "número: ";
$d = trim(fread(STDIN, 100));
$i = 0;

while(true) {
  if(++$i % $d == 0) {
    fwrite(STDOUT, sprintf("El %d es múltiplo de %d.\n", $i, $d));
  } else {
    fwrite(STDERR,
    sprintf("Error, El %d NO es múltiplo de %d \n", $i, $d));
  }
  sleep(1);
}
?>
```

```bash
php 1-streams.php 1> salida.log 2> error.log
```
* `>` manda el output a un archivo
* Se guarda la salida en un archivo salida y el error en un archivo error
* Si se usa `>>` en vez de `>`, entonces el archivo se concatena en vez de sobreescribirse

```bash
php 1-streams.php 1> salida.log 2>&1
```
El error y el output aparecen en el mismo archivo

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Herramientas avanzadas

### Buscar cadenas de caracteres

`grep -r [ruta] -e [expresion]` nos ayuda a encontrar cadenas de caracteres dentro de todos los archivos de la ruta que le demos, con expresiones regulares.
* -r: que sea recursivo
* -n: numero de linea donde se encuentra la palabra en el archivo
* -e: expresion regular
* -i: no importa si es mayuscula o minuscula
* -v: muestra solo los resultados que no cumplen con el patrón.

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Buscar archivos

`find [ruta] -name [nombre]` busca en base al nombre y la metadata dentro del directorio que le digamos.
* -name: el nombre del archivo (*.js devuelve todos los archivos que terminan con .js)
* -type: el tipo

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Emular un navegador

`curl [url]` emula un navegador.
* `> [nombre]` descarga el archivo con el nombre que le has dado.
* `-o [nombre]` igual que el anterior

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Comprimir archivos

`zip [nombre.zip] [archivo a comprimir]`: agrega o reemplaza las entradas de un archivo zip de la lista, que puede incluir el nombre especial para comprimir la entrada.

`upzip [archivo]` descomprime un .zip
* `-vl` no descomprime sino que ve lo que hay adentro

`tar` es un comando similar a zip, junta varios archivos en uno solo sin comprimirlos. Después se le dicta un algoritmo de compresión, que es zip.
* `cfz [archivo.tar.gz]` junta y comprime 
* `xfz [archivo .tar.gz]` descomprime

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Pipe

Sirve para encadenar el standard output de un comando con el standard input de otro comando. Pa esto se usa `|`.

* `| wc -l` muestra cantidad de lineas del output.
```bash
$ ls -l | wc -l
```
* `| grep [patrón]` devuelve las lineas que cumplen con el patrón.
```bash
$ cat peliculas.csv | grep Thriller
```
* `| more` muestra la lista de resultados por paginas.
```bash
$ cat peliculas.csv | more
```

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Crontab

`crontab` permite programar la ejecución de scripts.
* `-l` muestra la lista de crontab
* `-e` editar la tabla crontab. Con esto se pueden agregar más scripts

```bash
0   16  *   *   *    $Home/src/cronjobs/daily.sh
0   *   *   *   *    $Home/src/cronjobs/hourly.sh
*   *   *   *   *    $Home/src/cronjobs/minutely.sh
```

Columnas:
* minuto 0-59
* hora 0-23
* dia mes 1-31
* mes 1-12
* dia semana: 0-7 (0 y 7 domingo)
* script/comando

**Ejemplo 1 para la columna minuto**
`1` Se ejecuta en el minuto 1
`1,10,18` Se ejecuta en el minuto 1, 10 y 18
`*/5` Se ejecuta cada 5 minutos
`1-10` Se ejecuta los primeros 10 minutos de cada hora
`*` Se ejecuta cada minuto

**Ejemplo 2**
```bash
*/15 4 * * * script.sh
```

Ejecuta script.sh:
* todos los días de la semana
* todos los meses
* todos los días del mes
* a las 4 am
* cada 15 minutos

**Ejemplo 3**
```bash
0 3 * * 1 script.sh
```

Ejecuta script.sh:
* solo si es lunes
* todos los meses
* todos los días del mes
* a las 3 am
* en el minuto cero

**Nota**: al momento de editar la tabla de crontab, asegurarse que se vea ordenado las columnas.

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Permisos

Podemos ver los permisos que tiene un archivo con `ls -l`.

```
$ ls -l
drwxr-xr-x 1 Sergio 197609   0 Jul  9 16:43 'a.txt'
```

Los permisos se muestran en el primer bloque del resultado. En el ejemplo anterior sería `drwxr-xr-x`.

Los permisos se pueden separar de la siguiente manera:

```
F/---/---/---
-: dir/link/file
---: permisos del owner (yo)
---: permisos del gropo
---: permisos de todo el mundo
```

Tipos de permisos:
* `r-–` permiso de lectura
* `rw-` permiso de lectura y escritura
* `rwx` permiso de lectura, escritura y ejecución

Los permisos tiene valores numéricos: 
* r = 4
* w = 2
* x = 1

Para otorgar permisos debemos darle un número que sea la suma de cada una de estas tres letras:

```
---: 0
--x: 1
-r-: 2
-wx: 3
r--: 4
r-x: 5
rw-: 6
rwx: 7
````

Para asignar los permisos se debe de dar el número tanto para el owner, el grupo y el público.
```
---/---/---
666: rw-rw-rw-
750: rwxr-x---`
```

**Cambiar permisos**

`chmod [numero] [archivo]` 

Permite cambiar los permisos a un archivo.

```bash
$ chmod 750 archivo.txt
```

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

## Ejecutar como super user

`sudo [script/comando]`

Ejecuta un comando como super usuario.

<div align="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>