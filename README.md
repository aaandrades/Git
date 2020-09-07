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

## Viaje en el tiempo Git
- git reset --soft #HashDelCommit: Marca los archivos del commit Stage
- git reset --mixed: Quitados del Stage
- git reset --hard: Se devuelve al Commit, quita todo lo que que se realizó en el commit.
- git reflog: muestra todo el histórico de movimientos de commits
- git reset --hard #Hash del commit: Restaura también commits que estaban perdidos.
- git checkout --nombre_archivo: Revierte los cambios realizados a un archivo antes de agregarlo al stage.

## Branch
Son lineas del tiempo de commits
Merge: Uniones de una rama a otra. 
  - Fast-forward:Automatico cuando no hay cambio en la rama principal y no hay conflictos para unir las ramas.
  - Uniones automaticas: Git detecta que la rama principal tuvo un cambio que las otras ramas no tienen, pero al hacer el merge lo une manteniendo los cambios de la línea actual que lleva.
  - Manual: Hay conflicto entre cambios. Crea el merge commit de forma manual del usuario.
  
Fast Forward: La más común, se ejecuta algo sobre la rama y se une
  - git branch nombre_rama: crea una nueva rama
  - git branch: muestra todas las ramas e indica sobre cual se está trabajando.
  - git checkout nombre_rama: se cambia a la rama escogida.
  - git diff nombre_rama nombre_otra_rama: Muestras las diferencias entre cada rama.
  - git merge nombre_rama_unir: Sobre la rama master se ejecuta para unir el contenido de la rama creada.
  - git branch -d nombre_rama: elimina la rama.
  
 Merge Automático: Se ejecuta algo sobre la rama pero el master se sigue actualizando
  - git checkout -b nombre_rama: Crea la rama y se mueve a la rama.
  - git merge nombre_rama_unir: Sobre la rama master se ejecuta para unir el contenido de la rama creada.

Merge Uniones con conflictos: Dos ramas modifican el mismo archivo.
  - Utilizar extensión de atom para definir qué parte del código va.
 Tags: Una referencia a un commit específico. Generalmente utilizado para marcar versiones o releases.
  - git tag nombre_capa: Agregar Tag.
  - git tag -a V0.1.0 HasCommit -m "Version Alfa"

## Git Stash
Caja o Contenedor donde se guardan los cambios temporales para dejarlo en el último commit. Es buena práctica borrar el stash siempre después de usar.
  - Git stash: Crea un nuevo stash con todo el trabajo actual o es proceso.
  - Git stash list: Muestra todos los WIP (Work in Progress) que tiene el proyecto.
  - git stash pop: Sirve para restaurar los archivos del Stash y los elimina.

## Git Rebase
Cuando sobre la master se realizan cambios que se utilizan en nuestra rama, el git rebase almacena los cambios actuales en un area temporal, corre la linea del tiempo del commit y vuelve a cargar los archivos que trabajamos en el area temporal.
<img src="https://cms-assets.tutsplus.com/uploads/users/585/posts/23191/image/rebase.png" alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />
Usualmente se utiliza para evitar conflictos con el merge, organiza los commits.
  - git rebase master: Actualiza respecto a la rama master
  GIT SQUASH
  - sobre el master permite unir los commits.
### Git rebase Actualizando rama

## Proceso de Publicación
- git init
- git add .
- git commit -m "mensaje del commit"
