# Manual CI/CD

## Índice

1. [Integración Continua](#integración-continua)
2. [Implementación de la Integración Continua](#implementación-de-la-integración-continua)

---


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
