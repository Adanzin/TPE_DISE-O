**High Availability Pattern para Arquitectura de Microservicios**
===========================================================

**Title**
--------

High Availability Pattern para Arquitectura de Microservicios

**Motivation**
------------

La arquitectura actual incluye clientes de PC y móviles que acceden a los datos de la empresa alojados en 2 bases de datos SQL (Clientes, Pedidos). La base de datos de Clientes contiene datos de clientes y pagos, mientras que la de Pedidos almacena los datos restantes. El acceso actual se reemplazará por protocolos HTTP/REST que faciliten el acceso desde clientes de PC y móviles.

La lógica de negocio de la empresa incluye los siguientes módulos funcionales con diferentes grados de criticidad. La decisión de implementar el Patrón de Alta Disponibilidad es necesaria para garantizar que el sistema pueda responder al 99,9% de las solicitudes, un requisito crítico para mantener la experiencia del usuario y la continuidad de las transacciones.

**Decision Drivers**
-----------------

*   Alta disponibilidad de funcionalidades críticas en los módulos de Clientes y Pagos.
*   Interoperabilidad con diversas plataformas (PC y móvil).
*   Capacidad para manejar un gran volumen de solicitudes y transacciones.
*   Minimización del tiempo de inactividad y garantía de recuperación en caso de fallas.

**Main Decision**
----------------

El Patrón de Alta Disponibilidad se implementará utilizando sistemas distribuidos, balanceo de carga y redundancia. Esto garantizará que el sistema pueda responder al 99,9% de las solicitudes, requisito crítico para mantener la experiencia del usuario y la continuidad de las transacciones.

El sistema será diseñado para manejar fallas de forma que se minimice el tiempo de inactividad y se garantice la recuperación. Se utilizarán tecnologías como balanceo de carga y redundancia para asegurar alta disponibilidad.
**Alternative Decisions**
----------------------

*   **Centralized Architecture**: Se podría usar una arquitectura centralizada donde todos los servicios estén alojados en un único servidor. Sin embargo, esto no proporcionaría la alta disponibilidad ni escalabilidad necesarias.
*   **Load Balancing Only**:  El balanceo de carga por sí solo no proporcionaría la alta disponibilidad ni escalabilidad requeridas. Solo distribuiría la carga entre múltiples servidores, pero no garantizaría redundancia ni tolerancia a fallos.

**Pros**
------

*   **High Availability**: Garantiza que el sistema responda al 99,9% de las solicitudes
*   **Scalability**: El diseño permitirá escalar horizontalmente, manejando mayor tráfico y demanda.
*   **Fault Tolerance**: Minimiza el tiempo de inactividad y asegura la recuperación ante fallas.

**Cons**
------

*   **Increased Complexity**: Requiere un diseño e implementación más complejos, aumentando el tiempo y los costos de desarrollo.
*   **Higher Costs**: Puede necesitar hardware y software más costosos para asegurar alta disponibilidad.
*   **Increased Maintenance**: Requiere mantenimientos y actualizaciones frecuentes.

**Assessment**
--------------

La decisión de implementar el Patrón de Alta Disponibilidad es adecuada para los requisitos, ya que aborda la necesidad de alta disponibilidad en los módulos críticos. El diseño garantizará el manejo de un alto volumen de solicitudes, tiempos de respuesta rápidos y escalabilidad. Además, minimizará el tiempo de inactividad y asegurará la recuperación ante fallos.
