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

---

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
