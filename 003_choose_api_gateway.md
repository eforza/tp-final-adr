# ADR 003: Implementación de un API Gateway en la Arquitectura de Microservicios

## Estado
ACEPTADO - 06/12/2023

## Contexto
En el proceso de migrar nuestra arquitectura de billetera virtual a microservicios, surgió la necesidad de gestionar eficientemente las interacciones entre los clientes y los diversos servicios, tanto en la aplicación monolítica existente como en los nuevos microservicios.

## Decisión
Hemos decidido implementar un API Gateway como el punto de entrada unificado para todas las interacciones con los microservicios. Este API Gateway actuará como un intermediario que maneja y enruta las solicitudes a los servicios apropiados, ya sea en el monolito existente o en los nuevos microservicios.

### Justificación de la Decisión
- **Simplificación de Interacciones con Clientes**: Proporciona un único punto de entrada, lo que simplifica la interacción de los clientes con nuestro sistema.
- **Facilidad en el Enrutamiento**: Permite un enrutamiento eficiente y claro de las solicitudes a los servicios correspondientes, independientemente de si están en el monolito o distribuidos como microservicios.
- **Flexibilidad en la Migración**: A medida que se trasladan funciones al nuevo servicio, el API Gateway se puede actualizar fácilmente para apuntar a estos, facilitando una migración gradual y controlada.
- **Seguridad y Control Centralizado**: Ofrece un punto para implementar medidas de seguridad, como autenticación y autorización, así como para realizar un seguimiento y monitorización del tráfico.

## Alternativas Consideradas
- Uso de un enfoque basado en enrutamiento a nivel de balanceadores de carga o a través de un servicio de descubrimiento.
- Mantener múltiples puntos de entrada para diferentes servicios, pero se descartó por la complejidad adicional para los clientes y el mantenimiento.

## Consecuencias
- Mejora en la gestión de solicitudes y enrutamiento hacia los servicios apropiados.
- Centralización de políticas de seguridad y control de tráfico.
- Potencial incremento en la complejidad de la arquitectura y en los requerimientos de mantenimiento.
- Mayor flexibilidad en la gestión y despliegue de servicios nuevos y existentes.
