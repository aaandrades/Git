# Git

## Main Commands

- git init: Inicia el repositorio local.
- git add . :Agregar todos los archivos para control de los cambios. Los coloca en el Stage.

GIT STATUS
- git status: Estado de todos los archivos de la carpeta. Muestra archivos que tienen modificaciones desde el ultimo commit y que no se han agregado al repositorio. Rama en que trabajamos, que archivos se han modificado y cuales estan listos para ser cargados.
- git status -s -b: Envia un resumen practico de los archivos que estan modificados acompañados de la información de la rama.

GIT COMMIT
- git commit: 'screenshot' del estado del repositorio local.
  - git commit -m "mensaje del commit".
- git checkout -- . : Reestablece archivos desde el ultimo commit
- git commit -am "mensaje": Agrega y genera el commit de una vez.
- git commit --amend -m "Nuevo mensaje": Corrige un commit.

GIT ADD
- git add *.png: agrega todo los archivos con formato png del directorio actual.
- git add "*.png": agrega todo los archivos con formato png que estan en el proyecto.
- git add css/: agrega todos los archivos dentro de la carpeta CSS.
- gitt add -A: Agrega todos los archivos que no se encontraban agregados.
- git add <index.html, index.css>: lista de archivos para agregar.

GIT RESET
- git reset .: Elimina todos los archivos que esten en el stage.

GIT LOG
- git log: trazabilidad de todas las modificaciones al proyecto.
- git log --oneline: Informacion del Log de forma mas corta y precisa.

GIT DIFF
- git diff: Listado de todas las modificaciones entre el ultimo commit y el momento actual.
- git diff --staged: Listado de todas las modificaciones que ya se encuentran agregadas.

## Creacion de Alias

- git config --global alias.lg "log --oneline --decorate --all --graph" -> el nombre va despues del "alias"
  - git lg: mismo resultados.
- git config --global alias.s "status -s -b".
  - git s: mismo resultado.

## Proceso de Publicación
- git init
- git add .
- git commit -m "mensaje del commit"
