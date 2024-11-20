# ATTRIBUTE-DRIVEN DESIGN (ADD)
En el siguiente informe presentaremos el diseño de una arquitectura de microservicios para una compañía de productos alimenticios, la cual busca migrar su sistema actual, de naturaleza monolítica, hacia una solución más modular y fácil de evolucionar. La nueva arquitectura dividirá el sistema en microservicios independientes para cada funcionalidad clave: gestión de clientes, pedidos, rutas de reparto, estadísticas, incidencias y pagos.
Se han aplicado patrones de diseño y tácticas de arquitectura para mejorar la escalabilidad, disponibilidad y seguridad, utilizando protocolos HTTP/REST para facilitar el acceso desde clientes en dispositivos móviles y de escritorio. Este enfoque garantiza una mayor flexibilidad y adaptabilidad a las demandas del negocio, optimizando la interacción y gestión de los datos alojados en las bases SQL existentes.

## ITERACION 0 

### Análisis del Sistema y capturacion de requerimientos
En esta Iteración se recolectaron los siguientes DRIVERS.
- [Requerimientos Funcionales](https://github.com/Adanzin/TPE_DISE-O/blob/399a12c6a0e978c3e7603cb3d7a5c2a3e227cb8d/docs/requerimientos/guie-functional-rqmts.md)
- [Atributos de calidad](https://github.com/Adanzin/TPE_DISE-O/blob/399a12c6a0e978c3e7603cb3d7a5c2a3e227cb8d/docs/requerimientos/Atributos%20de%20calidad.md)
- [Tabla de Prioridad](https://github.com/Adanzin/TPE_DISE-O/blob/399a12c6a0e978c3e7603cb3d7a5c2a3e227cb8d/docs/requerimientos/TablaDePrioridad.md)

## ITERACION 1
En esta iteración del método ADD, el objetivo principal es abordar los drivers de alta prioridad definidos para el sistema (QA2, QA3, QA5, RF1,RF6, RF9, RF10), con un enfoque especial en garantizar disponibilidad (99.9%), escalabilidad, y rendimiento en módulos críticos como Clientes y Pagos. Para lograr esto, se introducirá un diseño basado en patrones de alta disponibilidad que responda a los requisitos funcionales (RF) y los atributos de calidad (QA) priorizados.
Durante esta fase, el enfoque se centrará en identificar las decisiones arquitectónicas necesarias para desacoplar la arquitectura monolítica existente, implementar microservicios autónomos, y adoptar protocolos HTTP/REST para acceso interoperable desde múltiples plataformas. Esta iteración también tendrá en cuenta las dependencias críticas entre los módulos para optimizar la resiliencia del sistema frente a fallos y escalabilidad bajo cargas variables.
El diseño en esta etapa busca sentar las bases para garantizar que las decisiones tomadas sean compatibles con la evolución de los microservicios y sus requisitos operativos, minimizando el impacto en la mantenibilidad y maximizando la satisfacción del consumidor.

### Drivers considerados
- QA2 (Mantenibilidad - Escalabilidad)
- QA3 (Disponibilidad)
- QA5 (Interoperabilidad - Portabilidad)
- RF1 (El cliente debe poder acceder a los datos personales.)
- RF6 (Para los pagos, se debe usar de apoyo una pasarela de pago externa de Mercado Libre.)
- RF9 (Se debe sustituir el acceso a datos por protocolos HTTP/REST.)
- RF10 (Descomponer la arquitectura monolítica existente en microservicios autónomos para cada módulo funcional.)

### Decisiónes tomadas
- [High Availability Pattern para Arquitectura de Microservicios](https://github.com/Adanzin/TPE_DISE-O/blob/399a12c6a0e978c3e7603cb3d7a5c2a3e227cb8d/docs/decisions/0001-High-Availability-Pattern-para-Arquitectura-de-Microservicios.md)

### Diagramas de la decision
- [Diagrama de Modulos](https://github.com/Adanzin/TPE_DISE-O/blob/399a12c6a0e978c3e7603cb3d7a5c2a3e227cb8d/docs/decisions/0001-High-Availability-Pattern-para-Arquitectura-de-Microservicios.md)

## ITERACION 2
Este ADR aborda las decisiones necesarias para implementar un patrón de arquitectura tolerante a fallos que permita cumplir con los atributos de calidad y requisitos funcionales más críticos del sistema. El enfoque se centra en asegurar alta disponibilidad, confiabilidad y manejo eficiente de fallos en componentes clave como Clientes y Pagos, sin comprometer la escalabilidad ni el rendimiento del sistema.
Este ADR busca establecer un marco sólido para gestionar transacciones sensibles, mantener la continuidad operativa y satisfacer las expectativas de los usuarios.

### Drivers considerados
- QA6 (Tolerancia a Fallos)
- QA4 (Seguridad) 
- RF5 (Se debe poder emitir reportes de incidencias (camión averiado, reparto no realizado, etc) a los gestores de rutas.)

### Decisiónes tomadas
- [Patrón de Arquitectura Tolerante a Fallos para un Sistema Basado en Microservicios](https://github.com/Adanzin/TPE_DISE-O/blob/545773748f595be49f708dece5a9e1dba5d790d1/docs/decisions/0002-Patr%C3%B3n-de-Arquitectura-Tolerante-a-Fallos-para-un-Sistema-Basado-en-Microservicios.md)

## ITERACION 3
Este ADR se centra en la adopción del patrón API Gateway para el módulo de Reparto y Rutas, con el objetivo de satisfacer requisitos clave de rendimiento, escalabilidad y tiempos de respuesta rápidos. En esta iteración, se analizan los desafíos de manejar un alto volumen de tráfico y la necesidad de enrutar eficientemente las solicitudes hacia los microservicios correspondientes, mientras se integran mecanismos que mejoren la seguridad y el control del sistema.
Se abordan las implicaciones técnicas del patrón, sus ventajas, como la composición de resultados de múltiples servicios y su capacidad para gestionar tráfico intensivo, y sus desventajas, como la complejidad adicional que podría introducir en la arquitectura. Además, se exploran alternativas como el balanceador de carga y el almacenamiento en caché, evaluando su viabilidad frente a los objetivos del sistema. Este documento establece la base para garantizar una experiencia de usuario eficiente y un desempeño robusto en este módulo crítico del sistema.

### Drivers considerados
- QA7 (Rendimiento)
- RF8 (La gestión de repartos y rutas cuentan con 2 algoritmos de optimización seleccionados en función de la demora del camión.)

### Decisión tomada
- [Patrón API Gateway para Reparto y Rutas](https://github.com/Adanzin/TPE_DISE-O/blob/545773748f595be49f708dece5a9e1dba5d790d1/docs/decisions/0003-Patr%C3%B3n-API-Gateway-para-Reparto-y-Rutas.md)

## ITERACION 4
En esta iteración, el foco principal fue manejar el incremento de carga en el módulo de Pedidos, garantizando un rendimiento óptimo y escalabilidad frente a un aumento significativo en el número de pedidos por hora. Se tomó la decisión de implementar el patrón de Balanceo de Carga, el cual permite distribuir de manera eficiente las solicitudes entre los servicios disponibles, reduciendo la latencia y aumentando la predictibilidad para los clientes.
El diseño incluye un balanceador de carga configurado con un algoritmo que considera tanto la carga actual de los servicios como el número de solicitudes en cola, aprovechando la arquitectura de microservicios para facilitar el escalado horizontal. Este patrón se complementa con mecanismos de monitoreo y registro para garantizar su correcto funcionamiento y rápida detección de problemas.

### Drivers considerados
- QA1 (Escalabilidad)
- RF2 (El cliente debe poder realizar pedidos de los productos de la empresa. (Máximo 3 intentos fallidos))
- RF3 (El sistema de pedidos pasa siempre por 3 fases (preprocesado, autorización y aceptación). No se puede pasar al siguiente estado sin haber procesado el anterior.)
- RF7 (La gestión de pedidos debe poder gestionar todas las peticiones de los pedidos de clientes y gestionar las incidencias en el reparto.)

### Decisiónes tomadas
- [Manejo del Incremento de Carga de Pedidos con el Patrón de Balanceo de Carga](https://github.com/Adanzin/TPE_DISE-O/blob/827739b298f04260732ad4bb1d2b100a871cf75d/docs/decisions/0004-Patr%C3%B3n-de-Balanceo-de-Carga-Registro-de-Decisi%C3%B3n-de-Arquitectura.md)

### Diagramas de la decision
- [Diagrama-de-Allocation-Arquitectura-Final](https://github.com/Adanzin/TPE_DISE-O/blob/827739b298f04260732ad4bb1d2b100a871cf75d/docs/imagenes/0004-Diagrama-de-Allocation-Final.png)
- [Diagrama-de-Flujo](https://github.com/Adanzin/TPE_DISE-O/blob/827739b298f04260732ad4bb1d2b100a871cf75d/docs/imagenes/0004-Diagrama-de-Flujo.jpeg)