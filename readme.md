- ¿Qué comando utilizaste en el paso 11? ¿Por qué? 
git reset --hard HEAD~1. 
De este modo echo un paso hacia atrás. El --hard descarta los cambios. ~1, que para este caso es lo mismo que ~, especifica que doy un paso hacia atrás. 
- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué? 
He hecho un git reflog para ver el commit donde había actualizado el archivo. He copiado la referencia del commit y he vuelto a él con un git reset --hard, seguido de la referencia que he copiado. El hard, de nuevo, me sirve para modificar mi working copy, donde puedo comprobar si ha funcionado. 
- El merge del paso 13, ¿Causó algún con?icto? ¿Por qué? 
No, ya que los cambios de la rama styled son nuevos respecto a la rama master. Git se queda con los de styled, ya que son más nuevos.
- El merge del paso 19, ¿Causó algún con?icto? ¿Por qué? 
Sí, porque hemos modificado exactamente las mismas líneas en dos archivos que pretendemos fusionar (merge). 
De haber sido simples cambios en la misma rama no habría habido conflicto ninguno (unos serían más nuevos que los otros), pero al tratarse de merge, git no sabe a qué archivo dar prioridad. 
- El merge del paso 21, ¿Causó algún con?icto? ¿Por qué? 
No, porque nos hemos quedado con el contenido de la rama styled en el último merge. Como styled estaba en línea con master, ha sido un fast forwards.
- ¿Qué comando o comandos utilizaste en el paso 25?
He utilizado git config alias.graph "log --graph --decorate --pretty=oneline"
seguido de git graph.
Este sistema muestra un diagrama aproximado de la situación de cada rama en función de los commits que hemos hecho. Es la forma más fidedigna (que conozco) de dibujar la estructura de nuestro repo sin usar SourceTree.
- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?  
Sí, podría ser ff porque no hemos hecho más que modificar un feature en una rama sin avanzar la rama master, por lo que siguen en línea y no perderíamos cambios en un hipotético merge ff.
- ¿Qué comando o comandos utilizaste en el paso 27? 
Hacemos un git reset (no hard) al paso anterior con git reset HEAD~1. Me indica que tengo unstaged changes, lo que me da pistas sobre que mi working copy no ha variado (como quería).
- ¿Qué comando o comandos utilizaste en el paso 28? 
Entiendo que se refiere a los cambios del working copy.
Como desconozco el propósito final, he usado git stash, que me descarta los cambios pero me los guarda por si hay que usarlos de nuevo. 
He comprobado que el working copy ha perdido los cambios que originalmente había commited en la rama title, pero de los que he vuelto en el paso anterior con el reset.
He investigado y descubierto que puedo eliminar dicho stash con stash drop cuando quiera. 
- ¿Qué comando o comandos utilizaste en el paso 29? 
git branch -D title
- ¿Qué comando o comandos utilizaste en el paso 30? 
git reflog para saber en qué referencia estaba el paso en el que hicimos el merge. 
He hecho un git reset --hard a la referencia para recuperar el título, aunque creo que es precisamente lo que tenía en el stash por si acaso.
- ¿Qué comando o comandos usaste en el paso 32? 
git reflog
git reset (ref) para volver al estado original manteniendo mi working copy
- ¿Qué comando o comandos usaste en el punto 33?
git reflog (aunque sigo teniéndolo en pantalla)
git reset de la referencia de cuando pusimos título al poema. 
