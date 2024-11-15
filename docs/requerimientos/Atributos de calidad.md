# Atributos de calidad

## *Escalabilidad* 
- Cuando la cantidad de pedidos realizados aumenta significativamente, el sistema debe ser capaz de manejar esta carga sin afectar el rendimiento general, especialmente en el módulo de Pedidos, que depende de la cantidad de pedidos por hora.

## *Mantenibilidad - Escalabilidad* 
- Al realizar cambios en un microservicio específico (por ejemplo, el módulo de Pedidos o Clientes), estos cambios deben poder implementarse, probarse y desplegarse sin afectar otros módulos, facilitando la evolución y el mantenimiento de la arquitectura. 

## *Disponibilidad*
- Si un cliente intenta acceder a la funcionalidad crítica del módulo de Clientes o realizar un pago en el módulo de Pagos, estos deben estar disponibles el 99.9% del tiempo para evitar afectar la experiencia del usuario y la continuidad de las transacciones

## *Seguridad* 
- Durante la gestión de pagos, el sistema debe garantizar la integridad y confidencialidad de las transacciones a través de la integración segura con la pasarela de MercadoLibre. Esto también aplica al acceso de datos sensibles de los clientes en el módulo de Clientes.

## *Interoperabilidad* 
- Al migrar al protocolo HTTP/REST, los servicios deben ser interoperables con diversas plataformas (PC y móviles), permitiendo que cualquier dispositivo compatible pueda acceder a los microservicios sin problemas de compatibilidad.

## *Tolerancia a Fallos*
- Ante una incidencia en el módulo de Incidencias (como el reporte de una avería en un camión), el sistema debe continuar operando sin interrumpir otros módulos. Los gestores deben recibir notificaciones de incidencias para minimizar los efectos en la operación.

## *Rendimiento* 
- Cuando se consultan rutas o estados de pedidos en el módulo de Reparto y rutas, el sistema debe responder en menos de dos segundos para asegurar una experiencia de usuario eficiente, especialmente en el módulo de pedidos que tiene fases críticas en su proceso.
