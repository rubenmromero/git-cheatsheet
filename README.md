# Git Cheatsheet

![Git Data Transport Commands](git-transport.png)

Command | Purpose
---- | ----
`git status` | Estado de los cambios en local y en el area de staging
`git branch -av` | Estado de las ramas locales y remotas del repositorio
`git init` | Inicializar Git en un proyecto local (carpeta sobre la que se ejecuta)
`git add <file>` | Añade el fichero <file> si es nuevo, o trackea los cambios realizados en el mismo si ya existe, en el área de staging
`git add .` | Añade/trackea todos los ficheros y cambios pendientes de trackear en el área de staging
`git rm <file>` | Trackea en el area de staging (listo para hacer commit) un fichero eliminado
`git checkout <file>` | Descarta los cambios realizados en el fichero <file> pendientes de trackear en el area de staging
`git checkout .` | Descarta todos los cambios realizados que estén pendientes de trackear en el área de staging a excepción de los ficheros nuevos aún no trackeados, los cuales se mantienen en el mismo estado (creados y pendientes de trackear)
`git commit -m "<message>"` | Commitea cambios trackeados en el area de staging
`git branch <branch>` | Crea la rama <branch> en el repositorio local
`git branch -d <branch>` | Elimina la rama <branch> en el repositorio local
`git branch -D <branch>` | Elimina la rama <branch> en el repostorio local pese a que no esté completamente mergeada
`git checkout <branch>` | Cambia la rama activa a otra rama <branch> existente en el repositorio (local o remoto)
`git checkout -b <branch>` | Crea la rama <branch> a partir de la rama activa (se replica) se posiciona en la misma
`git fetch -p` | Actualiza el índice local con el estado actual de todas las ramas existentes en el repositorio remoto, eliminando aquellas que ya no existan
`git pull` | Actualiza en la rama local activa los cambios existentes en la rama enlazada en el repositorio remoto
`git push -u origin <branch>` | Empuja los cambios commiteados en la rama local activa a la rama <branch> del repositorio remoto creándola en caso de que no exista, y enlazando ambas ramas (local y remota) entre si
`git push` | Empuja los cambios commiteados en la rama local activa a la rama enlazada existente en el repositorio remoto
`git push --force` | Empuja los cambios commiteados en la rama local activa descartando posibles commits diferentes que puedan existir en la rama enlazada del repositorio remoto
`git push origin :<branch>` | Elimina la rama <branch> en el repositorio remoto
`git tag <tag> -m "<message>"` | Crea el tag <tag> en el repo local a partir del HEAD en el que estemos situados (rama activa + último commit)
`git tag -d <tag>` | Elimina el tag <tag> en el repositorio local
`git push --tags` | Empuja los tags existentes en el repositorio local al remoto
`git push origin :<tag>` | Elimina el tag <tag> en el repositorio remoto
`git merge <branch>` | Mergea los nuevos commits existentes en la rama <branch> a la rama activa
`git rebase <branch>` | Hace un rebase de la rama activa sobre los nuevos commits existentes en la rama de origen <branch> (base)
`git reset HEAD <file>` | Descarta los cambios trackeados en el área de staging pertenecientes al fichero <file>
`git reset HEAD` | Descarta todos los cambios trackeados en el área de staging
`git reset HEAD~<n>` | Deshace los últimos <n> commits existentes en la rama local activa manteniendo todos los cambios realizados a través de los mismos (soft reset) listos para poder ser trackeados de nuevo en el área de staging, o bien descartados definitivamente mediante la ejecución del comando `git checkout .`
`git reset --hard origin/<branch>` | Descarta todos los posibles commits y cambios realizados en la rama local activa poniendola en el mismo estado que la rama <branch> existente en el repositorio remoto, ya esté enlazada o no a la rama local activa (hard reset)
`git stash` | Oculta todos los cambios no commiteados (trackeados + pendientes de trackear) en un directorio de trabajo temporal a excepción de los ficheros nuevos aún no trackeados, los cuales se mantienen en el mismo estado (creados y pendientes de trackear)
`git stash pop` | Recupera en la rama local activa los cambios previamente ocultados a través del comando `git stash`

Estos dos últimos comandos son muy útiles cuando se tienen cambios pendientes de commitear en una rama y se necesita hacer un checkout a otra rama distinta para evitar que trate de acarrearlos a la nueva rama activa.
