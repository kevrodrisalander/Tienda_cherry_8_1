# Cherry — Plataforma de tienda, ventas e inventario 🍒

Cherry es una plataforma web para administrar la operación de una tienda y ofrecer un catálogo de productos en línea. Integra escaparate público, registro de clientes, carrito, checkout, control de existencias, proveedores, usuarios, envíos, reportes y emisión de tickets PDF.

Este documento sirve como presentación funcional y manual de instalación para clientes, distribuidores, personal de soporte e implementadores.

> **Importante:** la entrega debe incluir por separado los términos de licencia comercial, alcance del soporte, vigencia de actualizaciones y datos de contacto del proveedor. Este repositorio no contiene todavía una licencia comercial propia.

## Contenido

- [Funciones principales](#funciones-principales)
- [Tecnologías y componentes](#tecnologías-y-componentes)
- [Requisitos del servidor](#requisitos-del-servidor)
- [Instalación rápida](#instalación-rápida)
- [Instalación paso a paso](#instalación-paso-a-paso)
- [Acceso inicial](#acceso-inicial)
- [Configuración para producción](#configuración-para-producción)
- [Operación y mantenimiento](#operación-y-mantenimiento)
- [Solución de problemas](#solución-de-problemas)
- [Alcance comercial y seguridad](#alcance-comercial-y-seguridad)

## Funciones principales

### Tienda y experiencia de compra

- Catálogo público organizado por categorías y secciones.
- Consulta de productos, precios y disponibilidad.
- Carrito de compras almacenado en la sesión del navegador.
- Registro e inicio de sesión de clientes.
- Checkout con validación de existencias en tiempo real.
- Registro operativo de pagos en efectivo, tarjeta o vales.
- Cálculo de efectivo recibido y cambio.
- Registro de pedidos, partidas y movimientos de salida.
- Generación de ticket de compra en PDF con formato de 80 mm.
- Página informativa de sucursales con mapas integrados.

### Administración comercial

- Gestión de productos y stock.
- Control de lotes, ubicación, mínimos, máximos y vencimientos.
- Registro de entradas y salidas para seguimiento de inventario.
- Búsqueda y filtros avanzados de existencias.
- Activación, desactivación y restauración de registros.
- Exportación del stock filtrado a Excel.
- Gestión de proveedores y marcas asociadas.
- Gestión de clientes, domicilios y datos de envío.
- Administración de usuarios y consulta de roles.
- Reportes de ventas por rango de fechas.
- Generación de tickets PDF de ventas y pedidos.

### Roles contemplados

El modelo incluye roles para administrador, supervisor, vendedor, almacén, contador, cliente, soporte técnico, compras, recursos humanos, invitado y abogado. La matriz de permisos está definida en el modelo de usuario.

> La existencia de roles no implica que todas las rutas administrativas estén protegidas automáticamente. Antes de publicar el sistema se debe aplicar y validar el middleware de autenticación, autorización y roles de acuerdo con la licencia o implementación contratada.

## Tecnologías y componentes

| Componente | Tecnología | Uso |
|---|---|---|
| Backend | PHP 8.1+ y Laravel 10 | Lógica, rutas, validaciones, sesiones y acceso a datos |
| Base de datos | PostgreSQL | Catálogos, usuarios, pedidos, ventas, pagos e inventario |
| Frontend | Blade, JavaScript, CSS y Vite 5 | Interfaz y compilación de estilos |
| UI | Bootstrap 5, Bootstrap Icons y Font Awesome | Diseño e iconografía |
| Tablas | jQuery DataTables | Consultas, paginación y filtros |
| Formularios | Select2 y SweetAlert2 | Selectores y mensajes interactivos |
| PDF | DOMPDF | Tickets de compra y venta |
| Excel | Laravel Excel / PhpSpreadsheet | Exportación de existencias |
| Autenticación | Laravel Auth y Sanctum | Sesiones web y base para API autenticada |
| Pruebas | PHPUnit 10 | Pruebas automatizadas |

Algunas bibliotecas visuales se cargan desde CDN. El servidor y los equipos cliente necesitan acceso a internet para obtener Bootstrap, DataTables, jQuery, Select2, SweetAlert2, iconos y traducciones externas. Para instalaciones aisladas se deben alojar esos recursos localmente.

## Requisitos del servidor

### Requisitos mínimos

- PHP 8.1 o superior.
- Extensiones PHP: `ctype`, `curl`, `dom`, `fileinfo`, `filter`, `hash`, `mbstring`, `openssl`, `pdo`, `pdo_pgsql`, `session`, `tokenizer`, `xml` y `zip`.
- PostgreSQL 13 o superior recomendado.
- Composer 2.x.
- Node.js 18 o superior y npm.
- Servidor web Apache 2.4 o Nginx.
- Acceso de escritura para el usuario del servidor web en `storage/` y `bootstrap/cache/`.
- Navegador moderno con JavaScript habilitado.



## Estructura del proyecto

```text
app/                 Modelos, controladores, servicios y exportaciones
bootstrap/           Arranque y caché del framework
config/              Configuración de Laravel
database/migrations/ Estructura versionada de la base de datos
database/seeders/    Catálogos y datos de demostración
public/              Punto de entrada y recursos públicos
resources/views/     Pantallas Blade
resources/css/       Estilos compilados con Vite
routes/               Rutas web, API y consola
storage/              Logs, sesiones, cachés y archivos internos
tests/                Pruebas automatizadas
```
Al solicitar ayuda incluya la versión, ambiente, pasos para reproducir el problema y fragmentos relevantes del log, sin compartir contraseñas, claves privadas ni datos personales.
