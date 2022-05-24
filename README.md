# Comandos Github
Inicializando git.
```Bash
git init
```

Agregando todos los archivos que se han modificado.
```Bash
git add .
```

Envia los cambios del archivo al Sistema de Control de Versiones y puedes dejar un mensaje de descripción de los cambios.
```Bash
git commit -m "descripcion de los cambios"
```

Crea una nueva conexión a un repositorio remoto, poner nombre de origin al repositorio remoto para hacer referencia a una URL no tan sencilla. 
```Bash
git remote add origin https://....
```

Envía los cambios al repositorio remoto 
```Bash
git push origin main
```

_______________________
Te muestra el estado
```Bash
git status
``` 

Te muestra todos los cambios historicos hechos incluyendo linead de código, cuándo y quién hizo los cambios
```Bash
git show
```

Ver la historia entera de un archivo
```Bash
git log biografia.txt
```
