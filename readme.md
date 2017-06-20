- �Qu� comando utilizaste en el paso 11? �Por qu�? 
git reset --hard HEAD~1. 
De este modo echo un paso hacia atr�s. El --hard descarta los cambios. ~1, que para este caso es lo mismo que ~, especifica que doy un paso hacia atr�s. 
- �Qu� comando o comandos utilizaste en el paso 12? �Por qu�? 
He hecho un git reflog para ver el commit donde hab�a actualizado el archivo. He copiado la referencia del commit y he vuelto a �l con un git reset --hard, seguido de la referencia que he copiado. El hard, de nuevo, me sirve para modificar mi working copy, donde puedo comprobar si ha funcionado. 
- El merge del paso 13, �Caus� alg�n con?icto? �Por qu�? 
No, ya que los cambios de la rama styled son nuevos respecto a la rama master. Git se queda con los de styled, ya que son m�s nuevos.
- El merge del paso 19, �Caus� alg�n con?icto? �Por qu�? 
S�, porque hemos modificado exactamente las mismas l�neas en dos archivos que pretendemos fusionar (merge). 
De haber sido simples cambios en la misma rama no habr�a habido conflicto ninguno (unos ser�an m�s nuevos que los otros), pero al tratarse de merge, git no sabe a qu� archivo dar prioridad. 
- El merge del paso 21, �Caus� alg�n con?icto? �Por qu�? 
No, porque nos hemos quedado con el contenido de la rama styled en el �ltimo merge. Como styled estaba en l�nea con master, ha sido un fast forwards.
- �Qu� comando o comandos utilizaste en el paso 25?
He utilizado git config alias.graph "log --graph --decorate --pretty=oneline"
seguido de git graph.
Este sistema muestra un diagrama aproximado de la situaci�n de cada rama en funci�n de los commits que hemos hecho. Es la forma m�s fidedigna (que conozco) de dibujar la estructura de nuestro repo sin usar SourceTree.
- El merge del paso 26, �Podr�a ser fast forward? �Por qu�?  
S�, podr�a ser ff porque no hemos hecho m�s que modificar un feature en una rama sin avanzar la rama master, por lo que siguen en l�nea y no perder�amos cambios en un hipot�tico merge ff.
- �Qu� comando o comandos utilizaste en el paso 27? 
Hacemos un git reset (no hard) al paso anterior con git reset HEAD~1. Me indica que tengo unstaged changes, lo que me da pistas sobre que mi working copy no ha variado (como quer�a).
- �Qu� comando o comandos utilizaste en el paso 28? 
Entiendo que se refiere a los cambios del working copy.
Como desconozco el prop�sito final, he usado git stash, que me descarta los cambios pero me los guarda por si hay que usarlos de nuevo. 
He comprobado que el working copy ha perdido los cambios que originalmente hab�a commited en la rama title, pero de los que he vuelto en el paso anterior con el reset.
He investigado y descubierto que puedo eliminar dicho stash con stash drop cuando quiera. 
- �Qu� comando o comandos utilizaste en el paso 29? 
git branch -D title
- �Qu� comando o comandos utilizaste en el paso 30? 
git reflog para saber en qu� referencia estaba el paso en el que hicimos el merge. 
He hecho un git reset --hard a la referencia para recuperar el t�tulo, aunque creo que es precisamente lo que ten�a en el stash por si acaso.
- �Qu� comando o comandos usaste en el paso 32? 
git reflog
git reset (ref) para volver al estado original manteniendo mi working copy
- �Qu� comando o comandos usaste en el punto 33?
git reflog (aunque sigo teni�ndolo en pantalla)
git reset de la referencia de cuando pusimos t�tulo al poema. 
