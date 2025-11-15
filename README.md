# ProyectoPOO
# Proyecto POO -- Sistema de Gestión (NetBeans + PostgreSQL)

## 1. Introducción

Este proyecto corresponde a un **Sistema de Gestión** desarrollado en
Java utilizando **Programación Orientada a Objetos (POO)**, con interfaz
gráfica construida en **NetBeans**, y persistencia de datos utilizando
**PostgreSQL**.\
El sistema permite administrar clientes, productos, empleados, compras y
facturas mediante formularios que interactúan con una base de datos
relacional.

La arquitectura del proyecto sigue el patrón **MVC
(Modelo--Vista--Controlador)**, garantizando una separación clara entre
la interfaz, la lógica de negocio y el acceso a datos.

------------------------------------------------------------------------

## 2. Estructura del Proyecto

    PROYECTO_POO/
    │── src/
    │   └── uts/edu/poo/
    │       ├── controlador/
    │       ├── dao/
    │       ├── modelo/
    │       ├── vista/
    │       └── iconos/
    │── nbproject/
    │── build.xml
    │── manifest.mf

### 2.1 Paquete `modelo`

Incluye las **clases que representan las entidades** de la base de
datos:

-   Cliente\
-   Empleado\
-   Producto\
-   Compra\
-   DetalleCompra\
-   Factura

Cada clase maneja sus atributos mediante encapsulación (variables
privadas + getters/setters) y contiene constructores y métodos
auxiliares.

### 2.2 Paquete `dao`

Contiene las clases encargadas del **acceso a PostgreSQL**:

-   `ClienteDAO`
-   `EmpleadoDAO`
-   `ProductoDAO`
-   `CompraDAO`
-   `DetalleCompraDAO`

Cada DAO ejecuta sentencias SQL usando consultas preparadas y la
conexión definida en `ConexionBD.java`.

### 2.3 Paquete `controlador`

Gestiona los eventos de la interfaz gráfica y el flujo del programa:

-   Captura clics de botones
-   Obtiene información de los formularios
-   Valida datos ingresados por el usuario
-   Llama a los métodos del DAO correspondiente

Ejemplos: `ControladorProducto`, `ControladorEmpleado`,
`ControladorCompra`, etc.

### 2.4 Paquete `vista`

Contiene los **formularios gráficos** diseñados en NetBeans, usando Java
Swing.

------------------------------------------------------------------------

## 3. Base de Datos en PostgreSQL

### 3.1 Conexión

El archivo `ConexionBD.java` configura la conexión a PostgreSQL:

-   Driver: `org.postgresql.Driver`
-   Puerto por defecto: **5432**
-   URL: `jdbc:postgresql://localhost:5432/nombre_basedatos`
-   Usuario y contraseña
-   Manejo de excepciones

### 3.2 Tablas principales

#### **Tabla: clientes**

  Campo        Tipo      Descripción
  ------------ --------- ---------------------
  id_cliente   SERIAL    Identificador único
  nombre       VARCHAR   Nombre del cliente
  telefono     VARCHAR   Teléfono
  direccion    VARCHAR   Dirección

#### **Tabla: productos**

  Campo         Tipo
  ------------- ---------
  id_producto   SERIAL
  nombre        VARCHAR
  precio        NUMERIC
  cantidad      INTEGER

#### **Tabla: empleados**

  Campo         Tipo
  ------------- ---------
  id_empleado   SERIAL
  nombre        VARCHAR
  cargo         VARCHAR
  salario       NUMERIC

#### **Tabla: compras** y **detalle_compra**

Relacionan productos con facturas o compras, permitiendo registrar
transacciones completas.

### 3.3 Relaciones

-   Un **cliente** puede generar varias **facturas**.\
-   Una **factura** contiene varios **detalles**.\
-   Cada **detalle** referencia un **producto** y su cantidad.

------------------------------------------------------------------------

## 4. Funcionamiento del Sistema

### 4.1 Módulo de Clientes

Permite agregar, editar, eliminar y listar clientes.

### 4.2 Módulo de Productos

Permite gestionar el inventario: agregar productos, editar precio,
modificar stock y eliminar productos.

### 4.3 Módulo de Empleados

Incluye registro, actualización y eliminación de empleados.

### 4.4 Módulo de Compras y Facturación

Permite seleccionar productos, calcular totales y registrar facturas con
sus detalles.

------------------------------------------------------------------------

## 5. Arquitectura MVC

### **Modelo (Model)**

Representa los datos y entidades.

### **Vista (View)**

Formularios Swing diseñados en NetBeans.

### **Controlador (Controller)**

Recibe eventos, procesa la lógica y comunica vista-modelo.

Este patrón facilita el mantenimiento y la escalabilidad del proyecto.

------------------------------------------------------------------------

## 6. Requisitos para Ejecutar el Proyecto

-   **Java JDK 8 o superior**
-   **NetBeans (Recomendado 8.2 o Apache NetBeans 12+)**
-   **PostgreSQL 12 o superior**
-   **Driver JDBC de PostgreSQL (postgresql.jar)**

------------------------------------------------------------------------

## 7. Instrucciones para la Ejecución

1.  Importar el proyecto en NetBeans.\
2.  Verificar que el driver JDBC esté agregado en *Libraries*.\
3.  Editar `ConexionBD.java` con tus credenciales de PostgreSQL.\
4.  Crear las tablas en PostgreSQL según el modelo descrito.\
5.  Ejecutar desde NetBeans con el botón **Run**.

------------------------------------------------------------------------

## 8. Conclusiones

Este proyecto demuestra:

-   Uso correcto de POO en Java.\
-   Aplicación estructurada del patrón MVC.\
-   Integración con PostgreSQL mediante JDBC.\
-   Operaciones CRUD completas.\
-   Interfaz gráfica funcional con Swing/NetBeans.

------------------------------------------------------------------------

## 9. Créditos

Estiben Quiñonez Arango
Harvic Edisson Quintero Caceres 
Carlos Perez Esparza
**Programación Orientada a Objetos (POO)**.
