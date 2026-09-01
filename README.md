# TallerExpress

Sistema interno de gestión para un taller mecánico, desarrollado en Java SE con interfaz gráfica mediante JOptionPane, persistencia con JDBC (H2) y arquitectura por capas.

## Descripción general

TallerExpress centraliza la información de clientes, vehículos, repuestos, usuarios y órdenes de servicio, reemplazando el manejo por hojas de cálculo y formularios físicos. Permite:

- Gestionar el inventario de repuestos (crear, editar, activar/desactivar, filtrar por categoría o proveedor).
- Registrar clientes y sus vehículos, validando que la placa sea única.
- Autenticar usuarios con roles (ADMIN / RECEPCIONISTA).
- Registrar órdenes de servicio con los repuestos utilizados, calculando el costo total de la reparación de forma transaccional.
- Consultar el historial de servicios de cada vehículo.

## Arquitectura

El proyecto sigue una arquitectura por capas:

```
model        -> las clases que representan los datos (Cliente, Vehiculo, Repuesto, Usuario, Orden, DetalleOrden)
dao          -> acceso a la base de datos con JDBC (una interfaz + una implementación por cada entidad)
service      -> reglas de negocio y validaciones (código único, stock, cliente activo, transacciones)
controller   -> conecta las pantallas con los servicios
presentation -> las ventanas con JOptionPane
exception    -> excepciones personalizadas (ValidacionException, PersistenciaException)
util         -> utilidades (logs, formato de tablas, InicializarBD)
config       -> configuración de la conexión a la base de datos
```

## Requisitos previos

- Java 17 o superior.
- Maven.
- Base de datos H2 (embebida, no requiere instalación aparte — se incluye como dependencia en `pom.xml`).

## Pasos de configuración y ejecución

1. Clonar el repositorio.
2. Abrir el proyecto en NetBeans (o el IDE de preferencia) como proyecto Maven.
3. Crear las tablas y el usuario administrador inicial:
   - Ejecutar la clase `hub3.tallerexpress.util.InicializarBD` (clic derecho → Run File) o (Shift + F6).
   - Esto lee `tablas.sql`, crea las 6 tablas en la base H2 (`tallerexpress_db.mv.db`), y crea un usuario administrador de prueba.
4. Ejecutar la clase principal `hub3.tallerexpress.TallerExpress`.
5. Iniciar sesión con las credenciales de prueba:
   - Usuario: `admin`
   - Contraseña: `admin123`

## Capturas de pantalla

- Login


  <img width="254" height="119" alt="image" src="https://github.com/user-attachments/assets/75ac8654-948e-4dc5-ab9d-5b7b3b16af5a" />

  
- Menú Principal

  
  <img width="810" height="110" alt="image" src="https://github.com/user-attachments/assets/0849bb4d-d284-4b02-b534-2d78b417cfdf" />

## Diagramas

- Relacion


<img width="285" height="721" alt="image" src="https://github.com/user-attachments/assets/6e9c068a-947a-45e0-936c-10f202f451f3" />

- Caso de usos


<img width="755" height="207" alt="image" src="https://github.com/user-attachments/assets/044cd7c0-51bd-47cb-b41b-10ccdadd4dc0" />


## Entregables

- Repositorio GitHub (público): `<https://github.com/TheplexyBoy/Java-prueba_desempe-o>`
- Proyecto comprimido (.zip)

## Datos del Coder

- Nombre: `<Andres Quintero>`
- Clan: `<Puerta De Oro>`
- Correo: `<andresquinteroho@gmail.com>`
- Documento: `<1047224334>`
