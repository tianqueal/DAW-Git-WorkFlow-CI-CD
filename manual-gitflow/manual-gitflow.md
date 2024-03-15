# ![Imagen de GitFlow](../assets/git-flow.png "GitFlow") Manual GitFlow

## Índice

1. [¿Qué es GitFlow?](#qué-es-gitflow)
   - [Ventajas, necesidades y motivos](ventajas-necesidades-y-motivos)

2. [Workflows alternativos](#workflows-alternativos)
   - [...](#...)
   - [...](#...)
   - [...](#...)
  
3. [Funcionamiento de GitFlow](#funcionamiento-de-gitflow)

4. [Comandos de GitFlow](#comandos-de-gitflow)
   - ...
   - ...

---

## ¿Qué es GitFlow?

## Workflows alternativos

## Funcionamiento de GitFlow

Se basa en dos ramas principales: `master` y `develop` (o `dev`).

1. **Master**:
   La rama `master` es estable y siempre contiene el código en producción. Se considera la versión más reciente y estable del proyecto.

2. **Develop**:
   La rama `develop` es donde se integran todas las características nuevas. Es menos estable que master, pero se utiliza para pruebas y desarrollo
   continuo.

El flujo de trabajo típico de GitFlow implica varias ramas adicionales:

- **Feature Branches (ramas de características)**:
  Se crean a partir de `develop` y se utilizan para desarrollar nuevas características. Una vez completadas, se fusionan de nuevo en `develop`.

- **Release Branches (ramas de lanzamiento)**:
  Se crean a partir de `develop` cuando se está preparando una nueva versión para lanzamiento. Aquí se realizan correcciones de errores y ajustes
  finales antes de la publicación. Una vez listo, se fusiona tanto en `master` como en `develop`, y se etiqueta con un número de versión.

- **Hotfix Branches (ramas de corrección de errores)**:
  Se crean a partir de `master` y se utilizan para corregir errores críticos en producción. Después de solucionar el problema, se fusionan tanto en
  `master` como en `develop`.

Este flujo de trabajo permite un desarrollo estructurado, con versiones estables en `master`, desarrollo continuo en `develop`, y características y correcciones de errores gestionadas de forma ordenada en ramas separadas.

![Imagen de las ramas GitFlow](../assets/git-flow-works.svg "Ramas GitFlow")

## Comandos de GitFlow

1. **Inicializar GitFlow en un repositorio**
   ~~~
   git flow init
   ~~~
   Este comando inicializa GitFlow en el repositorio actual, creando las ramas `master` y `develop` y configurando el flujo de trabajo.
   
2. **Crear una nueva rama de característica (feature)**
   ~~~
   git flow feature start <nombre_caracteristica>
   ~~~
   Crea una nueva rama de característica basada en `develop`, donde puedes trabajar en una nueva funcionalidad.
   
3. **Finalizar una característica**
   ~~~
   git flow feature finish <nombre_caracteristica>
   ~~~
   Fusiona la rama de característica en `develop` y la elimina.
   
4. **Crear una nueva rama de lanzamiento (release)**
   ~~~
   git flow release start <nombre_version>
   ~~~
   Crea una nueva rama de lanzamiento basada en `develop`, donde puedes realizar correcciones finales antes del lanzamiento.

5. **Finalizar un lanzamiento**
   ~~~
   git flow release finish <nombre_version>
   ~~~
   Fusiona la rama de lanzamiento en `master` y `develop`, estableciendo una nueva versión. También elimina la rama de lanzamiento.

6. **Crear una nueva rama de corrección de errores (hotfix)**
   ~~~
   git flow hotfix start <nombre_correccion>
   ~~~
   Crea una nueva rama de corrección de errores basada en `master`, para abordar problemas críticos en producción.

7. **Finalizar una corrección de errores**
   ~~~
   git flow hotfix finish <nombre_correccion>
   ~~~
   Fusiona la rama de corrección de errores en `master` y `develop`, y elimina la rama de corrección de errores.
   
