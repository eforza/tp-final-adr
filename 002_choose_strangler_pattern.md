# ADR 002: Uso del Patrón Strangler para la migración a microservicios

## Estado
ACEPTADO - 07/12/2023

## Contexto
Como parte de la transición a una arquitectura de microservicios en nuestro sistema de billetera virtual, se propone la adopción del patrón Strangler para la migración. Este patrón implica reemplazar gradualmente partes de la aplicación existente con nuevos servicios.

## Decisión
Hemos decidido utilizar el patrón Strangler para la migración a microservicios, comenzando con los servicios más pequeños y débilmente acoplados. Esto incluye la migración inicial del Notificacion Service y del QR Service, seguido por el Payment Service y, finalmente, el Customer Service.

Orden de Migración
1. **NotificacionService**: Debido a su menor complejidad y acoplamiento débil.
2. **QRService**: Por su interfaz clara con el resto del sistema.
3. **PaymentService**: A pesar de ser el más complejo, es el de mayor valor para la unidad de negocio.
4. **CustomerService**: Se migra al final para abordar la complejidad y los desafíos después de ganar experiencia.

### Justificación de la Decisión
- **Minimizar el riesgo**: Comenzar con servicios más pequeños y menos complejos reduce el riesgo y permite que el equipo gane experiencia en la migración.
- **Aprendizaje progresivo**: Permite al equipo desarrollar competencias en microservicios gradualmente, lo cual es crucial dado el conocimiento limitado y la experiencia del equipo.

## Riesgos y Restricciones
- **Limitación de experiencia**: El equipo tiene conocimiento y experiencia limitados en microservicios.
- **Complejidad del PaymentService**: El alto valor y complejidad del Payment Service representa un desafío significativo.

## Alternativas Consideradas
- Migración empezando por el dominio de mayor valor para el negocio (en este caso, PaymentService), pero se descartó debido al riesgo y la curva de aprendizaje del equipo.

## Consecuencias
- Se espera una implementación más controlada y de menor riesgo de la nueva arquitectura de microservicios.
- Posible demora en la realización de beneficios significativos hasta que los servicios de mayor valor sean migrados.
- Mayor confianza y competencia del equipo en la gestión de microservicios a medida que avanza el proyecto.


