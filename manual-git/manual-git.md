# Manual Git

Git es un sistema de control de versiones distribuido que permite realizar un seguimiento de los cambios en archivos a lo largo del tiempo, coordinar el trabajo con otras personas y revertir los archivos a estados anteriores cuando sea necesario. Es una herramienta esencial para cualquier desarrollador de software o equipo de desarrollo colaborativo.

## [Setup y Configuración](#setup-y-configuración-1)

- git
- config

## [Obtención y creación de proyectos](#obtencion-y-creacion-de-proyectos-1)

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
|`git -config [--global]`||

## Obtención y creación de proyectos

| Comando | Descripción |
|---------|-------------|
| `git init`|Crea un repositorio Git vacío. Se creará una rama inicial sin ningún commit.|
| `git clone`|Clona un repositorio en un directorio nuevo creado y crea ramas de seguimiento remoto para cada rama en el repositorio clonado.|

## Instántaneas Básicas

| Comando | Descripción |
|---------|-------------|
| `git add`|Este comando actualiza el índice utilizando el contenido actual que se encuentra en el árbol de trabajo, para preparar el contenido preparado para el siguiente commit.|
| `git status`|Muestra las rutas que tienen diferencias entre el archivo índice y el commit HEAD actual y las rutas que tienen diferencias entre el árbol de trabajo y el archivo índice.|
| `git diff`|Muestra los cambios entre el árbol de trabajo y el índice o un árbol, los cambios resultantes de una fusión y los cambios entre dos archivos en disco.|
| `git commit`|Crea un nuevo commit que contiene el contenido actual del índice y el mensaje de registro dado que describe los cambios.|
| `git reset`|Deshace commits que no han sido enviados a un repositorio remoto. Puede usarse para eliminar commits que contienen errores o que ya no son necesarios.|
