**Patrón de Balanceo de Carga - Registro de Decisión de Arquitectura**
===========================================================

**Titulo**
--------

Manejo del Incremento de Carga de Pedidos con el Patrón de Balanceo de Carga

**Motivacion**
------------

La arquitectura existente tiene una parte de clientes de PC y móviles que acceden a los datos de la empresa alojados en dos bases de datos SQL (Clientes, Pedidos). La base de datos de Clientes contiene datos de clientes y pagos, mientras que la base de datos de Pedidos almacena los datos restantes. El acceso actual será reemplazado por protocolos HTTP/REST para facilitar el acceso desde clientes de PC y móviles. La lógica de negocio de la empresa tiene los siguientes módulos funcionales, con diferentes grados de criticidad. El principal requisito es manejar el aumento de la carga de pedidos sin afectar el rendimiento general, especialmente en el módulo de Pedidos, que depende del número de pedidos por hora.

Se elige el patrón de Balanceo de Carga para mejorar el rendimiento general y la escalabilidad del sistema, especialmente en el módulo de Pedidos. Esta decisión aborda el requisito de manejar el incremento de la carga de pedidos y mejorar el rendimiento y la escalabilidad general.

**Decision Drivers**
-----------------

*   Manejar el incremento de la carga de pedidos sin afectar el rendimiento general.
*	Mejorar el rendimiento general y la escalabilidad del sistema.
*	Garantizar que el sistema pueda manejar un gran número de pedidos por hora.
*	Reducir la latencia y aumentar la predictibilidad para los clientes.

**Decisión Principal**
----------------

Se elige el patrón de Balanceo de Carga para manejar el incremento de la carga de pedidos y mejorar el rendimiento general y la escalabilidad del sistema. Esta decisión se basa en el requisito de gestionar el aumento de la carga de pedidos y mejorar el rendimiento y la escalabilidad.

El patrón de Balanceo de Carga se implementa utilizando un algoritmo de programación que considera la carga en cada proveedor y el número de solicitudes en espera de servicio. El sistema está diseñado con una arquitectura de microservicios, lo que permite el escalado horizontal y el balanceo de carga. El Balanceador de Carga se integra con otros componentes del sistema, como los mecanismos de monitoreo y registro, para garantizar el correcto funcionamiento del sistema y detectar cualquier problema.

**Decisiones Alternativas**
------------------------

*   Caché: Implementar mecanismos de caché también puede impactar el rendimiento y la escalabilidad del sistema. La caché puede reducir la carga en el sistema al almacenar datos frecuentemente accedidos en una ubicación de almacenamiento más rápida.
*	Mecanismos de Cola: Implementar mecanismos de cola también puede impactar el rendimiento y la escalabilidad del sistema. Las colas pueden manejar un gran número de solicitudes y reducir la carga en el sistema.

**Pros**
------

*   **Mejor Rendimiento y Escalabilidad: El patrón de Balanceo de Carga mejora el rendimiento y la escalabilidad general del sistema, especialmente en el módulo de Pedidos.
*	**Latencia Reducida: El patrón de Balanceo de Carga reduce la latencia y aumenta la predictibilidad para los clientes.
*	**Introducción de Concurrencia: El patrón de Balanceo de Carga introduce concurrencia, lo que puede reducir el tiempo de bloqueo y mejorar la capacidad de respuesta.

**Cons**
------

*   **Mayor Complejidad: El patrón de Balanceo de Carga introduce una mayor complejidad en la gestión del balanceador de carga y su configuración.
*	**Posible Incremento de Latencia: El balanceador de carga puede aumentar la latencia si no está correctamente configurado o si los servicios subyacentes no están diseñados para manejar la carga.

**Decisiones de Seguimiento**
------------------------

*   Diseñar el Balanceador de Carga para usar un algoritmo de programación que tenga en cuenta la carga en cada proveedor y el número de solicitudes en espera de servicio.
*	Garantizar que los servicios subyacentes estén diseñados para manejar la carga y estén configurados correctamente para trabajar con el Balanceador de Carga.
*	Implementar mecanismos de monitoreo y registro para garantizar el correcto funcionamiento del Balanceador de Carga y detectar cualquier problema.