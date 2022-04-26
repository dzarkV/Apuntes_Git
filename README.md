Algunos apuntes de comnados importantes usados en el curso.

"find .git/objects/ -type f"
para ver los objetos en el git repoository
  
"git ls-files"
para ver los archivos en el staging area

"git checkout-index -a"
vuelve los archivos que estaban en staging area al working directory como archivos fisicos

"git cat-file -t b2e2fbb" 
se usa con los primeros caracteres hash del objeto, para ver el tipo de objeto de que se trata

"git cat-file -s b2e2fbb"
igual que el anterior, se usa con los primeros carateres hash, para ver al tamaño del objeto

"git cat-file -p b2e2fbb"
en este caso, se puede ver el cnotenido del objeto. Si se trata de un objeto commit se ve que esta compuesto por un objeto tree, este tree, a su vez puede ser consultado colocando el mismo comando, pero solo cambiando su hash
"git checkout -b nombrerama"
crea y cambia a la rama creada

"git branch -m nombrerama nombreRama"
renombrar la rama 

"git remote -v"
ver la URL del repositorio remoto

"git remote show origin"
ver más información sobre las ramas remotas y las ramas locales: por ejemplo, si las ramas locales están actualizadas con las remotas

"git branch -vv"
consulta la relación de las ramas con su commit y si está relacionada con una rama remota

"git push -u origin branchname"
permite subir los cambios realizados en local al origin directamente con el tracking de ello

"git push origin -d branchname"
borrar la rama con el nombre específico en el origin (repositorio remoto) 

"gir reflog"
consultar el historial de todo lo realizado en una determinada rama, con una caducidad de 90 días

" git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%C(bold blue)<%an>%Creset' --abbrev-commit" "
Creacion de un alias para "git lg", que muestra el log de los commitsde manera grafica y con algunos colores 

"git log --stat"
Consulta los cambios específicos de cada commit

"git log -p"
Consulta cambios de manera pormenorizada de cada commit

"git shortlog"
Muestra los commits por cada colaborador (o usuario)

"git shortlog -n -s"
Muestra solo el listado de colaboradores con su n[umero de commits respectivos

"git shortlog -n -s -e"
Muestra los colaboradores y su email

"git log --author="partername" --oneline"
Muestras los commits de un autor específico en una sola línea

"git log --grep="commit message" --oneline"
Muestra los commits con el mensaje específico en una sola línea

"git log --merges --oneline"
Muestra los commits que han hecho merge

"git log --no-merges --oneline"
Muestra los commits que NO han hecho merge

"git cherry-pick commithash"
Estando ubicado en la rama receptora (por ejemplo, main), se replica el commit mencionado de la rama feature (por ejemplo), sin necesidad de hacer un merge

"git stash"
Guarda el directorio de trabajo y el índice (staging area) actual, como si fuera una fotografía de lo actual

"git stash pop"
Devuelve la referencia a ese estado del stash guardado. Esto borra el stash.

"git gc"
Llama al garbage collector para limpiar el repositorio


