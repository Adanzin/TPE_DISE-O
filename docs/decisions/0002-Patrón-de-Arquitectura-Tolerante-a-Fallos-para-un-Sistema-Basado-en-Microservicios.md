**Patrón de Arquitectura Tolerante a Fallos para un Sistema Basado en Microservicios**
===========================================================

**Title**
--------

Patrón de Arquitectura Tolerante a Fallos para un Sistema Basado en Microservicios


**Motivation**
------------

La arquitectura existente incluye clientes de PC y móviles que acceden a los datos de la empresa alojados en 2 bases de datos SQL (Clientes, Pedidos). El acceso actual se reemplazará por protocolos HTTP/REST que faciliten el acceso desde clientes de PC y móviles. La lógica de negocio de la empresa incluye los siguientes módulos funcionales, con diferentes grados de criticidad. La nueva arquitectura debe contar con los elementos de software y/o tecnología adecuados para poder ejecutar los microservicios. El sistema debe garantizar la integridad y confidencialidad de las transacciones mediante una integración segura con la pasarela de MercadoLibre, y asegurar la disponibilidad y fiabilidad del sistema.

**Decision Drivers**
-----------------

*   Guaranteeing the integrity and confidentiality of transactions and sensitive customer data
*   Ensuring the system's availability and reliability
*   Managing all customer order requests and delivery incidents
*   Providing a way to manage delivery routes and optimize truck fleets
*   Ensuring the system's performance and scalability, particularly for the Orders module

**Main Decision**
----------------

El patrón de Arquitectura Tolerante a Fallos es la mejor opción para los requisitos dados porque aborda todos los requisitos especificados. Al implementar mecanismos de redundancia y conmutación por error, el sistema puede garantizar la integridad y confidencialidad de las transacciones y los datos sensibles de los clientes. Además, el sistema puede continuar operando sin interrumpir otros módulos en caso de un incidente, y los gerentes pueden recibir notificaciones de incidentes para minimizar los efectos sobre la operación. Este patrón es particularmente adecuado para componentes críticos como Pagos y Entregas, que requieren alta disponibilidad y fiabilidad.

**Alternative Decisions**
----------------------

*   **Load Balancing Architecture**:Esta arquitectura podría usarse para distribuir la carga entre varios servidores, pero no proporcionaría el mismo nivel de redundancia y conmutación por error que el patrón de Arquitectura Tolerante a Fallos.
*   **Service-Oriented Architecture (SOA):**:Esta arquitectura podría usarse para separar el sistema en servicios más pequeños e independientes, pero no proporcionaría el mismo nivel de tolerancia a fallos que el patrón de Arquitectura Tolerante a Fallos.

**Pros**
------

*   Aborda los requisitos de garantizar la integridad y confidencialidad de las transacciones y los datos sensibles de los clientes
*   Asegura la disponibilidad y fiabilidad del sistema
*   Gestiona todas las solicitudes de pedidos de clientes e incidentes de entrega
*   Provee una forma de gestionar las rutas de entrega y optimizar las flotas de camiones
*   Asegura el rendimiento y la escalabilidad del sistema, particularmente para el módulo de Pedidos

**Cons**
------

*   Puede incrementar la complejidad y los costos de mantenimiento del sistema
*   Puede no abordar completamente los requisitos de escalabilidad y rendimiento del sistema, particularmente para el módulo de Pedidos

**Assessment**
--------------

La decisión de implementar el patrón de Arquitectura Tolerante a Fallos es parcialmente adecuada. El patrón aborda los requisitos de garantizar la integridad y confidencialidad de las transacciones y los datos sensibles de los clientes, así como asegurar la disponibilidad y fiabilidad del sistema. Sin embargo, la decisión no aborda explícitamente los requisitos de escalabilidad y rendimiento del sistema, particularmente para el módulo de Pedidos.

**Follow-up Decisions**
*   Determinar los mecanismos específicos de redundancia y conmutación por error a utilizar, considerando la complejidad del sistema y la necesidad de escalabilidad
*   Asegurar la integración segura con la pasarela de MercadoLibre y la protección de los datos sensibles de los clientes
*   Abordar los requisitos de escalabilidad y rendimiento del sistema, particularmente para el módulo de Pedidos
