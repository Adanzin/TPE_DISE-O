This document contains the functional requirements we elicited for the Farmacy Food system, based on the first Kata session and 
the documents provided to all teams. You will find the _actors_ we identified, and how they interact with the system in major scenarios.

# ***Actors***
- Cliente
- Sistema

<br>

# ***Cliente<sup>1</sup>***

## Manejo de cuenta
- El cliente debe poder acceder a los datos personales.

# ***Modulo Pedidos<sup>2</sup>***

## ***Pedidos*** 
- El cliente debe poder realizar pedidos de los productos de la empresa.
- El cliente tendrá permitido 3 intentos como máximo para hacer el pedido.
- El sistema de pedidos pasa siempre por 3 fases: preprocesado, autorización y aceptación.
- No se debe poder avanzar a la siguiente fase sin haber finalizado la anterior.

## Gestión
- La gestión de pedidos debe poder gestionar todas las peticiones de los pedidos de clientes.
- La gestión de pedidos debe gestionar las incidencias en el reparto.

<br>


# ***Reparto y Rutas <sup>3</sup>***

## Gestión
- La gestión de repartos y rutas debe contar con 2 algoritmos de optimización seleccionados en función de la demora del camión.

<br>


# ***Estadísticas <sup>4</sup>***

## Emisión de Estadísticas
- Se deben poder obtener estadísticas con información del cliente. 
- Se deben poder obtener estadísticas del estado de los pedidos.
- Se deben poder obtener estadísticas sobre la situación real de los camiones.

<br>


# ***Incidencias <sup>5</sup>***

## Emisión de Incidencias
- Se debe poder emitir reportes de incidencias (camión averiado, reparto no realizado, etc) a los gestores de rutas.

<br>


# ***Pagos <sup>6</sup>***

## Seguridad de Pagos
- Se debe integrar y usar de apoyo una pasarela de pago externa de Mercado Libre.

<br>


# ***Arquitectura <sup>7</sup>***

## Conexion
- Se debe sustituir el acceso a datos por protocolos HTTP/REST.

## Arquitectura
- Se debe descomponer la arquitectura monolítica existente a microservicios autónomos. 

<br>
