# Especificación de Requerimientos de Software (SRS)

## Plataforma Marketplace de Comercio Electrónico

| Campo | Valor |
|---------|---------|
| Documento | Especificación de Requerimientos |
| Versión | 1.0 |
| Clave | MTS-07 |
| Fecha | 23/10/2026 |
| Empresa | Comercializadora ShopNet S.A.S |

---

# Historial de Revisiones

| Fecha | Versión | Descripción | Autor |
|---------|---------|---------|---------|
| 22/10/2026 | 1.0 | Redacción inicial | Joan Esteban Buitrago |
| 23/10/2026 | 1.1 | Requerimientos funcionales y no funcionales | Daniel Camilo Borrero |

---

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

---

# 2. Descripción General

La plataforma Marketplace está diseñada para permitir a los usuarios buscar productos, hacer pedidos, administrar inventario y gestionar compras desde una aplicación web.

## 2.1 Perspectiva del Producto

El Marketplace será una aplicación web accesible desde cualquier navegador. Administrará:

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

---

# 3. Requerimientos Específicos

## 3.1 Requerimientos Funcionales

---

### RF01 - Creación de Usuario

**Prioridad:** Alta

**Descripción:**  
La plataforma permitirá registrar usuarios clientes y vendedores.

**Entradas:**
- Correo electrónico
- Nombre
- Contraseña

**Proceso:**
1. El usuario diligencia el formulario.
2. El sistema valida:
   - Correo existente y válido.
   - Contraseña segura.
   - Nombre disponible.
3. Se crea el usuario.

**Salida:**
- Acceso al rol correspondiente.

**Restricciones:**
- Correo válido y activo.
- Interfaces diferentes según el rol.

**Efecto Colateral:**
- Redirección a la interfaz correspondiente.

---

### RF02 - Recuperación de Contraseña

**Prioridad:** Alta

**Descripción:**  
Permite recuperar la contraseña asociada a un correo registrado.

**Entradas:**
- Correo electrónico

**Proceso:**
1. Seleccionar "Recuperar contraseña".
2. Introducir correo registrado.
3. Enviar instrucciones de recuperación.

**Salida:**
- Recuperación o cambio de contraseña.

**Restricciones:**
- El correo debe existir en el sistema.

**Efecto Colateral:**
- Acceso nuevamente a la plataforma.

---

### RF03 - Carrito de Compras

**Prioridad:** Alta

**Descripción:**  
Los usuarios podrán agregar productos disponibles a un carrito de compras.

**Entradas:**
- Productos en stock.

**Proceso:**
1. Seleccionar productos.
2. Agregarlos al carrito.
3. Confirmar compra.

**Salida:**
- Carrito actualizado.

**Restricciones:**
- Solo productos disponibles.

**Efecto Colateral:**
- Disminución del inventario tras la compra.

---

### RF04 - Búsqueda y Filtro de Productos

**Prioridad:** Alta

**Descripción:**  
Permite buscar productos por nombre o categoría.

**Entradas:**
- Nombre del producto.
- Categoría.

**Proceso:**
1. Ingresar criterio de búsqueda.
2. Consultar base de datos.
3. Mostrar resultados.

**Salida:**
- Lista de productos coincidentes.

**Restricciones:**
- Solo productos registrados.

**Efecto Colateral:**
- Consultas frecuentes a la base de datos.

---

### RF05 - Notificación de Stock Bajo

**Prioridad:** Alta

**Descripción:**  
Notifica al vendedor cuando un producto alcance un nivel bajo de inventario.

**Entradas:**
- Cantidad disponible.

**Proceso:**
1. Monitorear stock.
2. Detectar umbral mínimo.
3. Enviar notificación.

**Salida:**
- Correo o notificación interna.

**Restricciones:**
- Solo al propietario del producto.

**Efecto Colateral:**
- Recepción de alertas.

---

### RF06 - Inicio de Sesión

**Prioridad:** Alta

**Descripción:**  
Permite acceder a la plataforma mediante credenciales registradas.

**Entradas:**
- Usuario
- Contraseña

**Proceso:**
1. Ingresar credenciales.
2. Validar información.
3. Crear sesión activa.

**Salida:**
- Acceso concedido o mensaje de error.

**Restricciones:**
- Usuario registrado previamente.

**Efecto Colateral:**
- Inicio de sesión activo.

---

## 3.2 Requerimientos No Funcionales

### RNF01 - Seguridad de Contraseñas

**Prioridad:** Alta

**Descripción:**  
Las contraseñas deberán almacenarse utilizando algoritmos de hash seguros.

---

### RNF02 - Compatibilidad

**Prioridad:** Alta

**Descripción:**  
La plataforma deberá ejecutarse correctamente en:

- Computadores
- Tablets
- Teléfonos móviles

Además, deberá ser accesible desde navegadores modernos.

---

# Consideraciones Futuras

Se recomienda agregar los siguientes RNF:

### RNF03 - Disponibilidad
El sistema estará disponible el 99% del tiempo.

### RNF04 - Rendimiento
Las búsquedas deberán responder en menos de 3 segundos.

### RNF05 - Escalabilidad
El sistema deberá soportar un crecimiento gradual de usuarios y productos.

### RNF06 - Usabilidad
La interfaz deberá ser intuitiva y fácil de utilizar.

---

# Confidencialidad

**Comercializadora ShopNet S.A.S.**

Documento confidencial para uso interno del proyecto Marketplace.