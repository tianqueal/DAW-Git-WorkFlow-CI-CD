# ![Imagen de Git](../assets/Git_icon.svg "Git") Manual Git

Git es un sistema de control de versiones distribuido que permite realizar un seguimiento de los cambios en archivos en un periodo de tiempo, coordinar el trabajo con otras personas y revertir los archivos a estados anteriores cuando sea necesario.

## Índice

1. [Sistema de control de versiones](#sistema-de-control-de-versiones)

2. [¿Qué es Git?](#qué-es-git)
   - [Git como la mejor alternativa](#git-como-la-mejor-alternativa)
   - [Funcionamiento externo de Git](#funcionamiento-externo-de-git)
   - [Extructura interna de Git](#extructura-interna-de-git)
  
3. [Setup y Configuración](#setup-y-configuración)
   - git
   - config

4. [Obtención y creación de proyectos](#obtención-y-creación-de-proyectos)
   - init
   - clone

5. [Instantáneas básicas](#instantáneas-básicas)
   - add
   - status
   - diff
   - commit
   - reset

6. [Ramificación y fusión](#ramificación-y-fusión)
   - branch
   - checkout
   - switch
   - merge
   - log
   - tag
   - stash

7. [Compartir y actualizar](#compartir-y-actualizar)
   - fetch
   - pull
   - push
   - remote
8. [Inspección y comparación](#inspección-y-comparación)
   - diff
  
9. [Patching](#patching)
   - cherry-pick

---

## Sistema de control de versiones

Un sistema de control de versiones (VCS) es una herramienta que ayuda a gestionar y controlar los cambios realizados en archivos y carpetas a lo largo del tiempo en un proyecto de software u otro tipo de desarrollo. 
Estos sistemas registran cada modificación realizada en los archivos, lo que permite a los desarrolladores rastrear quién hizo qué cambio, cuándo se realizó y por qué.

## ¿Qué es Git?

### Git como la mejor alternativa

Git se considera uno de los mejores sistemas de control de versiones por varias razones. Se distribuye para que todos los desarrolladores tengan una copia completa del historial de cambios localmente. La gestión de sucursales es rápida y eficiente, y se conserva el historial completo, lo que facilita la detección de cambios y la reversión a versiones anteriores. 

Existen herramientas y servicios complementarios como GitHub, GitLab y Bitbucket que amplían la funcionalidad. En conjunto, estas características hacen de Git una opción sólida y versátil para el control de versiones en proyectos de desarrollo. 

### Funcionamiento externo de Git

Git puede gestionarse de varias maneras desde una perspectiva externa al sistema mismo. 

1. **Terminal de comandos**: Los usuarios pueden interactuar con Git a través de la línea de comandos utilizando una variedad de comandos específicos de Git. Estos comandos permiten realizar operaciones como clonar un repositorio, agregar y confirmar cambios, fusionar ramas, crear etiquetas y más. 

2. **Interfaces gráficas de usuario (GUI)**: Existen diversas herramientas que proporcionan interfaces gráficas para gestionar repositorios Git de forma visual. Estas herramientas, como GitKraken, Sourcetree y GitHub Desktop, ofrecen una forma más accesible de realizar operaciones de control de versiones sin necesidad de utilizar la línea de comandos. 

3. **Integración en herramientas de desarrollo**: Muchas herramientas de desarrollo, como Visual Studio Code, IntelliJ IDEA y Eclipse, ofrecen integración nativa con Git. Esto permite a los desarrolladores realizar operaciones de control de versiones directamente desde el entorno de desarrollo, lo que facilita la gestión del código fuente dentro del flujo de trabajo de desarrollo.

### Extructura interna de Git

1. HEAD:
   - Puntero al último commit en la rama actual.

2. Objects:
   - Almacena objetos fundamentales de Git como blobs (datos), trees (estructuras de directorios) y commits.

3. Refs:
   - Contiene referencias a commits específicos, ramas y etiquetas.

4. Config:
   - Archivo que guarda la configuración del repositorio.

5. Hooks:
   - Carpeta que contiene scripts ejecutados en eventos específicos de Git.

6. Index:
   - Archivo que actúa como área de preparación para los cambios antes de realizar un commit.

7. Logs:
   - Almacena información de registro.

8. Configuración Global y Local:
   - Archivos que contienen configuraciones a nivel global y local respectivamente.

9. .gitignore:
   - Archivo que especifica patrones de archivos/directorios que Git debe ignorar al rastrear cambios. Se utiliza para            excluir archivos temporales, compilados, logs, etc.
  
     ~~~
      # Ignorar directorios de dependencias o entornos virtuales
      node_modules/
      venv/
     ~~~

La carpeta .git junto con .gitignore son esenciales para el funcionamiento interno y la organización del repositorio en Git.

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
