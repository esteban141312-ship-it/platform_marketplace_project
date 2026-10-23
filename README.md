# Platform Marketplace

## Descripción del proyecto

Platform Marketplace es un proyecto de desarrollo de software que busca construir una plataforma de comercio electrónico tipo marketplace.

Este repositorio contiene el código fuente y los archivos necesarios para el desarrollo colaborativo del proyecto.

## Repositorio

Repositorio oficial de GitHub:

https://github.com/esteban141312-ship-it/platform_marketplace_project.git

## Requisitos

Antes de comenzar, cada integrante debe tener instalado:

* Git.
* Git Bash.
* Visual Studio Code u otro editor de código.
* PHP y Composer, cuando sean necesarios para trabajar con Laravel.
* Las demás herramientas  se definiran durante el desarrollo.

## 1. Clonar el repositorio

Cada integrante debe clonar el repositorio en su equipo, para eso se hace lo siguiente:

Abrir Git Bash y ejecutar:

```bash
git clone https://github.com/esteban141312-ship-it/platform_marketplace_project.git
```

Entrar en la carpeta del proyecto:

```bash
cd platform_marketplace_project
```

## 2. Actualizar el proyecto

Antes de comenzar a trabajar, se deben descargar los cambios más recientes de la rama principal.

```bash
git switch main
git pull origin main
```

## 3. Crear una rama de trabajo

**Cada integrante debe trabajar en una rama independiente. No se deben realizar cambios directamente en `main`.**

El nombre de la rama debe indicar el área del proyecto en la que se está trabajando y, preferiblemente, la tarea que se va a desarrollar.

Se utilizarán las siguientes convenciones:

| Área                  | Prefijo     | Ejemplo                       |
| --------------------- | ----------- | ----------------------------- |
| Backend               | `backend/`  | `backend/login`               |
| Frontend              | `frontend/` | `frontend/catalogo-productos` |
| Base de datos         | `database/` | `database/modelo-usuarios`    |
| Documentación         | `docs/`     | `docs/instalacion`            |
| Corrección de errores | `fix/`      | `fix/validacion-login`        |
|

### Ejemplos

Si se va a trabajar en el backend:

```bash
git switch -c backend/login
```

Si se va a trabajar en el frontend:

```bash
git switch -c frontend/catalogo-productos
```

Si se va a trabajar en la base de datos:

```bash
git switch -c database/modelo-usuarios
```

Si se va a documentar el proyecto:

```bash
git switch -c docs/instalacion
```


**Importante:** cada integrante debe crear su propia rama. Si dos personas trabajan en la misma área, deben utilizar nombres diferentes que identifiquen sus tareas o colocarles su nombre, la -c que se coloca significa create, se debe colocar  cada vez que se vaya a crear una rama nueva y moverse de una vez a ella, otra forma seria primero crear una rama utilizando branch, por ejemplo "git branch backend/login" para luego utilizar el switch y cambiar a ella  .

## 4. Realizar cambios en el código

Después de crear la rama, se pueden realizar los cambios correspondientes a la tarea asignada.

Consultar el estado de los archivos modificados:

```bash
git status
```

Agregar los cambios:

```bash
git add .
```

Crear un commit con un mensaje descriptivo:

```bash
git commit -m " agregar funcionalidad de login"
```

Ejemplos de mensajes para los commits:

* `feat: agregar registro de usuarios`
* `fix: corregir validacion del formulario`
* `docs: actualizar documentacion`
* `style: mejorar estilos del catalogo`
* `test: agregar pruebas de autenticacion`

Los mensajes de los commits deben describir los cambios realizados.

## 5. Subir la rama a GitHub

Para publicar la rama y sus cambios en GitHub, ejecutar:

```bash
git push -u origin nombre-de-rama
```

Por ejemplo:

```bash
git push -u origin backend/login
```

Cada integrante debe reemplazar `nombre-de-rama` por el nombre de su propia rama.
la -u es para que se cree la rama por peimera vez, despues de crearse no es necesario colocar el -u solo el git push origin nombre-de-rama.
cabe recalcar que no se deben hacer cambios en la rama main.

## 6. Crear un Pull Request
**Importante:**: solo haran los cambios los encargados de unir todas las ramas a la rama principal, por lo tanto esta parte solo es informativa y no deben hacer cambios otros grupos, para mayor seguridad se agrego una ruleset al repositorio para que los pullrequest solo lo puedan hacer ciertos roles o grupos.

**Esta parte solo lo hacen los devops**
Después de subir la rama a GitHub:

1. Ingresar al repositorio en GitHub.
2. Seleccionar la opción **Compare & pull request**, si aparece, o crear un Pull Request manualmente.
3. Seleccionar como rama de origen la rama en la que se trabajó.
4. Seleccionar `main` como rama de destino.
5. Escribir un título descriptivo.
6. Explicar brevemente los cambios realizados.
7. Crear el Pull Request.

El Pull Request permite revisar los cambios antes de integrarlos en la rama principal.



**No se deben integrar cambios directamente en `main`.** Todos los cambios deben seguir el proceso de Pull Request establecido para el equipo.


## 7. Revisar y aprobar los cambios

Los Pull Requests deben revisarse antes de integrar los cambios.

Los responsables designados del repositorio serán los encargados de revisar y autorizar la integración de los cambios en `main`.

Si se solicitan modificaciones, el autor debe realizarlas en su misma rama:

```bash
git add .
git commit -m "fix: corregir observaciones del pull request"
git push
```

Los nuevos cambios aparecerán en el Pull Request existente.

## 8. Actualizar la rama de trabajo

Si otros integrantes han integrado cambios en `main` mientras trabajabas, puedes actualizar tu rama de la siguiente manera.

Primero, guarda y confirma tus cambios pendientes. Después, ejecuta:

```bash
git fetch origin 
```
Descarga la información más reciente del repositorio de GitHub, incluidas las actualizaciones de sus ramas
Importante: no modifica directamente tus archivos de trabajo ni combina los cambios con su rama actual.

Por ejemplo, un compañero agregó una nueva funcionalidad y ya la integraron en main. Con fetch, su Git detecta esa actualización.

```bash
git switch main

```
cambia a la rama main local
```bash
git pull origin main
```
Descarga e integra en su main local los cambios que existen en la rama main de GitHub.
```bash
git switch nombre-de-rama

```
cambia a su rama ya creada
```bash
git merge main
```
Este comando incorpora a su rama de trabajo los cambios que acabas de descargar en main.

Si aparecen conflictos, deben resolverse antes de continuar.

Finalmente, se sube los cambios actualizados:

```bash
git push
```

## 9. Reglas de trabajo del equipo

1. La rama `main` es la rama principal del proyecto.
2. No se deben realizar cambios directamente en `main`.
3. Cada integrante debe trabajar en una rama independiente.
4. Los nombres de las ramas deben identificar el área o el tipo de trabajo.
5. Si dos integrantes trabajan en la misma área, deben crear ramas con nombres diferentes.
6. Los commits deben tener mensajes descriptivos.
7. Los cambios deben subirse a GitHub mediante `git push`.
8. Para integrar cambios en `main`, se debe crear un Pull Request.
9. Los Pull Requests deben revisarse antes de su integración.
10. Se debe actualizar el proyecto antes de comenzar una nueva tarea.
11. No se deben subir contraseñas, claves privadas ni otros datos sensibles al repositorio.

## 10. Flujo de trabajo resumido

Cada integrante debe seguir este proceso:

1. Actualizar `main`.
2. Crear una rama según su área de trabajo.
3. Desarrollar la tarea asignada.
4. Guardar los cambios mediante commits.
5. Subir la rama a GitHub.
6. Crear un Pull Request hacia `main`.
7. Esperar la revisión y aprobación.
8. Integrar los cambios cuando sean autorizados.

### Comandos principales

```bash
# Actualizar main
git switch main
git pull origin main

# Crear una rama según el área de trabajo
git switch -c backend/nombre-de-la-tarea

# Revisar cambios
git status

# Preparar y confirmar cambios
git add .
git commit -m "feat: descripcion del cambio"

# Subir la rama a GitHub
git push -u origin backend/nombre-de-la-tarea
```

**Nota:** los ejemplos con `backend/` deben cambiarse por el prefijo correspondiente al área de trabajo de cada integrante.

## Objetivo del flujo de trabajo

Este procedimiento busca facilitar el trabajo colaborativo, mantener organizado el código fuente y proteger la rama principal del proyecto.

Todos los integrantes deben respetar el flujo de trabajo acordado para reducir conflictos y facilitar la revisión de los cambios.
