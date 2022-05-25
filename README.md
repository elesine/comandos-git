# Comandos Git
Inicializando git.
```Bash
git init
```

Agregando todos los archivos que se han modificado a Staging Area / tracked.
```Bash
git add .
```

Envia los cambios al repositorio local (master o main), debes dejar un mensaje de descripción de los cambios.
```Bash
git commit -m "descripcion de los cambios"
```

Crea una nueva conexión a un repositorio remoto, poner nombre de origin al repositorio remoto para hacer referencia a una URL no tan sencilla.
```Bash
git remote add origin https://...
```

Envía los cambios al repositorio remoto.
```Bash
git push origin main
```
_______________________

### Copia tu repositorio de Git y añade los archivos 

Clona el repositorio, debes copiar la URL (puede ser HTTPS o SSH).

```bash
git clone https://...
```
_______________________
### Puede usar los siguientes comandos para más información de los commits

Te muestra el estado.
```Bash
git status
``` 

Te muestra todos los cambios históricos hechos incluyendo lineas de código, cuándo y quién hizo los cambios.
```Bash
git show archivo.txt
```

Ver la historia entera de commits de un archivo.
```Bash
git log archivo.txt
```

Ver la diferencia entre 2 commit
```Bash
git diff id-commit-version-mas-antigua id-commit-version-mas-reciente
```
______________________

Mueve los archivos que le indiquemos al estado Untracked, lo saca de la zona de Staging.
```bash
git rm --cached
```
Elimina los archivos de Git y del disco duro. Git guarda el registro de la existencia de los archivos, por lo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).
```bash
git rm --force
```