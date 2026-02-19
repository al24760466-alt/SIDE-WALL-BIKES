# SIDE-WALL-BIKES


##  Descripción del Proyecto

Este repositorio contiene el diseño arquitectónico y modelado de datos para **"SIDE WALL BIKES"**, un sistema de información diseñado para administrar una tienda especializada en ciclismo de alto rendimiento (Enduro y Downhill).

El sistema resuelve la problemática de gestión de inventarios complejos, donde los productos y componentes tienen especificaciones técnicas detalladas y provienen de diversos proveedores internacionales. El software permite:
* **Control de Stock:** Monitoreo en tiempo real de componentes.
* **Gestión de Proveedores:** Trazabilidad del origen de cada pieza.
* **Punto de Venta (POS):** Procesamiento de compras con múltiples artículos.
* **Historial de Clientes:** Base de datos para fidelización y garantías.

El proyecto cumple con los estándares de normalización de bases de datos (3NF) para garantizar la integridad de la información y evitar redundancias.

---

##  Motivación y Justificación

Como estudiante de ingeniería y practicante de MTB, identifiqué que las soluciones genéricas de punto de venta no se adaptan a las necesidades específicas de una tienda de componentes técnicos.
* **Problema:** Dificultad para rastrear qué proveedor surtió una pieza específica cuando se requiere garantía, y la complejidad de vender "kits" o múltiples refacciones en un solo ticket.
* **Solución:** Desarrollar una arquitectura propia que permita relaciones complejas entre el inventario y las ventas, asegurando escalabilidad y profesionalización del negocio desde su etapa temprana.

---

##  Arquitectura del Sistema

A continuación se detallan los modelos diseñados para la estructura de datos y la lógica de negocio.

### 1. Modelo Entidad-Relación (Base de Datos)

Este diagrama representa la estructura lógica de la base de datos relacional. Se ha diseñado siguiendo el modelo de Chen para visualizar claramente las entidades fuertes y las interrelaciones.

![Diagrama Entidad Relación](./assets/diagrama_er.png)

**Puntos Clave del Diseño:**
* **Resolución de Relación N:M:** Se implementó la entidad débil `Detalle_Compra` para romper la relación de "Muchos a Muchos" entre `Ventas` y `Productos`. Esto permite que un solo ticket de compra contenga múltiples productos diferentes, registrando la cantidad y el precio histórico de cada uno.
* **Integridad Referencial:** Uso estricto de Llaves Primarias (PK) y Foráneas (FK) para asegurar que no existan compras sin cliente, ni productos sin proveedor.
* **Cardinalidad:**
    * **Proveedor (1) -> (N) Productos:** Un proveedor surte muchos productos.
    * **Cliente (1) -> (N) Compras:** Un cliente puede tener múltiples historiales de compra.

### 2. Diagrama de Clases (Lógica de Negocio / UML)

Este modelo representa la estructura orientada a objetos que tendrá el software. Define las clases, sus atributos (estado) y sus métodos (comportamiento), aplicando principios de encapsulamiento.

![Diagrama UML](./assets/diagrama_uml.png)



---

## 💻 Stack Tecnológico (Proyección)

Este diseño está preparado para ser implementado con las siguientes tecnologías:

* **Motor de Base de Datos:** MySQL \.
* **Backend:** Python

---
*Desarrollado por Santiago Basto Jimenez - Estudiante de Ingeniería en Sistemas Computacionales.*
