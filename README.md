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
Para descargar contenido de un repositorio remoto, los comandos git pull y git fetch están disponibles para realizar esta tarea. 

Puedes considerar git fetch como la versión segura de los dos comandos. Este comando descarga el contenido remoto, pero no actualiza el estado de trabajo del repositorio local, por lo que tu trabajo actual no se verá afectado. 
```bash
$ git fetch <remote>
```
```bash
$ git fetch <remote> <branch>
```
git pull constituye una alternativa más agresiva, ya que descarga el contenido remoto a la rama local activa e inmediatamente ejecuta git merge para crear un commit fusionado con el nuevo contenido remoto.
```bash
$ git pull origin main
```
--allow-unrelated-histories, se usará en un evento raro que fusione las historias de dos proyectos que comenzaron sus vidas de forma independiente.
```bash
$ git pull origin main --allow-unrelated-histories
```
### Branch(ramas)
Crear una nueva rama 
```bash
$ git branch new_branch
```
Ver las ramas locales existentes
```bash
$ git branch 
```
ver las ramas locales y remotas existentes
```bash
$ git -r branch
```
_________________________
### Checkout(extraer)
En términos de Git, "checkout" (extraer) es el acto de cambiar entre diferentes versiones de una entidad objetivo. El comando git checkout opera sobre tres entidades distintas: archivos, confirmaciones y ramas.

Cambio de rama
```bash
$ git checkout <branchname>
```
Crear una rama y cambiar a ella al instante.
```bash
$ git checkout -b ＜new-branch＞
```
_________________________
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

### merge
Ir a mi rama con checkout primero 
```bash
$ git merge new-feature
```
### Cherry Pick 
git cherry-pick es un potente comando que permite que las confirmaciones arbitrarias de Git se elijan por referencia y se añadan al actual HEAD de trabajo.
En este caso, imaginemos que queremos aplicar la confirmación f a la rama main
git checkout main
```
$ git cherry-pick f
```

