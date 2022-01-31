# Platzi  
# Curso de Introduccion a la Terminal y Linea De Comandos  
  
- **ls**: lista el contenido de la carpeta donde estamos parados.  
- **ls -l**: lista el contenido de la carpeta, pero con detalles.  
- **ls -lh**: lista el contenido de la carpeta, pero con detalles y el peso de los archivos los muestra para la lectura _humana_ (en kilobytes, megabytes, etc.).  
- **ls -l -la**: lista el contenido de la carpeta incluyendo archivos ocultos, pero con detalles.  
- **ls -lS**: lista el contenido de la carpeta, pero con detalles y ordenándolos por tamaño.  
- **ls -lr**: lista el contenido de la carpeta, pero con detalles y ordenados en reversa.  
  
- **tree**: lista los directorios en forma de árbol.  
- **tree -L** _numero_: lista los directorios en forma de árbol, pero sólo profundiza el valor indicado en _numero_.  
  
<br />  
  
- **cd**: cambia el directorio. Ej _cd carpeta_.  
- **clear**: limpia la pantalla.  
- **CTRL + l**: atajo de teclado de **clear**, limpia la pantalla.  
- **pwd**: devuelve el directorio donde estoy parado.  
- **file** _archivo_: devuelve información del archivo.  
  
## Manipular archivos y directorios  
- **mkdir** _carpeta_: crea un directorio llamado _carpeta_.  
- **touch** _archivo_: crea un archivo llamado _archivo_.  
- **cp** _archivo_ _copia_: crea una copia del archivo _archivo_ y llama a la copia _copia_.  
- **mv** _archivo_ _nuevaUbicacion_: mueve el _archivo_ a una _nuevaUbicacion_. También puede ser que la _nuevaUbicacion_ sea sólo un nuevo nombre dentro de la carpeta actual, por lo que lo estaría renombrando.  
  
- **rm** _archivo_: elimina el archivo.  
- **rm -i** _archivo_: elimina el archivo, pero antes me pregunta (interactivo) si deseo borrarlo.  
- **rm -r** _directorio_: elimina el directorio (recursivamente, significa que eliminará también a todo su contenido).  
- **rm -rf** _directorio_: elimina el directorio (recursivamente, significa que eliminará también a todo su contenido). ***Pero además lo hace forzosamente*** (OJO).  
  
## Explorar contenido de archivos  
- **head** _archivo_: devuelve las primeras 10 líneas de un archivo.  
- **head** _archivo_ **-n cantidad**: devuelve las primeras líneas de un archivo, pero aclarando cuántas queremos en cantidad.  
- **tail** _archivo_: devuelve las últimas 10 líneas de un archivo.  
- **tail** _archivo_ **-n cantidad**: devuelve las últimas líneas de un archivo, pero aclarando cuántas queremos en cantidad.  
- **less** _archivo_: ingresa al archivo de una manera interactiva. Si quiero buscar dentro del arvhivo tecleo la tecla **/** + la palabra que quiero buscar y la encuentra.  
- **type** _comando_: nos dirá el tipo del _comando_.  
- **alias** X="_comando_": se crea un alias. Al ejecutar X, se ejecutará el _comando_.  
- **help** _comando_: devuelve la ayuda para el _comando_.  
- _comando_ **--help**: devuelve la ayuda para el _comando_.  
- **man** _comando_: nos muestra el manual de uso del _comando_.  
- **info** _comando_: nos muestra la descripción del _comando_.  
- **whatis** _comando_: descripción corta del _comando_.  
  
## Wildcards  
- ls <span style="color:blue">*</span>.txt: el asterisco es un comodín. En este caso, el comando listará todos los archivos que terminen en _.txt_.  
- ls datos<span style="color:blue">*</span>: si el asterisco está al final del comando, me buscará los archivos que empiecen con _datos_.  
- ls datos<span style="color:blue">?</span>: busca todos los archivos que empiecen con datos y le siga sólo un caracter.  
- ls datos<span style="color:blue">???</span>: busca todos los archivos que empiecen con datos y le sigan sólo tres caracteres.  
- ls [[:upper:]]: busca los archivos o directorios que empiecen en mayúsculas.  
- ls **-d** [[:upper:]]: busca directorios que empiecen en mayúsculas.  
- ls [[:lower:]]: busca los archivos o directorios que empiecen en minúsculas.  
- ls [ad]*: busca los archivos que empiecen con a o con d.  
  
## Redirecciones  
- ls datos* **>** misarchivos.txt: guarda en el archivo _misarchivos.txt_ el resultado de _ls datos*_.  
- ls *.html **>>** misarchivos.txt: guarda en el archivo _misarchivos.txt_ el resultado de _ls *.html_ sin eliminar los datos existentes en _misarchivos.txt_ (concatenando).  
- ls *asdasd **2>>** misarchivos.txt: el comando ls *asdasd me devuelve un error, para guardar ese error hay que utilizar el tipo de entrada 2, ya que ese es el _standard error_.  
- ls asdasd **>** output.txt **2>&1**: guarda en _output.txt_ el resultado del comando. En caso de que esto devuelva error, guarda el error.  
  
>Independiente del lenguaje, cualquier programa tiene un flujo de entrada de datos “STANDARD INPUT” = “<”, un flujo de salida “STANDARD OUTPUT” = “>” o “1>” y un modo de capturar errores “STANDARD ERROR” = “2>”. En la terminal, podemos tener este mismo flujo de datos gracias a: “<” , “>” y “2>”.
TIP: esto es muy utilizado en los logs para definir los estados: [“ok”, “warning”, “error”].  
  
## Pipe operator  
- ls -lh **|** less: concatena ambos comandos, en este caso hace un listado y me lo muestra con less.  
- ls -lh **|** tee output.txt **|** less: concatena los comandos, en este caso hace un listado, eso lo guarda con tee en _output.txt_ y me lo muestra con less.  
  
## Encadenando comandos: operadores de control  
- ls **;** mkdir holi **;** cal: el **;** concatena comandos ejecutándolos en orden uno por uno (forma síncrona).  
- ls **&** date **&** cal: **&** ejecuta los comandos de forma asíncrona, no espera que se terminen de ejecutar los comandos anteriores para ejecutar los siguientes.  
- mkdir test **&&** cd test: **&&** ejecuta los comandos de forma condicional, si se ejecuta el primer comando satisfactoriamente, se ejecutará el siguiente.  
- cd testt **||** echo "Hola mundo": **||** ejecuta los comandos de forma síncrona sin importar si el primero se ejecutó satisfactoriamente o no.  
