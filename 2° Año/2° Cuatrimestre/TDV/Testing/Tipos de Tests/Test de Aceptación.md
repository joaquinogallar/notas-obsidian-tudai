## Definición

Los **test de aceptación** son pruebas realizadas para verificar si un sistema cumple con los criterios de aceptación y requisitos establecidos por los interesados (clientes, usuarios finales, etc.). Estos tests aseguran que el software funciona como se espera y satisface las necesidades del negocio.

## Propósito

- **Validar requisitos**: Asegurar que el sistema cumple con los requisitos funcionales y no funcionales definidos.
- **Verificación final**: Probar el sistema en condiciones que simulan el uso real antes de su implementación en producción.
- **Satisfacción del cliente**: Confirmar que el software satisface las expectativas del cliente y los usuarios finales.

## Características

- **Enfoque en el usuario**: Los test de aceptación se centran en la experiencia del usuario y cómo interactúa con el sistema.
- **Basados en criterios**: Se definen en base a criterios de aceptación específicos que deben cumplirse para que una funcionalidad se considere completa.
- **Pruebas manuales o automatizadas**: Pueden llevarse a cabo de forma manual o a través de herramientas de automatización.

## Tipos de Test de Aceptación

1. **Pruebas de Aceptación del Usuario (UAT)**: Realizadas por los usuarios finales para validar el sistema.
2. **Pruebas de Aceptación del Cliente**: Realizadas por los clientes para asegurar que el sistema cumple con sus requisitos.
3. **Pruebas de Aceptación de Negocio**: Focalizadas en verificar si el software se ajusta a los procesos y políticas del negocio.

## Ejemplo de Test de Aceptación

```gherkin title:Gherkin
Feature: Registro de Usuario

  Scenario: Registro exitoso con datos válidos
    Given un usuario en la página de registro
    When el usuario ingresa su nombre, email y contraseña válidos
    Then el usuario debe ser registrado y redirigido a la página de bienvenida