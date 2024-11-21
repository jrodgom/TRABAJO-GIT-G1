# TRABAJO-GIT-G1

![image](https://github.com/user-attachments/assets/4f26f1a4-856f-4215-8ec8-4ed764ab9a2a)

## ¿Qué es GIT?
Git es un sistema de control de versiones, cuya principal función es permitir a los desarrolladores gestionar cambios en el código de un proyecto a lo largo del tiempo. Git mantiene un historial de cambios de todos los archivos en un repositorio, lo cual facilita el trabajo colaborativo y la recuperación de versiones anteriores de un proyecto.

Git permite a los desarrolladores colaborar de manera eficiente, manteniendo un registro completo de cada cambio en el código, facilitando la detección y resolución de errores, y ayudando a integrar nuevas funcionalidades sin interferir en el trabajo de los demás.

# Comandos esenciales de Git

## Git init
Sirve para crear un repositorio Git local vacío o reinicializa uno existente. Aunque con git clone (ahora lo veremos) no hace falta porque nos estamos trayendo un repositorio desde la nube.

~~~
git init
~~~

## Clonar repositorio

Para clonar un repositorio desde la nube a local usaremos este comando:

~~~
git clone <url-https>
~~~

## Creación, navegación y borrado de ramas

### Crear rama

Para crear una rama

~~~
git branch <nombre-de-rama>
~~~

O si queremos crearla y movernos a la rama que estamos creando directamente

~~~
git checkout -b <nombre-de-rama>
~~~

### Navegar entre ramas

Para cambiar de rama

~~~
git switch <nombre-de-rama>
~~~

O:

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

## Listado de ramas

Muestra una lista de todas las ramas en el repositorio. La rama actual aparece resaltada con un asterisco *.
~~~
git branch
~~~

Lista todas las ramas, incluidas las remotas.
~~~
git branch -a
~~~

## Add, Status, Commit

Cada vez que queramos guardar un cambio, tendremos que hacer un `git commit`, para ello tendremos que añadir el archivo o directorio que queramos guardar con `git add <nombre>`.

### Add

Selecciona el/los archivos de los que queramos guardar cambios, y se quedarán a la espera de que hagamos un `commit`.

~~~
git add .
~~~

### Status

Para ver los archivos que tenemos seleccionados, pondremos el siguiente comando:

~~~
git status
~~~

Nos saldrán el/los archivos en rojo si no están añadidos con el `git add`. Una vez hecho saldrán en verde.

### Commit

Para guardar los cambios.

~~~
git commit -m "mensaje"
~~~

Usaremos el `-m "mensaje"` para poner una descripción sobre el cambio que se ha realizado.

## Push

Sube los cambios de una rama local al repositorio remoto, permitiendo que otros colaboradores accedan a las últimas modificaciones.

~~~
git push
~~~

Si no tenemos creado en el repositorio remoto la rama, tendremos que poner este comando (si creamos una rama a parte del main, que ya viene creado por defecto en el repositorio remoto):

~~~
git push --set-upstream origin <rama>
~~~

Ya una vez puesto el comando, bastará con poner `git push`, porque el `origin` establece la rama como predeterminada.

## Pull

Descarga y fusiona los cambios desde la rama remota a la rama actual en el repositorio local.

~~~
git pull
~~~

## Merge
Fusiona la rama especificada con la rama actual. Este comando se usa para combinar el trabajo de diferentes ramas en una sola.

Tienes que estar situado en la rama en la que quieras volcar los cambios:

~~~
git merge <nombre-de-rama>
~~~

## Stash
Es como guardar tus apuntes en una "caja temporal" para que puedas despejar tu escritorio y trabajar en algo nuevo. Cuando terminas, puedes abrir la caja y retomar donde lo dejaste.

## Comandos esenciales de `git stash`

| Comando                  | Descripción                                                |
|--------------------------|------------------------------------------------------------|
| `git stash`              | Guarda los cambios actuales en la pila y limpia el área de trabajo. |
| `git stash apply`        | Recupera los cambios más recientes de la pila.             |
| `git stash drop`         | Elimina el stash más reciente de la pila.                  |
| `git stash list`         | Muestra todos los *stashes* almacenados.                   |
| `git stash pop`          | Recupera el stash más reciente y lo elimina de la pila.    |


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
