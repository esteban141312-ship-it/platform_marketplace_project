# Platform Marketplace Project

## 1. Descripción del proyecto

El presente repositorio contiene el desarrollo del proyecto **Platform Marketplace**, realizado de manera colaborativa mediante Git y GitHub para gestionar el código fuente, organizar las tareas y mantener un control de versiones adecuado.

Para facilitar el trabajo en equipo, se utilizarán ramas independientes para desarrollar funcionalidades, corregir errores y actualizar la documentación. Los cambios se propondrán mediante Pull Requests antes de integrarse en la rama principal `main`.

**Repositorio:** https://github.com/esteban141312-ship-it/platform_marketplace_project

## 2. Requisitos

Para trabajar en el proyecto, es necesario contar con los siguientes elementos:

* Git instalado en el equipo.
* Una cuenta de GitHub con acceso al repositorio.
* Visual Studio Code u otro editor de código.
* Las herramientas y dependencias requeridas por el proyecto.

## 3. Clonación del repositorio

Para descargar el repositorio en un equipo local, se debe ejecutar el siguiente comando en una terminal:

```bash
git clone https://github.com/esteban141312-ship-it/platform_marketplace_project.git
```

Posteriormente, se debe ingresar al directorio del proyecto:

```bash
cd platform_marketplace_project
```

Para abrir el proyecto en Visual Studio Code, se puede utilizar el siguiente comando:

```bash
code .
```

Si el repositorio ya se encuentra descargado en el equipo, no es necesario realizar nuevamente la clonación.

## 4. Actualización de la rama principal

Antes de iniciar una nueva tarea, se recomienda actualizar la rama principal para disponer de los últimos cambios publicados en GitHub.

Primero, se debe cambiar a la rama `main`:

```bash
git switch main
```

Después, se deben descargar e integrar los cambios remotos:

```bash
git pull origin main
```

**Importante:** el desarrollo de funcionalidades debe realizarse en ramas independientes. Se debe evitar la modificación directa de la rama `main`.

## 5. Creación de ramas nuevas

Cada integrante debe trabajar en una rama relacionada con la tarea asignada.

Para crear una rama y cambiar automáticamente a ella, se utiliza el siguiente comando:

```bash
git switch -c nombre-de-la-rama
```

Por ejemplo:

```bash
git switch -c backend/login
```

Este comando crea una rama denominada `backend/login` y establece dicha rama como la activa.

También es posible realizar esta operación en dos pasos:

```bash
git branch backend/login
git switch backend/login
```

### 5.1. Convención para nombrar las ramas

Se recomienda utilizar nombres descriptivos que permitan identificar el tipo de trabajo realizado.

| Prefijo     | Descripción                                | Ejemplo                       |
| ----------- | ------------------------------------------ | ----------------------------- |
| `backend/`  | Desarrollo de funcionalidades del servidor | `backend/login`               |
| `frontend/` | Desarrollo de la interfaz de usuario       | `frontend/catalogo-productos` |
| `database/` | Modificaciones en la base de datos         | `database/modelo-usuarios`    |
| `docs/`     | Actualización de la documentación          | `docs/instalacion`            |
| `fix/`      | Corrección de errores                      | `fix/validacion-login`        |
| `test/`     | Desarrollo de pruebas                      | `test/autenticacion`          |

Los nombres de las ramas deben ser claros y representar la tarea correspondiente.

## 6. Trabajo con ramas existentes en GitHub

En determinadas situaciones, un integrante puede necesitar trabajar en una rama que ya fue creada y publicada en GitHub por otro miembro del equipo. En estos casos, no es necesario crear una rama adicional.

### 6.1. Consulta de las ramas disponibles

Primero, se debe actualizar la información de las ramas remotas:

```bash
git fetch origin
```

A continuación, se pueden consultar las ramas locales y remotas:

```bash
git branch -a
```

Las ramas remotas aparecen identificadas con el formato:

```text
remotes/origin/nombre-de-la-rama
```

Por ejemplo:

```text
remotes/origin/backend
remotes/origin/frontend
remotes/origin/main
```

### 6.2. Descarga de una rama remota por primera vez

Si la rama existe en GitHub, pero todavía no existe en el equipo local, se debe ejecutar:

```bash
git switch --track origin/backend
```

Este comando crea una rama local denominada `backend`, la vincula con `origin/backend` y cambia a ella.

A partir de ese momento, será posible trabajar en la rama local y sincronizar los cambios con la rama remota correspondiente.

**Nota:** el nombre `backend` debe sustituirse por el nombre real de la rama requerida.

### 6.3. Cambio a una rama local existente

Si la rama ya se encuentra disponible en el equipo, basta con ejecutar:

```bash
git switch backend
```

Para verificar la rama activa, se puede utilizar:

```bash
git branch
```

La rama activa aparece identificada mediante un asterisco (`*`).

### 6.4. Actualización de una rama existente

Una vez seleccionada la rama correspondiente, se recomienda descargar los últimos cambios publicados en GitHub:

```bash
git pull
```

Este comando actualiza la rama local a partir de la rama remota asociada.

Se recomienda realizar esta operación antes de comenzar a modificar archivos, especialmente cuando varios integrantes trabajan sobre la misma rama.

## 7. Registro de cambios mediante commits

Después de modificar los archivos del proyecto, se debe verificar el estado del repositorio:

```bash
git status
```

Para preparar los cambios, se utiliza:

```bash
git add .
```

Posteriormente, se crea un commit con un mensaje descriptivo:

```bash
git commit -m "feat: agregar funcionalidad de login"
```

El commit registra los cambios en el historial local de Git.

### 7.1. Ejemplos de mensajes para los commits

```bash
git commit -m "feat: agregar catalogo de productos"
git commit -m "fix: corregir validacion del formulario"
git commit -m "docs: actualizar instrucciones de instalacion"
git commit -m "test: agregar pruebas de autenticacion"
```

Se recomienda utilizar mensajes breves, claros y relacionados con las modificaciones realizadas.

## 8. Publicación de cambios en una rama remota existente

Cuando se trabaja en una rama que ya existe en GitHub, los cambios pueden publicarse en ella sin necesidad de crear una rama nueva.

### 8.1. Verificación de la rama activa

Antes de publicar los cambios, se debe comprobar la rama en la que se está trabajando:

```bash
git branch
```

Si es necesario cambiar a la rama `backend`, se utiliza:

```bash
git switch backend
```

### 8.2. Actualización de la rama

Antes de realizar modificaciones, se recomienda descargar los últimos cambios publicados:

```bash
git pull
```

Esta operación permite trabajar con una versión actualizada de la rama.

### 8.3. Registro de los cambios

Una vez realizadas las modificaciones, se deben preparar y registrar los archivos:

```bash
git add .
git commit -m "feat: agregar funcionalidad de login"
```

### 8.4. Publicación de los cambios

Si la rama local ya está vinculada con su rama remota, se utiliza:

```bash
git push
```

Git enviará los nuevos commits a la rama remota asociada.

Por ejemplo, si se trabaja en la rama `backend`, los cambios se publicarán en `origin/backend`.

**Importante:** no es necesario crear otra rama ni utilizar `git push -u` en cada publicación. La opción `-u` se utiliza normalmente la primera vez que se publica una rama y se necesita configurar su seguimiento remoto.

### 8.5. Publicación de una rama local sin seguimiento remoto

Si una rama local todavía no está vinculada con una rama remota, se debe ejecutar:

```bash
git push -u origin nombre-de-la-rama
```

Por ejemplo:

```bash
git push -u origin backend
```

Una vez establecido el seguimiento, normalmente será suficiente utilizar:

```bash
git push
```

### 8.6. Ejemplo completo: publicación en una rama existente

Supóngase que se requiere trabajar en la rama `backend`, que ya existe en GitHub.

Si todavía no se encuentra disponible localmente, se deben ejecutar los siguientes comandos:

```bash
git fetch origin
git switch --track origin/backend
git pull
```

Después de realizar las modificaciones correspondientes, se registran y publican los cambios:

```bash
git add .
git commit -m "feat: agregar funcionalidad de login"
git push
```

Si la rama ya existe localmente, el procedimiento inicial es más sencillo:

```bash
git switch backend
git pull
```

Después de modificar los archivos:

```bash
git add .
git commit -m "feat: actualizar funcionalidad de login"
git push
```

De esta manera, los cambios se publican en la rama `backend` existente en GitHub, sin crear una rama adicional ni modificar directamente `main`.

## 9. Trabajo colaborativo sobre una misma rama

Cuando varios integrantes trabajan sobre una misma rama, es importante mantener las copias locales actualizadas para reducir el riesgo de conflictos.

### 9.1. Antes de comenzar a trabajar

Se debe seleccionar la rama correspondiente:

```bash
git switch backend
```

A continuación, se deben descargar los últimos cambios:

```bash
git pull
```

Una vez actualizada la rama, se puede iniciar el trabajo.

### 9.2. Cuando otro integrante publica cambios durante el desarrollo

Si otro integrante publica nuevos commits mientras se realizan modificaciones locales, la copia local puede quedar desactualizada.

Antes de publicar los cambios propios, se recomienda revisar el estado del repositorio:

```bash
git status
```

Si existen modificaciones que deben conservarse, se pueden registrar en un commit:

```bash
git add .
git commit -m "feat: avanzar funcionalidad de login"
```

Después, se pueden integrar los cambios remotos mediante:

```bash
git pull --rebase
```

Si aparecen conflictos, será necesario resolverlos en los archivos afectados y continuar el proceso siguiendo las indicaciones de Git.

Una vez completada correctamente la operación, se pueden publicar los cambios:

```bash
git push
```

**Importante:** `git pull --rebase` puede detenerse si se presentan conflictos. Estos deben resolverse antes de continuar. No se debe utilizar `git push --force` como solución automática ante un rechazo de Git.

### 9.3. Recomendaciones para el trabajo colaborativo

* Verificar la rama activa antes de realizar modificaciones.
* Ejecutar `git pull` antes de comenzar a trabajar.
* Registrar los cambios mediante commits pequeños y descriptivos.
* Coordinar las modificaciones de archivos cuando se comparte una rama.
* Publicar los cambios periódicamente.
* Revisar el estado del repositorio antes de sincronizar los cambios.
* Evitar sobrescribir las modificaciones realizadas por otros integrantes.

## 10. Creación de Pull Requests

Cuando una tarea se encuentre terminada, se debe crear un **Pull Request (PR)** para proponer la integración de los cambios en la rama principal `main`.

Los Pull Requests permiten revisar las modificaciones antes de incorporarlas a la rama principal.

### 10.1. Publicación de la rama

Antes de crear el Pull Request, es necesario publicar la rama en GitHub:

```bash
git push
```

Si es la primera publicación de la rama, se debe utilizar:

```bash
git push -u origin nombre-de-la-rama
```

### 10.2. Procedimiento para crear un Pull Request

1. Ingresar al repositorio en GitHub.
2. Abrir la sección **Pull requests**.
3. Seleccionar **New pull request**.
4. Elegir como rama de origen aquella en la que se realizaron los cambios.
5. Seleccionar `main` como rama de destino.
6. Escribir un título descriptivo.
7. Explicar los cambios realizados en la descripción.
8. Seleccionar **Create pull request**.

Ejemplo:

* **Rama de origen:** `backend/login`.
* **Rama de destino:** `main`.
* **Título:** `Agregar funcionalidad de inicio de sesión`.

### 10.3. Revisión del Pull Request

Antes de integrar los cambios, se recomienda verificar:

* Que las modificaciones correspondan a la tarea asignada.
* Que el código se encuentre organizado.
* Que no se incluyan modificaciones innecesarias.
* Que no se introduzcan errores conocidos.
* Que se hayan realizado las pruebas necesarias.

Si se solicitan correcciones, el autor podrá modificar la misma rama y publicar los nuevos cambios. El Pull Request se actualizará automáticamente.

### 10.4. Integración de los cambios

Los cambios podrán integrarse en `main` cuando el Pull Request cumpla los requisitos establecidos por el equipo y se cuente con los permisos necesarios.

**Estado actual:** la configuración de los permisos para determinar qué integrantes pueden aprobar e integrar cambios en `main` se encuentra pendiente. Esta configuración se realizará posteriormente.

Mientras se completa dicha configuración, los integrantes deben seguir el flujo de trabajo establecido y evitar realizar cambios directamente en `main`.

**Nota:** exigir Pull Requests mediante una regla de GitHub no restringe por sí solo qué integrantes pueden integrarlos. Para establecer ese control, será necesario configurar los permisos correspondientes.

## 11. Actualización de una rama de trabajo con los cambios de `main`

Durante el desarrollo, otros integrantes pueden integrar cambios en la rama principal. Para incorporar esos cambios en una rama de trabajo, se debe seguir el siguiente procedimiento.

### 11.1. Actualización de la información remota

```bash
git fetch origin
```

### 11.2. Actualización de la rama principal local

```bash
git switch main
git pull origin main
```

### 11.3. Regreso a la rama de trabajo

Por ejemplo:

```bash
git switch backend/login
```

### 11.4. Integración de los cambios de `main`

```bash
git merge main
```

Si aparecen conflictos, será necesario resolverlos en los archivos afectados y completar la integración.

### 11.5. Publicación de la rama actualizada

```bash
git push
```

Este procedimiento incorpora los cambios de `main` en la rama de trabajo.

**Importante:** este proceso no integra la rama de trabajo en `main`. Para proponer los cambios a la rama principal, se debe utilizar un Pull Request.

## 12. Reglas de trabajo en equipo

Para mantener el repositorio organizado, se establecen las siguientes recomendaciones:

1. Cada integrante debe trabajar en una rama relacionada con su tarea.
2. Se debe evitar trabajar directamente en `main`.
3. Antes de iniciar una tarea, se recomienda actualizar la rama correspondiente.
4. Los nombres de las ramas deben ser claros y descriptivos.
5. Los commits deben incluir mensajes que expliquen los cambios realizados.
6. Los cambios deben publicarse en GitHub mediante `git push`.
7. Las tareas terminadas deben presentarse mediante Pull Requests cuando corresponda.
8. Los Pull Requests deben revisarse antes de integrar cambios en `main`.
9. Las correcciones solicitadas deben realizarse en la rama asociada al Pull Request.
10. Se debe comprobar la rama activa antes de ejecutar comandos que modifiquen el proyecto.
11. Cuando varios integrantes trabajen sobre una misma rama, deben coordinarse para reducir los conflictos.
12. No se debe utilizar `git push --force` para solucionar automáticamente problemas de sincronización.
13. La configuración de permisos para restringir quién puede aprobar e integrar cambios en `main` se encuentra pendiente y se realizará posteriormente.

## 13. Flujo de trabajo resumido

### Caso A. Inicio de una tarea nueva

**1. Actualizar la rama principal:**

```bash
git switch main
git pull origin main
```

**2. Crear una rama para la tarea:**

```bash
git switch -c backend/login
```

**3. Realizar los cambios y registrarlos:**

```bash
git add .
git commit -m "feat: agregar funcionalidad de login"
```

**4. Publicar la rama:**

```bash
git push -u origin backend/login
```

**5. Crear un Pull Request en GitHub:**

Seleccionar `backend/login` como rama de origen y `main` como rama de destino.

### Caso B. Trabajo en una rama que ya existe en GitHub

**1. Actualizar la información remota:**

```bash
git fetch origin
```

**2. Crear la rama local vinculada a la rama remota:**

```bash
git switch --track origin/backend
```

**3. Actualizar la rama:**

```bash
git pull
```

**4. Realizar los cambios y crear un commit:**

```bash
git add .
git commit -m "feat: actualizar funcionalidad del backend"
```

**5. Publicar los cambios en la rama existente:**

```bash
git push
```

### Caso C. Continuación del trabajo en una rama local existente

**1. Cambiar a la rama:**

```bash
git switch backend
```

**2. Descargar los últimos cambios:**

```bash
git pull
```

**3. Registrar y publicar las modificaciones:**

```bash
git add .
git commit -m "fix: corregir validacion del backend"
git push
```

### Caso D. Actualización de una rama con los cambios de `main`

**1. Actualizar la información remota:**

```bash
git fetch origin
```

**2. Actualizar `main`:**

```bash
git switch main
git pull origin main
```

**3. Regresar a la rama de trabajo:**

```bash
git switch backend/login
```

**4. Integrar los cambios de `main`:**

```bash
git merge main
```

**5. Publicar la rama actualizada:**

```bash
git push
```

## 14. Comandos principales de Git

| Comando                                 | Función                                                                               |
| --------------------------------------- | ------------------------------------------------------------------------------------- |
| `git clone URL`                         | Descarga el repositorio.                                                              |
| `git status`                            | Muestra el estado de los archivos.                                                    |
| `git branch`                            | Muestra las ramas locales.                                                            |
| `git branch -a`                         | Muestra las ramas locales y remotas conocidas.                                        |
| `git fetch origin`                      | Actualiza la información de las ramas remotas.                                        |
| `git switch main`                       | Cambia a la rama `main`.                                                              |
| `git switch nombre-rama`                | Cambia a una rama local existente.                                                    |
| `git switch -c nombre-rama`             | Crea una rama nueva y cambia a ella.                                                  |
| `git switch --track origin/nombre-rama` | Crea una rama local vinculada a una rama remota existente.                            |
| `git pull`                              | Actualiza la rama activa desde su rama remota asociada.                               |
| `git pull origin main`                  | Descarga e integra los cambios de `origin/main` en la rama local activa.              |
| `git add .`                             | Prepara los cambios para el commit.                                                   |
| `git commit -m "mensaje"`               | Guarda los cambios en un commit local.                                                |
| `git push`                              | Publica los commits en la rama remota asociada.                                       |
| `git push -u origin nombre-rama`        | Publica una rama y configura su seguimiento remoto.                                   |
| `git merge main`                        | Integra los cambios de `main` en la rama activa.                                      |
| `git pull --rebase`                     | Actualiza la rama activa reorganizando los commits locales sobre los cambios remotos. |

## 15. Estado de la configuración de GitHub

Actualmente, la protección básica de la rama `main` está configurada para:

* Exigir Pull Requests antes de integrar cambios.
* Impedir la eliminación de la rama protegida.
* Bloquear los *force pushes*.

Sin embargo, **está pendiente configurar los permisos adicionales para controlar qué integrantes pueden aprobar e integrar cambios en `main`**. Esta configuración se realizará posteriormente.


Hasta entonces, los integrantes deben seguir el flujo de trabajo documentado: desarrollar en ramas independientes, publicar los cambios y utilizar Pull Requests para proponer su integración en la rama principal.
