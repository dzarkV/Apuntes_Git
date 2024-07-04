# Apuntes de uso de Git

La estructura básica de un repositorio de Git:

<img src="https://github.com/dzarkV/Apuntes_Git/blob/main/img/Ciclo de vida de los ficheros en Git.png" width=60% height=60%>

## Algunos comandos útiles

<table>
<thead>
  <tr>
    <th>Acción</th>
    <th>Comando y breve explicación</th>
  </tr>
  <tr>
  </tr>
  <tr>
  </tr>
</thead><tbody>
  <tr>
    <td rowspan="14">Consultar</td>
    <td><code>find .git/objects/ -type f</code><br>Línea para ver los objetos en el git repository</td>
  </tr>
  <tr>
    <td><code>git ls-files</code><br>Linea para ver los archivos en el staging area</td>
  </tr>
  <tr>
    <td><code>git cat-file -t b2e2fbb</code><br>Se usa con los primeros caracteres hash del objeto, para ver el tipo de objeto de que se trata</td>
  </tr>
  <tr>
    <td><code>git cat-file -s b2e2fbb</code><br>Igual que el anterior, se usa con los primeros caracteres hash, para ver el tamaño del objeto</td>
  </tr>
  <tr>
    <td><code>git cat-file -p b2e2fbb</code><br>En este caso, se puede ver el contenido del objeto. Si se trata de un objeto commit, se ve que está compuesto por un objeto tree. Este tree, a su vez, puede ser consultado colocando el mismo comando, pero solo cambiando su hash</td>
  </tr>
  <tr>
    <td><code>git log --stat</code><br>Consulta los cambios específicos de cada commit</td>
  </tr>
  <tr>
    <td><code>git log -p</code><br>Consulta cambios de manera pormenorizada de cada commit</td>
  </tr>
  <tr>
    <td><code>git shortlog</code><br>Muestra los commits por cada colaborador (o usuario)</td>
  </tr>
  <tr>
    <td>
      <code>git shortlog -n -s</code><br>Muestra solo el listado de colaboradores con su número de commits respectivos</td>
  </tr>
  <tr>
    <td>
      <code>git shortlog -n -s -e</code><br>Muestra los colaboradores y su email</td>
  </tr>
  <tr>
    <td>
      <code>git log --author="partername" --oneline</code><br>Muestras los commits de un autor específico en una sola línea</td>
  </tr>
  <tr>
    <td>
      <code>git log --grep="commit message" --oneline</code><br>Muestra los commits con el mensaje específico en una sola línea</td>
  </tr>
  <tr>
    <td>
      <code>git log --merges --oneline</code><br>Muestra los commits que han hecho merge</td>
  </tr>
  <tr>
    <td>
      <code>git log --no-merges --oneline</code><br>Muestra los commits que NO han hecho merge</td>
  </tr>  
  <tr>
    <td rowspan="4">Modificar rama local</td>
    <td><code>git checkout -b nombrerama</code><br>Crea y cambia a la rama creada</td>
  </tr>
  <tr>
    <td><code>git branch -m nombrerama nombreRama</code><br>Renombrar la rama </td>
  </tr>
  <tr>
    <td><code>git branch -vv</code><br>Consulta la relación de las ramas con su commit y si está relacionada con una rama remota</td>
  </tr>
  <tr>
    <td>
      <code>git reflog</code><br>Consultar el historial de todo lo realizado en una determinada rama con una caducidad de 90 días</td>
  </tr>  
  <tr>
    <td rowspan="5">Cosultar y modificar repositorio remoto</td>
    <td><code>git remote -v</code><br>Ver la URL del repositorio remoto</td>
  </tr>
  <tr>
    <td><code>git remote show origin</code><br>Ver más información sobre las ramas remotas y las ramas locales: por ejemplo, si las ramas locales están actualizadas con las remotas </td>
  </tr>
  <tr>
    <td>
      <code>git push -u origin branchname</code><br>Permite subir los cambios realizados en local al origin directamente con el tracking de ello
    </td>
  </tr>
  <tr>
    <td>
      <code>git push origin -d branchname</code><br>Borrar la rama con el nombre específico en el origin (repositorio remoto) 
    </td>
  </tr>
  <tr>
    <td>
      <code>git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%C(bold blue)<%an>%Creset' --abbrev-commit</code><br>Creacion de un alias para `git lg`, que muestra el log de los commits de manera grafica y con algunos colores 
    </td>
  </tr>
  <tr>
    <td rowspan="5">Guardar una instantánea, replicar y otros</td>
    <td><code>git cherry-pick commithash</code><br>Estando ubicado en la rama receptora (por ejemplo, main), se replica el commit mencionado de la rama feature (por ejemplo), sin necesidad de hacer un merge</td>
  </tr>
  <tr>
    <td>
      <code>git stash</code><br>Guarda el directorio de trabajo y el índice (staging area) actual, como si fuera una fotografía de lo actual
    </td>
  </tr>
  <tr>
    <td>
      <code>git stash pop</code><br>Devuelve la referencia a el estado del stash guardado. Esto borra el stash.
    </td>
  </tr>
  <tr>
    <td>
      <code>git gc</code><br>Llama al garbage collector para limpiar el repositorio
    </td>
  </tr>
  <tr>
    <td>
      <code>git checkout-index -a</code><br>Vuelve los archivos que estaban en staging area al working directory como archivos físicos
    </td>
  </tr>
</tbody>
</table>

## ¿Cómo deshacer cambios?

<img src="https://github.com/dzarkV/Apuntes_Git/blob/main/img/undoing-changes-git.png" width=70% height=70%>

## Archivo .gitignore

<img src="https://github.com/dzarkV/Apuntes_Git/blob/main/img/gitignore-file.png" width=70% height=70%>

## ¿Cómo manejar los conflictos? (con el versionado de código 😛

<img src="https://github.com/dzarkV/Apuntes_Git/blob/main/img/git-conflicts.png" width=70% height=70%>
