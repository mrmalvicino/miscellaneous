# Git Bash

- [Descargar Git](https://git-scm.com/)

## Crear repositorio

1. Inicializar Git en una carpeta:

```
git init
```

:warning: **El siguiente paso es necesario solo si se está creando un repositorio desde una terminal por primera vez.**

2. (*Opcional*) Definir nombre de usuario, mail y token:

```
git config --global user.name "username"
git config --global user.email mail@gmail.com
git config --global user.password TOKEN
```

:warning: **En caso de todavía no haberlo hecho, crear dentro de la carpeta los directorios y archivos necesarios para comenzar a escribir código, antes del siguiente paso.**

3. Agregar código y hacer un primer commit:

```
git add .
git commit -m "Initial commit"
```

4. Subir el contenido de la carpeta a la rama "main" de un repositorio vacío llamado "new-repo":

```
git remote add origin www.github.com/user/new-repo.git
git branch -M main
git push -u origin main
```

:warning: **Si se está creando un repositorio desde una terminal por primera vez, luego del paso anterior debería abrirse una interfaz de inicio de sesión para vincular la cuenta de Github. El repositorio comenzará a subirse a continuación.**

## Consultas

- Consultar el estado de un repositorio:

```
git status
```

- Consultar el detalle de todos los commits hechos a lo largo de las distintas versiones:

```
git log
```

- Consultar resumen de todos los commits hechos:

```
git log --oneline
```

- Descargar el repositorio "repo" del usuario "user":

```
git clone www.github.com/user/repo.git
```

## Implementación

- Implementar todos los cambios hechos:

```
git add .
```

- Descartar los cambios hechos:

```
git reset <nombredearchivo>
```

- Guardar una captura del estado del repositorio especificando las implementaciones hechas:

```
git commit -m "Escribir acá las implementaciones hechas"
```

- Guardar los commits hechos en la rama "main" del repositorio de GitHub:

```
git push -u origin main
```

## Git LFS (Large Files Storage)

- [Descargar Git LFS](https://git-lfs.github.com/)

- Usar Git LFS en el repositorio:

```
git lfs install
```

- Guardar todos los archivos con extensión "png":

```
git lfs track '*.png'
```

- Guardar todos los archivos con extensión "png" de la carpeta "images":

```
git lfs track 'images/*.png'
```

- Guardar todos los archivos de la carpeta "images":

```
git lfs track 'images/'
```

- Consultar una lista de lo que se está guardando en Git LFS:

```
git lfs track
```

- Consultar el detalle de todos los archivos guardados en Git LFS:

```
git lfs ls-files
```

## Colaboraciones

- Mostrar todas las ramas creadas e identificar la actual:

```
git branch
```

- Crear una nueva rama:

```
git branch nombredelarama
```

- Moverse a una rama:

```
git checkout nombredelarama
```

- Anadir a la rama main los cambios de la rama nombredelarama:

```
git checkout main
git merge nombredelarama
```

- Eliminar rama nombredelarama:

```
git branch -d nombredelarama
```

- Establecer nombre predeterminado de ramas:

```
git config --global init.defaultBranch <name>
```

## Combinar los últimos dos commits:

1. Asegurarse de estar en la rama correcta:
```
git checkout <nombre_de_la_rama>
```

2. Iniciar un rebase interactivo:
```
git rebase -i HEAD~2
```

- Se abrirá un editor de texto mostrando los últimos dos commits:
```
pick abc123 Mensaje del primer commit
pick def456 Mensaje del segundo commit
```

- Cambiar el segundo pick por squash
```
pick abc123 Mensaje del primer commit
squash def456 Mensaje del segundo commit
```

- Guardar y salir del editor:
```
:wq
```

- Editar el mensaje del commit resultante.

3. Si ya se había hecho push, cambiar el historial de la rama:
```
git push origin <nombre_de_la_rama> --force
```

## Otros

- Borrrar el último commit sin dejar rastro:

```
git reset --hard HEAD~1
git push -f origin main
```

- Cambiar el mensaje del último commit antes de haber hecho push:

```
git commit --amend -m 'Nuevo mensaje'
git push --force
```

- Consultar lista de configuraciones, como por ejemplo username o email:

```
git config -l
```

- Ver la url configurada para el repositorio:

```
git remote -v
```

- Quitar la url configurada para el repositorio:

```
git remote remove origin
```

- Alternativa para agregar origin:

```
git remote set-url origin http://github.com/emeery/nombre-repo.git
```