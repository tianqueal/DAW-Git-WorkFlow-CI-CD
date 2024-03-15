# Manual CI/CD

## Índice

1. [Integración Continua](#integración-continua)
2. [Implementación de la Integración Continua](#implementación-de-la-integración-continua)

---

## Integración Continua
La integración continua es un proceso de desarrollo de software en el que los desarrolladores integran el código nuevo que han escrito con una mayor frecuencia a lo largo del ciclo de desarrollo, y lo añaden a la base de código al menos una vez al día.
  
### ¿Qué son los Runners y los Pipelines?

  - ***Runners***: Los Runners son agentes de ejecución que ejecutan los trabajos de CI/CD definidos en los archivos de configuración (como ".gitlab-ci.yml") en GitLab. pueden ser compartidos entre varios proyectos o pueden ser específicos para un proyecto en particular, y pueden ser alojados por GitLab o configurados localmente.
  - ***Pipelines***: Los Pipelines son flujos de trabajo automatizados que se definen en archivos de configuración (habitualmente llamados ".gitlab-ci.yml") y que consisten en una serie de etapas y trabajos que deben ejecutarse como parte del proceso de CI/CD. Los Runners se encargan de ejecutar los trabajos definidos en cada etapa, utilizando el entorno y los recursos especificados en la configuración.
  - ***Stages***: Los stages son las etapas individuales dentro de un pipeline. Cada stage puede contener una o varias tareas relacionadas. Por ejemplo, un pipeline puede tener stages para compilar el código, ejecutar pruebas unitarias, realizar pruebas de integración y desplegar la aplicación. Los stages permiten organizar y estructurar el proceso de CI en pasos lógicos y secuenciales.

### Ejemplo de Despliegue
El despliegue como parte de un proceso de integración continua implica automatizar la entrega de código a un entorno de producción después de pasar una serie de pruebas automáticas y manuales. El proceso general incluye:

  1. Desarrollo de código por parte de los desarrolladores.
  2. Activación del proceso de CI cuando se realizan cambios en el repositorio de código.
  3. Ejecución de pruebas automáticas, como pruebas unitarias e integración, análisis de código estático, etc.
  4. Construcción de artefactos de la aplicación, como paquetes binarios y archivos de configuración.
  5. Despliegue en entornos de preproducción para pruebas adicionales.
  6. Despliegue en el entorno de producción una vez que las pruebas en el entorno de preproducción hayan sido exitosas.
  7. Monitorización continua y retroalimentación para mejorar el proceso de CI/CD.

Este enfoque garantiza que los cambios de código se integren y desplieguen de manera rápida y confiable, permitiendo entregas frecuentes y continuas de software de alta calidad.

### Explicación del .yml asociado
El archivo .yml en el contexto de CI/CD es un archivo de configuración YAML utilizado para definir y configurar pipelines de integración continua (CI) o despliegue continuo (CD).
  
En este archivo se especifican los pasos necesarios para automatizar el proceso de construcción, pruebas y despliegue de una aplicación de software. 
  
Los pasos se organizan en forma de "jobs" y "stages", donde cada job puede tener uno o más stages que representan las diferentes fases del proceso. Los ejemplos de configuraciones incluyen clonar el repositorio, compilar el código, ejecutar pruebas, desplegar la aplicación y realizar acciones posteriores, como notificaciones. 
  
El archivo .yml proporciona una manera flexible y fácil de definir y mantener la configuración del pipeline de CI/CD, permitiendo a los equipos automatizar y estandarizar el proceso de desarrollo y despliegue de software.

## Implementación de la Integración Continua

Hugo es un generador de sitios web estáticos que permite crear y mantener sitios web fácilmente.

### Pasos para la implementación

1. **Configuración en GitLab Pages**
   En la configuración del proyecto, se debe habilitar GitLab Pages y elegir una rama para el despliegue de la documentación generada por Hugo.
2. **Creación fichero `.gitlab-ci.yml`**
   En la raíz del proyecto, se debe crear un archivo `.gitlab-ci.yml` que define los jobs necesarios para compilar y desplegar el sitio web generado 
   por Hugo.
   
   ~~~yaml
   image: registry.gitlab.com/pages/hugo:latest
  
   pages:
     script:
     - hugo
     artifacts:
       paths:
       - public
     only:
     - master
   ~~~
   Este archivo indica que se debe usar la imagen de Hugo, compilar el sitio web con hugo, y desplegarlo en GitLab Pages cuando se haga un commit en      la rama master.
3. **Ejecutar Pipeline**: Se puede realizar un commit en el repositorio y observar cómo se ejecuta el pipeline de CI/CD en GitLab. Si todo sale bien,     el sitio web generado por Hugo estará disponible en GitLab Pages.
