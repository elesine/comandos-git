# Comandos Git
Inicializando git.
```Bash
$ git init
```

Agregando todos los archivos que se han modificado a Staging Area / tracked.
```Bash
$ git add .
```

Envia los cambios al repositorio local (master o main), debes dejar un mensaje de descripción de los cambios.
```Bash
$ git commit -m "descripcion de los cambios"
```

Crea una nueva conexión a un repositorio remoto, poner nombre de origin al repositorio remoto para hacer referencia a una URL no tan sencilla.
```Bash
$ git remote add origin https://...
```

Envía los cambios al repositorio remoto.
```Bash
$ git push origin main
```
_______________________

### Copia tu repositorio de Git y añade los archivos 

Clona el repositorio, debes copiar la URL (puede ser HTTPS o SSH).

```bash
$ git clone https://...
```
_______________________
### Puede usar los siguientes comandos para más información de los commits

Te muestra el estado.
```Bash
$ git status
``` 

Te muestra todos los cambios históricos hechos incluyendo lineas de código, cuándo y quién hizo los cambios.
```Bash
$ git show archivo.txt
```

Ver la historia entera de commits de un archivo.
```Bash
$ git log archivo.txt
```

Ver la diferencia entre 2 commit.
```Bash
$ git diff id-commit-version-mas-antigua id-commit-version-mas-reciente
```
_______________________
### Actualizar el repositorio local con cambios del repositoio remoto

El comando git pull se emplea para extraer y descargar contenido desde un repositorio remoto y actualizar al instante el repositorio local para reflejar ese contenido.
```bash
$ git pull origin master
```
--allow-unrelated-historiesque se usará en un evento raro que fusione las historias de dos proyectos que comenzaron sus vidas de forma independiente.
```bash
$ git pull origin master --allow-unrelated-histories
```
______________________
### Eliminado archivos de Staging area
Mueve los archivos que le indiquemos al estado Untracked, lo saca de la zona de Staging.
```bash
$ git rm --cached
```
Elimina los archivos de Git y del disco duro. Git guarda el registro de la existencia de los archivos, por lo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).
```bash
$ git rm --force
```
___________________________________
### LF will be replaces by CRLF 
En los sistemas Unix, el final de una línea se representa con un avance de línea (LF). 
En Windows, una línea se representa con un retorno de carro (CR) y un avance de línea (LF), es decir, (CRLF).

#### De forma global 

Git puede manejar esto convirtiendo automáticamente los finales de línea CRLF en LF cuando agrega un archivo al índice, y viceversa cuando extrae el código en su sistema de archivos. Puede activar esta funcionalidad con la configuración core.autocrlf. Si está en una máquina con Windows, configúrelo en verdadero: esto convierte las terminaciones LF en CRLF cuando revisa el código:

```bash
$ git config --global core.autocrlf true
```
Si está en un sistema Linux o Mac que usa finales de línea LF, entonces no quiere que Git los convierta automáticamente cuando extrae archivos; sin embargo, si se introduce accidentalmente un archivo con terminaciones CRLF, es posible que desee que Git lo arregle. Puede decirle a Git que convierta CRLF a LF en la confirmación, pero no al revés configurando core.autocrlf para ingresar:
```bash
$ git config --global core.autocrlf input
```
Esta configuración debería dejarte terminaciones CRLF en las cajas de Windows, pero terminaciones LF en los sistemas Mac y Linux y en el repositorio.

Si es un programador de Windows que realiza un proyecto solo para Windows, puede desactivar esta función y registrar los retornos de carro en el repositorio estableciendo el valor de configuración en falso:
```bash
$ git config --global core.autocrlf false
```

#### Para un proyecto
```bash
$ git config core.autocrlf false
```
