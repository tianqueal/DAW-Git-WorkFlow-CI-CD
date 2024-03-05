# Manual Git

## Setup and Config

- git
- config

## Getting and Creating Projects

- init
- clone

## Basic Snapshotting

- add
- status
- diff
- commit
- reset

## Branching and Merging

- branch
- checkout
- switch
- merge
- log
- tag
- stash

## Sharing and Updating

- fetch
- pull
- push
- remote

## Inspection and Comparison

- diff

## Patching

- cherry-pick

## Setup y Configuración

| Comando | Descripción |
|---------|-------------|
| `git -v` `git --version`|Muestra la versión actual de Git instalada en el sistema|

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
