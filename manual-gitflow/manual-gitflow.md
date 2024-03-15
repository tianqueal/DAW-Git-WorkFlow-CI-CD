# ![Imagen de GitFlow](../assets/git-flow.png "GitFlow") Manual GitFlow

## Índice

1. [¿Qué es GitFlow](#qué-es-gitflow)
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
   Gitflow es un modelo alternativo de creación de ramas en Git en el que se utilizan ramas de función y varias ramas principales.

   1.1 Ventajas:
   - Proporciona una estructura clara para el desarrollo y la gestión de versiones.
   - Facilita la colaboración en equipos grandes.
   - Permite la implementación de nuevas características sin afectar la rama principal hasta que estén listas.

## Workflows alternativos
   1.1 GitHub Flow:
   - Enfoque simplificado que se centra en despliegues continuos y entregas rápidas.
   - Ideal para proyectos pequeños o equipos que desean un proceso de desarrollo más ágil y continuo.

   1.2 GitLab Flow:
   - Similar a GitHub Flow pero con una rama adicional llamada "production".
   - Adecuado para proyectos que requieren una etapa de preproducción antes de la implementación en producción.

   1.3 GitLab CI/CD:
   - Utiliza GitLab para la integración continua y la entrega continua (CI/CD).
   - Proporciona una forma automatizada y controlada de implementar y entregar cambios de manera continua.

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