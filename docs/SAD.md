# SAD (System Architecture Document)

===========================================================
### Contexto
El sistema existente utiliza dos bases de datos SQL para gestionar información de Clientes y Pedidos. El objetivo principal es transformar este sistema en una arquitectura moderna basada en microservicios, con acceso a través de protocolos HTTP/REST. Los principales requisitos incluyen:

### Solución Integral Basada en Patrones Arquitectónicos para la Migración a Microservicios
Este documento presenta la solución arquitectónica para la migración de un sistema monolítico a una arquitectura basada en microservicios, optimizada para manejar alta disponibilidad, escalabilidad, tolerancia a fallos y tiempos de respuesta rápidos. La solución se basa en cuatro patrones arquitectónicos principales: Alta Disponibilidad, Tolerancia a Fallos, API Gateway, y Balanceo de Carga.

1. Alta disponibilidad para los módulos críticos (Clientes, Pagos y Reparto y Rutas).
2. Escalabilidad para manejar el creciente volumen de pedidos.
3. Tolerancia a fallos para garantizar continuidad operativa.
4. Respuesta eficiente (<2 segundos) en los módulos más sensibles, como Pedidos y Reparto y Rutas.

## Decisiones Arquitectónicas
1. Patrón de Alta Disponibilidad
-   Motivación: Garantizar que el sistema pueda responder al 99,9% de las solicitudes, minimizando tiempos de inactividad.
-   Implementación:
    -   Uso de balanceadores de carga distribuidos para asegurar redundancia.
    -   Replicación de bases de datos para evitar puntos únicos de fallo.
    -   Monitoreo constante para detectar y resolver problemas proactivamente.
-   Beneficio: Continuidad en los módulos críticos y experiencia consistente para los usuarios.

2. Patrón de Tolerancia a Fallos
-   Motivación: Mitigar el impacto de errores en los módulos críticos (Pagos y Reparto y Rutas).
-   Implementación:
    -   Conmutación por error (failover) entre servicios en caso de fallas.
    -   Uso de circuit breakers y patrones de retry para manejar errores parciales.
    -   Integración con mecanismos de notificación en tiempo real para alertar sobre incidencias.
-   Beneficio: Resiliencia frente a fallos y menor impacto en la operación del sistema.

3. Patrón API Gateway para Reparto y Rutas
-   Motivación: Gestionar el alto tráfico y asegurar tiempos de respuesta rápidos en un módulo crítico.
-   Implementación:
    -   Enrutamiento basado en reglas HTTP hacia microservicios específicos.
    -   Composición de APIs para combinar datos de múltiples fuentes en una sola respuesta.
    -   Capa de autenticación y autorización para reforzar la seguridad.
-   Beneficio: Gestión eficiente del tráfico y funcionalidad integrada en módulos complejos.

4. Patrón de Balanceo de Carga
-   Motivación: Distribuir la carga uniformemente entre los microservicios para mantener un rendimiento óptimo.
-   Implementación:
    -   Algoritmo Weighted Round Robin para priorizar instancias más eficientes.
    -   Integración con herramientas de monitoreo para detectar cuellos de botella.
    -   Compatibilidad con escalado automático para adaptarse a picos de demanda.
-   Beneficio: Escalabilidad y latencia reducida, especialmente para el módulo de Pedidos.

# Arquitectura Final
Integrando las decisiones anteriores, el sistema adoptará la siguiente arquitectura:

1.  Módulos Críticos (Clientes, Pagos y Reparto y Rutas):

-   Alta disponibilidad garantizada mediante redundancia y balanceo de carga.
-   API Gateway como punto de entrada unificado para enrutamiento eficiente.
-   Tolerancia a fallos con conmutación por error y circuit breakers.

2.  Módulos Semi-Críticos (Pedidos e Incidencias):

-   Escalabilidad horizontal con balanceo de carga y escalado automático.
-   Monitoreo continuo para asegurar tiempos de respuesta consistentes.

3.  Módulos No Críticos (Estadísticas):

-   Acceso optimizado mediante almacenamiento en caché para reducir la carga en la base de datos.

4.  Tecnologías Clave:
-   Kubernetes para orquestar microservicios con escalado automático.
-   NGINX o AWS API Gateway para implementar el patrón API Gateway.
-   HAProxy o balanceadores nativos de la nube para distribuir la carga.

### Esta solución aborda los principales requisitos del sistema al:

-   Garantizar disponibilidad y escalabilidad mediante patrones bien integrados.
-   Reducir riesgos de fallos mediante mecanismos proactivos.
-   Mejorar la experiencia del usuario con tiempos de respuesta rápidos.

## Diagramas de la Arquitectura Final
### Diagrama de Allication 
Este diagrama muestra la relación entre el software y el hardware o entre componentes lógicos.
![Diagrama-de-Allocation](https://github.com/Adanzin/TPE_DISE-O/blob/827739b298f04260732ad4bb1d2b100a871cf75d/docs/imagenes/0004-Diagrama-de-Allocation-Final.png)

### Diagrama de Flujo
Este diagrama describe procesos, interacciones entre componentes o pasos secuenciales en la lógica del sistema. 
![Diagrama-de-Flujo](https://github.com/Adanzin/TPE_DISE-O/blob/827739b298f04260732ad4bb1d2b100a871cf75d/docs/imagenes/0004-Diagrama-de-Flujo.jpeg)
