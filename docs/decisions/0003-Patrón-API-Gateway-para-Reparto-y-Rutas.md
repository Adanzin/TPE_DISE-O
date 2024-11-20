**Patrón API Gateway para Reparto y Rutas**
===========================================================

**Titulo**
--------

Implementar el patrón API Gateway para el módulo Reparto y Rutas para manejar un alto tráfico y garantizar tiempos de respuesta rápidos.

**Motivacion**
------------

La arquitectura existente tiene una parte de clientes PC y móviles que acceden a los datos de la empresa alojados en 2 bases de datos SQL (Clientes, Pedidos). 
La base de datos de Clientes contiene datos de clientes y de pago, mientras que la base de datos de Pedidos es responsable de almacenar los datos restantes. Se pretende sustituir el acceso actual por protocolos HTTP/REST que faciliten el acceso desde PC y clientes móviles. La lógica de negocio de la empresa cuenta con los siguientes módulos funcionales, con diferentes grados de criticidad. El módulo de Reparto y Rutas es crítico, y su rendimiento y escalabilidad dependerá del número de pedidos por hora. El sistema de pedidos siempre pasa por una cadena de tres fases: preprocesamiento, autorización y aceptación del pedido, de modo que no es posible pasar a un estado si el estado anterior no ha sido procesado correctamente.

El sistema debe responder en menos de dos segundos para asegurar una experiencia de usuario eficiente, especialmente en el módulo de pedidos, que tiene fases críticas en su proceso. El patrón API Gateway es la mejor opción para el módulo Reparto y Rutas debido a su capacidad para manejar un tráfico elevado y garantizar tiempos de respuesta rápidos.

**Decision Drivers**
-----------------

* El sistema debe responder en menos de dos segundos para garantizar una experiencia de usuario eficiente.
* El módulo de Reparto y Rutas es crítico y requiere alto rendimiento y escalabilidad..
* El patrón API Gateway es adecuado para manejar un tráfico elevado y garantizar tiempos de respuesta rápidos..

**Decision Principal**
----------------

El patrón API Gateway es la mejor opción para el módulo Reparto y Rutas debido a su capacidad para manejar un tráfico elevado y garantizar tiempos de respuesta rápidos. Al enrutar solicitudes a servicios utilizando criterios como el método y la ruta de solicitud HTTP, API Gateway puede manejar de manera eficiente la gran cantidad de solicitudes del módulo de pedidos. Además, el patrón de composición de API permite la combinación de resultados de múltiples servicios, lo cual es necesario para la compleja funcionalidad del módulo Reparto y Rutas. Las funciones perimetrales, en particular la autenticación, proporcionan una capa adicional de seguridad y control.

Para satisfacer los requisitos, el patrón API Gateway debe implementarse centrándose en el rendimiento y la escalabilidad, incluido el uso de almacenamiento en caché, equilibrio de carga y mecanismos de enrutamiento eficientes.

**Alternativas**
-----------------------

* Implementar un balanceador de carga para distribuir el tráfico entre múltiples instancias del módulo Reparto y Rutas.
* Utilizar un mecanismo de almacenamiento en caché para reducir el número de solicitudes a la base de datos.
* Implementación de un patrón de disyuntores para manejar fallas y errores parciales.

**Pros**
------

* El patrón API Gateway puede manejar un tráfico elevado y garantizar tiempos de respuesta rápidos.
* El patrón de composición de API permite la combinación de resultados de múltiples servicios.
* Las funciones edge proporcionan una capa adicional de seguridad y control.
* El patrón API Gateway se puede implementar centrándose en el rendimiento y la escalabilidad.

**Cons**
------

* El patrón API Gateway puede introducir complejidad y gastos generales adicionales.
* El sistema puede volverse más difícil de mantener y actualizar.
* El sistema puede ser más vulnerable a fallas y errores parciales.

**Evaluación**
--------------

El patrón API Gateway es ideal para manejar un tráfico elevado y garantizar tiempos de respuesta rápidos. Sin embargo, hay algunas preocupaciones que es necesario abordar:

* El patrón API Gateway puede introducir complejidad y sobrecarga adicionales, lo que podría afectar el rendimiento y la escalabilidad.
* La decisión de implementar el patrón API Gateway no aborda explícitamente los requisitos de rendimiento y escalabilidad para el módulo Clientes, que también es fundamental.
* La decisión no proporciona un plan claro para manejar fallas parciales, lo cual es una consideración importante para el patrón API Gateway.

**Preguntas Aclaratorias**
----------------------

* ¿Cómo se implementará el patrón API Gateway para garantizar que pueda manejar la gran cantidad de solicitudes del módulo de pedidos?
* ¿Qué mecanismos de almacenamiento en caché y equilibrio de carga se utilizarán para mejorar el rendimiento y la escalabilidad?
* ¿Cómo se diseñará el patrón API Gateway para manejar fallas parciales y garantizar que el sistema permanezca disponible?
* ¿Qué medidas de seguridad se implementarán para proteger contra el acceso no autorizado y garantizar la integridad del sistema?