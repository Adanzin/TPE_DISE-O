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

### Decisión tomada
- [High Availability Pattern para Arquitectura de Microservicios](https://github.com/Adanzin/TPE_DISE-O/blob/399a12c6a0e978c3e7603cb3d7a5c2a3e227cb8d/docs/decisions/0001-High-Availability-Pattern-para-Arquitectura-de-Microservicios.md)

### Diagramas de la decision
- [Diagrama de Modulos](https://github.com/Adanzin/TPE_DISE-O/blob/399a12c6a0e978c3e7603cb3d7a5c2a3e227cb8d/docs/decisions/0001-High-Availability-Pattern-para-Arquitectura-de-Microservicios.md)

## ITERACION 2
Este ADR aborda las decisiones necesarias para implementar un patrón de arquitectura tolerante a fallos que permita cumplir con los atributos de calidad y requisitos funcionales más críticos del sistema. El enfoque se centra en asegurar alta disponibilidad, confiabilidad y manejo eficiente de fallos en componentes clave como Clientes y Pagos, sin comprometer la escalabilidad ni el rendimiento del sistema.
Este ADR busca establecer un marco sólido para gestionar transacciones sensibles, mantener la continuidad operativa y satisfacer las expectativas de los usuarios.

### Decisión tomada
- [Patrón de Arquitectura Tolerante a Fallos para un Sistema Basado en Microservicios](https://github.com/Adanzin/TPE_DISE-O/blob/545773748f595be49f708dece5a9e1dba5d790d1/docs/decisions/0002-Patr%C3%B3n-de-Arquitectura-Tolerante-a-Fallos-para-un-Sistema-Basado-en-Microservicios.md)


## ITERACION 3
Este ADR se centra en la adopción del patrón API Gateway para el módulo de Reparto y Rutas, con el objetivo de satisfacer requisitos clave de rendimiento, escalabilidad y tiempos de respuesta rápidos. En esta iteración, se analizan los desafíos de manejar un alto volumen de tráfico y la necesidad de enrutar eficientemente las solicitudes hacia los microservicios correspondientes, mientras se integran mecanismos que mejoren la seguridad y el control del sistema.

Se abordan las implicaciones técnicas del patrón, sus ventajas, como la composición de resultados de múltiples servicios y su capacidad para gestionar tráfico intensivo, y sus desventajas, como la complejidad adicional que podría introducir en la arquitectura. Además, se exploran alternativas como el balanceador de carga y el almacenamiento en caché, evaluando su viabilidad frente a los objetivos del sistema. Este documento establece la base para garantizar una experiencia de usuario eficiente y un desempeño robusto en este módulo crítico del sistema.

### Decisión tomada
- [Patrón API Gateway para Reparto y Rutas](https://github.com/Adanzin/TPE_DISE-O/blob/545773748f595be49f708dece5a9e1dba5d790d1/docs/decisions/0003-Patr%C3%B3n-API-Gateway-para-Reparto-y-Rutas.md)

