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
