# ADR 004: Uso de colas de mensajes para la comunicación asincrónica entre servicios

## Estado
PROPUESTA - 07/12/2023

## Contexto
En el contexto de nuestra migración a una arquitectura de microservicios para el sistema de billetera virtual, la comunicación efectiva y eficiente entre servicios es crucial. Hasta ahora, la comunicación entre servicios ha sido predominantemente sincrónica. Para mejorar la escalabilidad y la fiabilidad del sistema, proponemos introducir la comunicación asincrónica.

## Decisión
Decidimos implementar colas de mensajes SQS (Simple Queue Service) y un sistema de publicación-suscripción utilizando SNS (Simple Notification Service) para la comunicación asincrónica entre servicios.

### Justificación de la Decisión
- **Fiabilidad y escalabilidad**: la comunicación asincrónica a través de colas SQS y SNS proporcionará un mecanismo robusto y escalable para el manejo de mensajes entre servicios.
- **Desacoplamiento de servicios**: ayuda a desacoplar los servicios, permitiendo que operen de manera más independiente y manejen las solicitudes a su propio ritmo.
- **Mejora en el manejo de cargas de trabajo pico**: Proporciona un enfoque más eficiente para manejar picos de carga, ya que los mensajes pueden ser encolados y procesados gradualmente.

## Riesgos y Restricciones
- **Complejidad adicional**: introducir un sistema de colas de mensajes agrega una capa adicional de complejidad en la arquitectura.
- **Requerimientos de monitorización y alertas**: necesidad de un sistema de monitorización y alertas robusto para manejar y supervisar el flujo de mensajes.
- **Capacitación del equipo**: el equipo puede requerir formación adicional en la gestión y el uso de sistemas de colas de mensajes y publicación-suscripción.

## Alternativas Consideradas
- Mantener la comunicación sincrónica como única forma de comunicación, pese a sus limitaciones en términos de escalabilidad.

## Consecuencias
- Mejora significativa en la fiabilidad y eficiencia de la comunicación entre servicios.
- Mayor flexibilidad y escalabilidad en la arquitectura de microservicios.
- Necesidad de gestionar la complejidad adicional y asegurar un monitoreo efectivo.
- Potencial mejora en el manejo de cargas de trabajo y eficiencia en el procesamiento de tareas.
