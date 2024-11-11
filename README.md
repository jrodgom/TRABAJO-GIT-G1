# TRABAJO-GIT-G1

![image](https://github.com/user-attachments/assets/4f26f1a4-856f-4215-8ec8-4ed764ab9a2a)

## ¿Qué es GIT?
Git es un sistema de control de versiones, cuya principal función es permitir a los desarrolladores gestionar cambios en el código de un proyecto a lo largo del tiempo. Git mantiene un historial de cambios de todos los archivos en un repositorio, lo cual facilita el trabajo colaborativo y la recuperación de versiones anteriores de un proyecto.

Git permite a los desarrolladores colaborar de manera eficiente, manteniendo un registro completo de cada cambio en el código, facilitando la detección y resolución de errores, y ayudando a integrar nuevas funcionalidades sin interferir en el trabajo de los demás.

# Comandos esenciales de Git

## Listado de ramas

Muestra una lista de todas las ramas en el repositorio. La rama actual aparece resaltada con un asterisco *.
~~~
git branch
~~~
Lista todas las ramas, incluidas las remotas.
~~~
git branch -a
~~~

## Creación, navegación y borrado de ramas

### Crear rama

Para crear una rama

~~~
git branch <nombre-de-rama>
~~~

o si queremos crearla y movernos a la rama que estamos creando directamente

~~~
git checkout -b <nombre-de-rama>
~~~

### Navegar entre ramas

Para cambiar de rama

~~~
git checkout <nombre-de-rama>
~~~

### Eliminar una rama

Elimina una rama de manera segura si ya ha sido fusionada.

~~~
git branch -d <nombre-de-rama>
~~~

Elimina una rama forzosamente, sin importar si ha sido fusionada o no.

~~~
git branch -D <nombre-de-rama>
~~~

## Push (enviar cambios al repositorio remoto)

Sube los cambios de una rama local al repositorio remoto, permitiendo que otros colaboradores accedan a las últimas modificaciones.

~~~
git push origin <nombre-de-rama> 
~~~

## Pull (obtener cambios del repositorio remoto)

Descarga y fusiona los cambios desde la rama remota a la rama actual en el repositorio local. Es una combinación de fetch y merge.

~~~
git pull
~~~

## Merge (fusionar ramas)
Fusiona la rama especificada con la rama actual. Este comando se usa para combinar el trabajo de diferentes ramas en una sola.

~~~
git merge <nombre-de-rama>
~~~

## Stash (guardar cambios temporalmente)
Guarda temporalmente los cambios sin comprometerlos en el historial. Esto permite cambiar a otra rama sin perder el trabajo actual.

~~~
git stash
~~~

Recupera los cambios guardados con git stash y los aplica a la rama actual, eliminándolos de la pila de stashes.

~~~
git stash pop: 
~~~

## Amend (editar el último commit)
Permite modificar el último commit, ya sea para cambiar su mensaje o agregar archivos omitidos. Es útil para corregir errores en el commit anterior.

~~~
git commit --amend
~~~

## Revert (revertir un commit)
Crea un nuevo commit que revierte los cambios de un commit específico sin alterar el historial. Es una manera segura de deshacer cambios ya compartidos con otros colaboradores.

~~~
git revert <id-del-commit>
~~~

## Cherry-pick (Seleccionar cambios específicos)
Permite aplicar los cambios de un commit específico de otra rama a la rama actual. Es útil para aplicar correcciones o mejoras individuales sin fusionar ramas completas.

~~~
git cherry-pick <id-del-commit>
~~~

## Descargar ramas remotas

~~~
git checkout -b nombre-de-la-rama origin/rama-jose
~~~

## Pull Request
Un Pull Request es una solicitud de integración de cambios en el repositorio principal, especialmente en plataformas como GitHub o GitLab. A través de un Pull Request, los colaboradores pueden revisar, discutir y aprobar cambios antes de integrarlos a la rama principal.

## Provocar un conflicto en un Pull Request
Los conflictos en Git suelen ocurrir cuando dos ramas modifican las mismas líneas de un archivo de forma diferente. Para provocar un conflicto en un Pull Request:

### Crea una rama nueva, haz una modificación en un archivo y crea un commit.
### Cambia a la rama principal o a otra rama y realiza un cambio diferente en el mismo archivo y en la misma línea.
### Intenta hacer un merge o un pull request con estas dos ramas. Git detectará el conflicto y te pedirá que resuelvas las diferencias manualmente antes de continuar.
