# TRABAJO-GIT-G1

![image](https://github.com/user-attachments/assets/4f26f1a4-856f-4215-8ec8-4ed764ab9a2a)

## ¿Qué es GIT?
Git es un sistema de control de versiones, cuya principal función es permitir a los desarrolladores gestionar cambios en el código de un proyecto a lo largo del tiempo. Git mantiene un historial de cambios de todos los archivos en un repositorio, lo cual facilita el trabajo colaborativo y la recuperación de versiones anteriores de un proyecto.

Git permite a los desarrolladores colaborar de manera eficiente, manteniendo un registro completo de cada cambio en el código, facilitando la detección y resolución de errores, y ayudando a integrar nuevas funcionalidades sin interferir en el trabajo de los demás.

# Comandos esenciales de Git

## Listado de ramas

git branch: Muestra una lista de todas las ramas en el repositorio. La rama actual aparece resaltada con un asterisco *.
git branch -a: Lista todas las ramas, incluidas las remotas.


## Borrado de ramas


git branch -d <nombre-de-rama>: Elimina una rama de manera segura si ya ha sido fusionada.
git branch -D <nombre-de-rama>: Elimina una rama forzosamente, sin importar si ha sido fusionada o no.

## Enviar cambios al repositorio remoto (push)

git push origin <nombre-de-rama>: Sube los cambios de una rama local al repositorio remoto, permitiendo que otros colaboradores accedan a las últimas modificaciones.

## Obtener cambios del repositorio remoto (pull)
git pull: Descarga y fusiona los cambios desde la rama remota a la rama actual en el repositorio local. Es una combinación de fetch y merge.

## Fusionar ramas (merge)
git merge <nombre-de-rama>: Fusiona la rama especificada con la rama actual. Este comando se usa para combinar el trabajo de diferentes ramas en una sola.

## Guardar cambios temporalmente (stash)
git stash: Guarda temporalmente los cambios sin comprometerlos en el historial. Esto permite cambiar a otra rama sin perder el trabajo actual.
git stash pop: Recupera los cambios guardados con git stash y los aplica a la rama actual, eliminándolos de la pila de stashes.

## Editar el último commit (amend)
git commit --amend: Permite modificar el último commit, ya sea para cambiar su mensaje o agregar archivos omitidos. Es útil para corregir errores en el commit anterior.

## Revertir un commit (revert)
git revert <id-del-commit>: Crea un nuevo commit que revierte los cambios de un commit específico sin alterar el historial. Es una manera segura de deshacer cambios ya compartidos con otros colaboradores.

## Seleccionar cambios específicos (cherry-pick)
git cherry-pick <id-del-commit>: Permite aplicar los cambios de un commit específico de otra rama a la rama actual. Es útil para aplicar correcciones o mejoras individuales sin fusionar ramas completas.

## Pull Request
Un Pull Request (PR) es una solicitud de integración de cambios en el repositorio principal, especialmente en plataformas como GitHub o GitLab. A través de un PR, los colaboradores pueden revisar, discutir y aprobar cambios antes de integrarlos a la rama principal.

## Cómo provocar un conflicto en un Pull Request
Los conflictos en Git suelen ocurrir cuando dos ramas modifican las mismas líneas de un archivo de forma diferente. Para provocar un conflicto en un Pull Request:

Crea una rama nueva, haz una modificación en un archivo y crea un commit.
Cambia a la rama principal o a otra rama y realiza un cambio diferente en el mismo archivo y en la misma línea.
Intenta hacer un merge o un pull request con estas dos ramas. Git detectará el conflicto y te pedirá que resuelvas las diferencias manualmente antes de continuar.
