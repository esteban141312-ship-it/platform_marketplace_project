# Especificación de Requerimientos de Software (SRS)

## Plataforma Marketplace de Comercio Electrónico

| Campo | Valor |
|---------|---------|
| Documento | Especificación de Requerimientos |
| Versión | 1.0 |
| Clave | MTS-07 |
| Fecha | 23/10/2026 |
| Empresa | Comercializadora ShopNet S.A.S |

# Historial de Revisiones

| Fecha | Versión | Descripción | Autor |
|---------|---------|---------|---------|
| 22/10/2026 | 1.0 | Redacción inicial | Joan Esteban Buitrago |
| 23/10/2026 | 1.1 | Requerimientos funcionales y no funcionales | Daniel Camilo Borrero |
| 30/10/2026 | 1.2 | Incorporación de nuevos requerimientos funcionales y actualización de requerimientos no funcionales | Joan Esteban Buitrago |

# 1. Introducción

Este documento contiene la especificación de requerimientos de software (SRS) para el desarrollo de una plataforma de comercio electrónico tipo Marketplace. El sistema permitirá optimizar procesos de ventas, control de inventario y gestión de pedidos, permitiendo que múltiples vendedores publiquen productos y que los clientes puedan realizar compras desde una plataforma centralizada.

## 1.1 Propósito

Describir completamente el comportamiento de la plataforma, así como sus requisitos funcionales y no funcionales, teniendo en cuenta las especificaciones del cliente.

## 1.2 Alcance

La plataforma estará disponible para cualquier usuario que se registre como cliente de la empresa. Los empleados e integrantes de la empresa también tendrán acceso a la plataforma.

## 1.3 Definiciones, Acrónimos y Abreviaturas

| Término | Definición |
|----------|------------|
| SRS | Especificación de Requerimientos de Software |
| Marketplace | Plataforma digital donde diferentes vendedores ofrecen productos o servicios y los clientes pueden comprarlos desde un mismo sitio |
| RF | Requerimiento Funcional |
| RNF | Requerimiento No Funcional |
| Admin | Usuario con máximo nivel de permisos |
| Cliente | Usuario que realiza compras |
| Vendedor | Usuario encargado de administrar y vender productos |

## 1.4 Referencias

- Documentación técnica de aplicaciones de comercio electrónico.
- Estándares de desarrollo de software.

## 1.5 Apreciación Global

Este documento servirá como guía para el diseño, desarrollo y pruebas de la plataforma.

# 2. Descripción General

La plataforma Marketplace está diseñada para permitir a los usuarios buscar productos, hacer pedidos, administrar inventario y gestionar compras desde una aplicación web.

## 2.1 Perspectiva del Producto

El Marketplace será una aplicación web accesible desde cualquier navegador.

Administrará:

- Clientes
- Vendedores
- Productos
- Pedidos

## 2.2 Funciones del Producto

- Creación de usuarios cliente.
- Creación de usuarios vendedor.
- Búsqueda de productos por nombre o categoría.
- Recuperación de contraseña.
- Carrito de compras.
- Seguimiento del estado de pedidos.
- Gestión de inventario.
- Revisión y aprobación de publicaciones por parte del administrador.
- Gestión de los estados de los pedidos por parte del vendedor.
- Registro de pedidos realizados por los clientes.
- Visualización del resumen y total de la compra antes de confirmarla.
- Botones de redirección a redes sociales.
- Sistema de notificaciones para clientes, vendedores y administradores.
- Reportes de productos más vendidos.
- Reportes de ventas mensuales.
- Reportes de usuarios registrados.
- Reportes de vendedores con mayores ventas.
- Consulta del historial de pedidos según el rol del usuario.

## 2.3 Características de Usuario

### Cliente

- Registrarse.
- Buscar productos.
- Realizar compras.
- Consultar estado de pedidos.

### Vendedor

- Crear productos.
- Gestionar inventario.
- Consultar pedidos.

### Administrador

- Gestionar usuarios.
- Generar reportes.
- Administrar información global.

## 2.4 Restricciones

- Cumplir normativas de protección de datos.
- Compatible con múltiples navegadores.
- Diseño responsivo.
- Los pagos se procesarán mediante servicios externos.

## 2.5 Suposiciones y Dependencias

- Acceso a Internet.
- Dispositivos compatibles con aplicaciones web.
- Integración con servicios de autenticación por correo electrónico.

# 3. Requerimientos Específicos

## 3.1 Requerimientos Funcionales

### RF01 - Creación de Usuario

| Campo | Detalle |
|---------|---------|
| Prioridad | Alta |
| Descripción | La plataforma permitirá registrar usuarios clientes y vendedores. |
| Entradas | Correo electrónico, Nombre, Contraseña |
| Proceso | 1. El usuario diligencia el formulario.<br>2. El sistema valida correo existente y válido.<br>3. El sistema valida contraseña segura.<br>4. El sistema valida nombre disponible.<br>5. Se crea el usuario. |
| Salida | Acceso al rol correspondiente. |
| Restricciones | Correo válido y activo.<br>Interfaces diferentes según el rol. |
| Efecto Colateral | Redirección a la interfaz correspondiente. |

### RF02 - Recuperación de Contraseña

| Campo | Detalle |
|---------|---------|
| Prioridad | Alta |
| Descripción | Permite recuperar la contraseña asociada a un correo registrado. |
| Entradas | Correo electrónico |
| Proceso | 1. Seleccionar "Recuperar contraseña".<br>2. Introducir correo registrado.<br>3. Enviar instrucciones de recuperación. |
| Salida | Recuperación o cambio de contraseña. |
| Restricciones | El correo debe existir en el sistema. |
| Efecto Colateral | Acceso nuevamente a la plataforma. |

### RF03 - Carrito de Compras

| Campo | Detalle |
|---------|---------|
| Prioridad | Alta |
| Descripción | Los usuarios podrán agregar productos disponibles a un carrito de compras. |
| Entradas | Productos en stock. |
| Proceso | 1. Seleccionar productos.<br>2. Agregarlos al carrito.<br>3. Confirmar compra. |
| Salida | Carrito actualizado. |
| Restricciones | Solo productos disponibles. |
| Efecto Colateral | Disminución del inventario tras la compra. |

### RF04 - Búsqueda y Filtro de Productos

| Campo | Detalle |
|---------|---------|
| Prioridad | Alta |
| Descripción | Permite buscar productos por nombre o categoría. |
| Entradas | Nombre del producto, Categoría |
| Proceso | 1. Ingresar criterio de búsqueda.<br>2. Consultar base de datos.<br>3. Mostrar resultados. |
| Salida | Lista de productos coincidentes. |
| Restricciones | Solo productos registrados. |
| Efecto Colateral | Consultas frecuentes a la base de datos. |

### RF05 - Notificación de Stock Bajo

| Campo | Detalle |
|---------|---------|
| Prioridad | Alta |
| Descripción | Notifica al vendedor cuando un producto alcance un nivel bajo de inventario. |
| Entradas | Cantidad disponible |
| Proceso | 1. Monitorear stock.<br>2. Detectar umbral mínimo.<br>3. Enviar notificación. |
| Salida | Correo o notificación interna. |
| Restricciones | Solo al propietario del producto. |
| Efecto Colateral | Recepción de alertas. |

### RF06 - Inicio de Sesión

| Campo | Detalle |
|---------|---------|
| Prioridad | Alta |
| Descripción | Permite acceder a la plataforma mediante credenciales registradas. |
| Entradas | Usuario, Contraseña |
| Proceso | 1. Ingresar credenciales.<br>2. Validar información.<br>3. Crear sesión activa. |
| Salida | Acceso concedido o mensaje de error. |
| Restricciones | Usuario registrado previamente. |
| Efecto Colateral | Inicio de sesión activo. |

### RF07 - Revisar Publicaciones

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Permite al administrador consultar, evaluar y gestionar las publicaciones de productos antes de que sean visibles al público o después de su publicación. |
| Entradas | Identificador de la publicación. |
| Proceso | El administrador accede al módulo de productos, consulta las publicaciones pendientes, selecciona una y revisa su información. Puede aprobarla, rechazarla, solicitar cambios o pausarla. Para rechazar, solicitar cambios o pausar debe indicar un motivo. |
| Salida | Actualización del estado de la publicación y confirmación de la acción realizada. |
| Restricciones | Solo el administrador puede revisar publicaciones. Ningún usuario puede aprobar sus propias publicaciones. |
| Efecto Colateral | Se actualiza la visibilidad del producto, se registra la revisión en el historial y se notifica al autor. |

### RF08 - Estados de los Pedidos

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Permite al vendedor gestionar y actualizar los estados de los pedidos que recibe. |
| Entradas | Identificador del pedido, nuevo estado, número de guía o transportadora cuando corresponda y motivo de cancelación. |
| Proceso | El vendedor consulta sus pedidos, selecciona uno y actualiza su estado. El sistema valida que el cambio sea permitido y registra la modificación. |
| Salida | Pedido actualizado y mensaje de confirmación. |
| Restricciones | Solo el vendedor responsable puede cambiar el estado. El flujo normal es Pendiente → En preparación → Enviado → Entregado. La cancelación solo se permite antes del envío y requiere un motivo. Para marcar como enviado se necesita el número de guía. |
| Efecto Colateral | Se notifica al cliente y se registra el historial de estados. Si se cancela el pedido, se devuelve el stock al inventario y se inicia el reembolso cuando corresponda. |

### RF09 - Registrar el Pedido

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Permite registrar en el sistema el pedido del cliente una vez que confirma su compra. |
| Entradas | Identificador del cliente, productos del carrito, cantidades, precios, dirección de envío, método de envío, método de pago, cupón y total confirmado. |
| Proceso | El sistema valida los datos, verifica las existencias y los precios. Si todo es correcto, genera un número único de pedido y almacena la información de la compra. |
| Salida | Confirmación del pedido, número asignado, resumen de compra y estado inicial. |
| Restricciones | El cliente debe tener sesión iniciada, el carrito debe contener productos y los datos de envío y pago deben estar completos. Se debe evitar el registro duplicado. |
| Efecto Colateral | Se descuenta o reserva el inventario, se vacía el carrito y se envía una confirmación al cliente. |

### RF010 - Ver el Total de la Compra Antes de Confirmar

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Permite al cliente visualizar el resumen completo de su compra antes de confirmar el pedido. |
| Entradas | Productos del carrito, cantidades, dirección de envío y cupón de descuento opcional. |
| Proceso | El sistema consulta los precios y la disponibilidad, calcula el subtotal, descuentos, envío e impuestos, y muestra el total a pagar. |
| Salida | Resumen de compra con subtotal, descuentos, envío, impuestos y total. |
| Restricciones | Solo el cliente autenticado puede consultar su carrito. Debe existir al menos un producto y los precios y existencias deben validarse. |
| Efecto Colateral | Si el cliente confirma, continúa el proceso de registro del pedido. Si existen cambios de precio o disponibilidad, se actualiza el carrito. |

### RF011 - Botones de Redirección a Redes Sociales

| Campo | Detalle |
|---|---|
| Prioridad | Media |
| Descripción | La plataforma mostrará botones que redirigen a sus redes sociales y canales de contacto: WhatsApp, Instagram y Facebook. |
| Entradas | Clic del usuario sobre uno de los botones. |
| Proceso | El usuario selecciona una red social y el sistema utiliza el enlace configurado para redirigirlo al canal correspondiente. |
| Salida | Apertura de la red social o canal seleccionado. |
| Restricciones | Los enlaces deben corresponder a las cuentas oficiales. Si un enlace no está configurado, el botón no se muestra. |
| Efecto Colateral | La plataforma permanece abierta y conserva la sesión del usuario. |

### RF012 - Notificaciones

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | El sistema informará a los usuarios sobre eventos relevantes, como cambios de estado de pedidos, resultados de revisión de publicaciones, stock bajo y nuevas reseñas. |
| Entradas | Evento generado por el sistema, destinatario y mensaje. |
| Proceso | Cuando ocurre un evento, el sistema identifica al usuario correspondiente, genera la notificación y la almacena para su consulta. |
| Salida | Notificación visible en la plataforma y contador de notificaciones sin leer. |
| Restricciones | Cada usuario solo puede consultar sus propias notificaciones. Las notificaciones abiertas se marcan como leídas y se conservan en un historial. |
| Efecto Colateral | Se actualiza el contador de notificaciones pendientes de lectura. |

### RF013 - Reporte de Productos Más Vendidos

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Permite al administrador consultar cuáles son los productos con mayores ventas. |
| Entradas | Periodo de consulta y cantidad de productos que desea mostrar. |
| Proceso | El administrador selecciona el periodo y el sistema calcula las unidades vendidas por producto, ordenándolas de mayor a menor. |
| Salida | Listado con nombre del producto, vendedor, unidades vendidas y total vendido. |
| Restricciones | Solo el administrador puede consultar el reporte. Se cuentan únicamente pedidos entregados. Por defecto se muestran los 10 productos más vendidos. |
| Efecto Colateral | Se registra la consulta del reporte. |

### RF014 - Reporte de Ventas Mensuales

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Permite al administrador consultar el comportamiento de las ventas de la plataforma por mes. |
| Entradas | Mes y año que se desea consultar. |
| Proceso | El administrador selecciona el periodo y el sistema calcula los totales correspondientes. |
| Salida | Reporte con cantidad de pedidos, unidades vendidas y total vendido. |
| Restricciones | Solo el administrador puede consultar el reporte. Se cuentan los pedidos entregados y se excluyen los cancelados. |
| Efecto Colateral | Se registra la consulta del reporte. |

### RF015 - Reporte de Cantidad de Usuarios Registrados

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Permite al administrador consultar la cantidad de usuarios registrados en la plataforma. |
| Entradas | Rango de fechas de registro opcional. |
| Proceso | El administrador accede al reporte y el sistema cuenta los usuarios registrados, clasificándolos por tipo. |
| Salida | Total de usuarios registrados, diferenciados entre clientes y vendedores. |
| Restricciones | Solo el administrador puede consultar el reporte. Se cuentan únicamente las cuentas registradas en la base de datos. |
| Efecto Colateral | Se registra la consulta del reporte. |

### RF016 - Reporte de Vendedores con Más Ventas

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Permite al administrador consultar cuáles vendedores generan mayores ventas en la plataforma. |
| Entradas | Mes o periodo a consultar y cantidad de vendedores que se desean mostrar. |
| Proceso | El sistema calcula las ventas de cada vendedor, las ordena de mayor a menor y presenta el ranking. |
| Salida | Listado con nombre del vendedor, cantidad de pedidos, unidades vendidas y total vendido. |
| Restricciones | Solo el administrador puede consultar el reporte. Se cuentan únicamente pedidos entregados. Por defecto se muestran los 10 vendedores con mayores ventas. |
| Efecto Colateral | Se registra la consulta del reporte. |

### RF017 - Historial de Pedidos

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Permite consultar el historial de pedidos según el rol del usuario. |
| Entradas | Filtros por estado, rango de fechas o número de pedido. |
| Proceso | El usuario accede al módulo de pedidos y consulta los registros que le corresponden según su rol. Puede filtrar y seleccionar un pedido para consultar sus detalles. |
| Salida | Listado de pedidos con número, fecha, productos, total, estado y número de guía cuando corresponda. |
| Restricciones | El cliente solo puede ver sus propios pedidos, el vendedor los pedidos que incluyen sus productos y el administrador todos los pedidos. Los pedidos entregados y cancelados se conservan en el historial y no pueden cambiar de estado. |
| Efecto Colateral | No tiene efectos colaterales adicionales. |

## 3.2 Requerimientos No Funcionales

## 3.2 Requerimientos No Funcionales

### RNF01 - Hasheo de Contraseñas

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Al registrar un usuario, la contraseña deberá almacenarse mediante un algoritmo de hash seguro. |

### RNF02 - Compatibilidad

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | El sistema deberá estar disponible como aplicación web para computadores, teléfonos móviles y tabletas. |

### RNF03 - Disponibilidad

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | El sistema deberá estar disponible el 99 % del tiempo. |

### RNF04 - Escalabilidad

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | El sistema deberá soportar un crecimiento gradual en la cantidad de usuarios y productos registrados. |

### RNF05 - Usabilidad

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | La interfaz deberá ser intuitiva y fácil de utilizar para los diferentes tipos de usuarios. |

### RNF06 - Rendimiento

| Campo | Detalle |
|---|---|
| Prioridad | Alta |
| Descripción | Las búsquedas de productos deberán responder en menos de 3 segundos. |

# Confidencialidad

**Comercializadora ShopNet S.A.S.**

Documento confidencial para uso interno del proyecto Marketplace.