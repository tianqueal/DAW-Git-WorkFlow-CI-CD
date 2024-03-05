# Manual Git

Git es un sistema de control de versiones distribuido que permite realizar un seguimiento de los cambios en archivos a lo largo del tiempo, coordinar el trabajo con otras personas y revertir los archivos a estados anteriores cuando sea necesario. Es una herramienta esencial para cualquier desarrollador de software o equipo de desarrollo colaborativo.

## [Setup y Configuración](#setup-y-configuración-1)

- git
- config

## [Obtención y creación de proyectos](#obtención-y-creación-de-proyectos-1)

- init
- clone

## [Instantáneas básicas](#instantáneas-básicas-1)

- add
- status
- diff
- commit
- reset

## [Ramificación y fusión](#ramificación-y-fusión-1)

- branch
- checkout
- switch
- merge
- log
- tag
- stash

## [Compartir y actualizar](#compartir-y-actualizar-1)

- fetch
- pull
- push
- remote

## [Inspección y comparación](#inspección-y-comparación-1)

- diff

## [Patching](#patching-1)

- cherry-pick

## Setup y Configuración

| Comando | Descripción |
|---------|-------------|
| `git -v` `git --version`|Muestra la versión actual de Git instalada en el sistema|
|`git -config [--global]`|Permite configurar opciones específicas del usuario, tanto de forma global como local en un determinado directorio|
|`git config [--global] user.name "Usuario"`|Establece el nombre del usuario|
|`git config [--global] user.email "usuario@example.com"`|Establece el correo electrónico del usuario|
|`git config [--global] alias.<comando> checkout`|Crea un alias para un comando en concreto (se debe omitir el prefijo `git`)|

Cuando se inicia Git por primera vez en un sistema, es importante **configurar el nombre y dirección de correo electrónico**. Estos detalles se utilizan para identificar al autor de los cambios en el historial del repositorio. Cuando se realiza un commit, Git registra esta información junto con los cambios realizados.

## Obtención y creación de proyectos

| Comando | Descripción |
|---------|-------------|
| `git init`|Crea un repositorio Git vacío. Se creará una rama inicial sin ningún commit.|
| `git clone`|Clona un repositorio en un directorio nuevo creado y crea ramas de seguimiento remoto para cada rama en el repositorio clonado.|

## Instantáneas Básicas

| Comando | Descripción |
|---------|-------------|
| `git add`|Este comando actualiza el índice utilizando el contenido actual que se encuentra en el árbol de trabajo, para preparar el contenido preparado para el siguiente commit.|
| `git status`|Muestra las rutas que tienen diferencias entre el archivo índice y el commit HEAD actual y las rutas que tienen diferencias entre el árbol de trabajo y el archivo índice.|
| `git diff`|Muestra los cambios entre el árbol de trabajo y el índice o un árbol, los cambios resultantes de una fusión y los cambios entre dos archivos en disco.|
| `git commit`|Crea un nuevo commit que contiene el contenido actual del índice y el mensaje de registro dado que describe los cambios.|
| `git reset`|Deshace commits que no han sido enviados a un repositorio remoto. Puede usarse para eliminar commits que contienen errores o que ya no son necesarios.|

## Ramificación y fusión
| Comando | Descripción | Ejemplo |
|---------|-------------|---------|
|`git branch`| Lista todas las ramas del repositorio| `git branch --list`|
|`git branch <nombre>`| Crea una nueva rama con el nombre especificado| `git branch nueva_rama`|
|`git branch -d <rama>`| Elimina la rama especificada de forma segura| `git branch -d rama_antigua`|
|`git branch -m <nombre>`| Renombra la rama actual con el nuevo nombre| `git branch -m nuevo_nombre`|
|`git checkout <rama>`| Cambia a la rama especificada| `git checkout feature1`|
|`git switch <rama>`| Cambia a la rama especificada (versión Git 2.23 o posterior)| `git switch feature2`|
|`git merge <rama>`| Fusiona la rama especificada con la rama actual| `git merge feature1`|
|`git log [<opciones>]`| Muestra el historial de confirmaciones| `git log --oneline`|
|`git tag <nombre>`| Crea un tag para la confirmación actual| `git tag v1.0.0`|
|`git stash`| Guarda temporalmente los cambios no comprometidos| `git stash`|
|`git stash apply [<indice>]`| Aplica los cambios almacenados por `git stash`| `git stash apply`|
|`git stash list`| Lista todos los sets de cambios guardados| `git stash list`|
|`git stash drop [<indice>]`| Elimina un set de cambios guardado específico| `git stash drop stash@{1}`|

## Compartir y actualizar

| Comando | Descripción |
|---------|-------------|
| `git fetch`|Obtiene ramas y/o etiquetas de uno o más repositorios, junto con los objetos necesarios para completar sus historiales.|
| `git pull`|Incorpora los cambios de un repositorio remoto a la rama actual. Si la rama actual está por detrás de la remota, entonces por defecto adelantará la rama actual para que coincida con la remota.|
| `git push`|Actualiza refs remotas usando refs locales, mientras envía los objetos necesarios para completar las refs dadas.|
| `git remote`|Gestiona el conjunto de repositorios ("remotos") cuyas ramas rastrea.|

## Inspección y Comparación

| Comando | Descripción | Ejemplo |
|---------|-------------|---------|
|`git diff [opciones] <referencia> <referencia>`|Muestra las diferencias entre dos puntos en la historia del repositorio|`git diff --staged` `git diff HEAD~1 HEAD`|
|`git diff [opciones] <archivo>`|Muestra las diferencias específicas de un archivo|`git diff archivo.txt`|
|`git diff --color`|Resalta las diferencias con colores para una mejor visualización|`git diff --color`|
|`git diff --name-only`|Muestra solo los nombres de los archivos con diferencias|`git diff --name-only`|
|`git diff --stat`|Muestra estadísticas resumidas de las diferencias|`git diff --stat`|

El comando `git diff` puede mostrar las diferencias entre la zona de trabajo y el área de preparación (staging), entre el área de preparación y la última confirmación, o entre dos confirmaciones específicas, entre otras opciones.

## Patching

| Comando | Descripción |
|---------|-------------|
| `git cherry-pick`|Dados uno o más commits existentes, aplica el cambio que cada uno introduce, registrando un nuevo commit para cada uno.|
