# ADR 001: Migración a microservicios para el sistema de billetera virtual

## Estado
ACEPTADO - 07/12/2023

## Contexto
El sistema actual de billetera virtual se basa en un backend de Java con Spring Boot, encapsulando todas las funcionalidades, incluyendo el procesamiento de transacciones de pago, lectura de QR, manejo de cuentas de usuario y seguridad, en una única aplicación denominada Core. La aplicación se ejecuta en contenedores Docker y utiliza una única base de datos para el almacenamiento de datos.

Problemas del Sistema Actual
- **Escalabilidad**: Dificultades para escalar durante picos de demanda debido a que todos los servicios corren en la misma aplicación.
- **Mantenimiento y actualización**: Retos en mantener y actualizar el sistema por tener un único proyecto y repositorio. Conflictos frecuentes en merges de código debido a la superposición en el trabajo en diferentes funcionalidades.
- **Rendimiento**: Cuellos de botella en ciertos servicios que necesitan diferentes soportes de infraestructura.

## Decisión
Decidimos migrar de una arquitectura monolítica a una basada en microservicios. Esta decisión está dirigida a mejorar la escalabilidad, la mantenibilidad y facilitar la introducción de nuevas características.

## Restricciones y Riesgos Identificados
- **Equipo con conocimiento limitado en microservicios** y poca experiencia (seniority).
- Riesgos de **aumentar la complejidad** en la gestión de servicios distribuidos y comunicación entre microservicios.
  
## Alternativas Consideradas
- Refactorización del monolito sin migrar a microservicios.
- Uso de arquitectura serverless para ciertos componentes.

## Consecuencias
- Se espera una mejora en la escalabilidad y el rendimiento del sistema.
- Mayor flexibilidad para el desarrollo y despliegue de nuevas funcionalidades.
- Posibles desafíos iniciales debido a la curva de aprendizaje del equipo y la complejidad de la nueva arquitectura.
