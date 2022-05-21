# Apuntes de uso de Git

La estructura básica de un repositorio de Git:

<img src="https://github.com/dzarkV/Apuntes_Git/blob/main/img/Ciclo de vida de los ficheros en Git.png" width=60% height=60%>

## Consultar 

`find .git/objects/ -type f`

Línea para ver los objetos en el git repository

---  

`git ls-files`

Linea para ver los archivos en el staging area

---

`git cat-file -t b2e2fbb`

Se usa con los primeros caracteres hash del objeto, para ver el tipo de objeto de que se trata

---

`git cat-file -s b2e2fbb`

Igual que el anterior, se usa con los primeros caracteres hash, para ver el tamaño del objeto

---

`git cat-file -p b2e2fbb`

En este caso, se puede ver el contenido del objeto. Si se trata de un objeto commit, se ve que está compuesto por un objeto tree. Este tree, a su vez, puede ser consultado colocando el mismo comando, pero solo cambiando su hash

---

`git log --stat`

Consulta los cambios específicos de cada commit

---

`git log -p`

Consulta cambios de manera pormenorizada de cada commit

---

`git shortlog`

Muestra los commits por cada colaborador (o usuario)

---

`git shortlog -n -s`

Muestra solo el listado de colaboradores con su número de commits respectivos

---

`git shortlog -n -s -e`

Muestra los colaboradores y su email

---

`git log --author="partername" --oneline`

Muestras los commits de un autor específico en una sola línea

---

`git log --grep="commit message" --oneline`

Muestra los commits con el mensaje específico en una sola línea

---

`git log --merges --oneline`

Muestra los commits que han hecho merge

---

`git log --no-merges --oneline`

Muestra los commits que **NO** han hecho merge

---

## Ramas

`git checkout -b nombrerama`

Crea y cambia a la rama creada

---

`git branch -m nombrerama nombreRama`

---

Renombrar la rama 

---

`git branch -vv`

Consulta la relación de las ramas con su commit y si está relacionada con una rama remota

---

`git reflog`

Consultar el historial de todo lo realizado en una determinada rama con una caducidad de 90 días

---


## Repositorio remoto

`git remote -v`

Ver la URL del repositorio remoto

---

`git remote show origin`

Ver más información sobre las ramas remotas y las ramas locales: por ejemplo, si las ramas locales están actualizadas con las remotas

---

`git push -u origin branchname`

Permite subir los cambios realizados en local al origin directamente con el tracking de ello

---

`git push origin -d branchname`

Borrar la rama con el nombre específico en el origin (repositorio remoto) 

---

`git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%C(bold blue)<%an>%Creset' --abbrev-commit`

Creacion de un alias para `git lg`, que muestra el log de los commits de manera grafica y con algunos colores 

---

## Modificar

`git cherry-pick commithash`

Estando ubicado en la rama receptora (por ejemplo, main), se replica el commit mencionado de la rama feature (por ejemplo), sin necesidad de hacer un merge

---

`git stash`

Guarda el directorio de trabajo y el índice (staging area) actual, como si fuera una fotografía de lo actual

---

`git stash pop`

Devuelve la referencia a ese estado del stash guardado. Esto borra el stash.

---

`git gc`

Llama al garbage collector para limpiar el repositorio

---

`git checkout-index -a`

Vuelve los archivos que estaban en staging area al working directory como archivos físicos

---
