
* Comandos de Git

git init  Iniciar proyecto

git add .  Agregar cambios al stage

git status  Te indica los archivos que se les está dando seguimiento

git commit -m "{mensaje}"  Se suben los cambios del stage y se genera un hash para hacer push
git commit --amend -m "{mensaje}"  Modifica el mensaje del último commit
git commit -am "{mensjae}"  Agregas los cambios al stage y al mismo tiempo creas el commit con su mensaje

git reset --soft HEAD^  El Head puede ser reemplazado por el hash de un commit, también se pueden mover a commits anteriores HEAD^n; ej HEAD^2, HEAD^3

git reset --hard {hash}  Regresar al hash especificado

git checkout --.  Deshacer cambios, regresar al estado del commit anterior
git checkout -b {nombre de la rama}  Crear y moverse a la nueva rama

git reflog  Revisar el historial del proyecto

git branch  Ver o crear ramas

git checkout {nombre de rama}  Sirve para cambiarnos a la rama que queremos


* Fast-forward
Se posiciona (git checkout {nombre de la rama}) en la rama que espera unir los nuevos cambios, los cuales fueron desarollados en otra rama diferente

* Recursive
La estrategia recursiva, revisa que no se hayan modificado las mismas líneas de código, o los mismos archivos, los archivos los revisa de forma interna, si es un archivo binario como una imagen se va generar un conflicto y se debe elegir de manera manual.

git merge {nombre de la rama de la que queremos traer los cambios y unir a nuestra actual rama}

Una vez que se une la rama y ya no se va a modidificar ponemos eliminar la rama para que ya no sigua existiendo sin una razón

git branch -d {nombre de la rama a eliminar}  Si ubieran cambios que no se han unido a ninguna rama, Git nos hará una advertencia, si aun así es necesario eliminar la rama se puede agregar al final la bandera -f para forzar la eliminación

git tag  Muestra los tags existentes
git tag {Nombre del tag}  Para agrega un tag a la rama actual
git tag -d {nombre del tag}  Para eliminar un tag
git tag -a v1.0.0 -m "{mensaje}"  Con -a (anotación) se crea una anotación
git tag -a v0.1.0 {hash}  Para agregar un tag a una hash en especifico

git show {anotacion de un tag}  Muestra información de un commit con tag 

La notación de versión v1.0.0
El primer número se cambia cuando se hace un cambio muy grande, como un brakepoint
El segundo número normalmente se cambia cuando se agregan nuevas caracteristicas
El último número está para las correciones de errores


git stash  Guardar progreso o cambios en un espacio aislado del código, fuera de un commit
git stash list  Listar stash's almacenados
git stash list --stat  Muestra información de los stash's con algo de información del stash
git stash pop  Toma el código del último stash y lo pone en el espacio del trabajo y borra el stash
git stash clear  Borra los stash's
git stash show {hash}  Muestro algo de información
git stash save "{mensaje}"  Al momento de hacer stash show muestra más el mensaje

git rebase {nombre de la rama a la que se queire apuntar el rebase}  Nos ayuda a actualizar el punto de separación de una rama
Ej. Estas en rama secundaria y quieres cambiar la rama de la cual inicia esta rama secundaria, estando en la rama secundaria haces el rebase.
Después de hacer el rebase los cambios de la rama secundaria están hasta arriba del historial, se puede hacer merge para unir a la rama principal; ej git checkout main --> git merge rama secundaria.
Esto aplicaría un Fast-forward y se podría eliminar la rama ya que quedaría vacía

git rebase -i HEAD~{número de commits que se tomarán}
pick no hace nada
squash  ve el commite anterior y los une








