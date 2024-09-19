## Arquitectura de Microservicios

Nuestra arquitectura de microservicios se basa en la separación de responsabilidades, alta cohesión dentro de los servicios y baja dependencia entre ellos, permitiendo un desarrollo, despliegue y escalado independiente. Los microservicios se comunican a través de APIs bien definidas y documentadas, utilizando tecnologías modernas que garantizan alta disponibilidad, seguridad y eficiencia.

### Herramientas y Tecnologías

- **IntelliJ IDEA**: IDE que facilita el desarrollo de microservicios en Java, integrando plugins para Docker, Kubernetes y GitLab.
- **VSCode**: Editor de código versátil, utilizado para el desarrollo de servicios en NodeJS y la manipulación de archivos de configuración.
- **Spring Boot**: Framework que simplifica el desarrollo de microservicios, proporcionando inyección de dependencias, configuración flexible y soporte para aplicaciones reactivas con WebFlux.
- **MongoDB**: Base de datos NoSQL que almacena los datos distribuidos de los microservicios, permitiendo alta escalabilidad y rendimiento.
- **Firebase**: Plataforma utilizada para gestionar la autenticación y autorización en la arquitectura de microservicios, integrando roles y permisos dinámicos.
- **GitLab**: Sistema de control de versiones y CI/CD que permite la automatización de pruebas y despliegues de los microservicios en un entorno de integración continua.
- **GitHub**: Alternativa para gestionar el código fuente, con integración a herramientas de revisión de código y automatización de workflows.
- **WebFlux**: Parte de Spring Framework utilizada para el desarrollo de aplicaciones reactivas y no bloqueantes, esencial en una arquitectura de microservicios de alta concurrencia.
- **SpringDoc OpenAPI**: Herramienta que genera la documentación interactiva de nuestras APIs REST, facilitando la comunicación entre servicios y la integración con terceros.
- **Docker**: Tecnología de contenedorización que encapsula los microservicios y sus dependencias, asegurando que cada servicio funcione de manera consistente en cualquier entorno.
- **Kubernetes**: Sistema de orquestación de contenedores que gestiona el despliegue, escalado y operación de los microservicios, garantizando alta disponibilidad y resiliencia ante fallos.
- **GCP Cloud**: Plataforma de nube pública que soporta el despliegue y escalado de los microservicios, aprovechando servicios gestionados como balanceadores de carga y bases de datos en la nube.
- **Railway**: Proveedor de infraestructura que permite un despliegue rápido de microservicios, ideal para entornos de desarrollo y pruebas.
- **SonarQube**: Herramienta utilizada para analizar la calidad del código y aplicar buenas prácticas en la implementación de los microservicios.
- **JUnit**: Framework de pruebas unitarias que garantiza que cada microservicio funcione correctamente de forma independiente.

### Organización en Multirepo

Nuestra arquitectura de microservicios está organizada en un enfoque **Multirepo**, donde cada microservicio tiene su propio repositorio de código independiente. Este enfoque proporciona varias ventajas:

- **Desarrollo Independiente**: Cada equipo o desarrollador puede trabajar en su microservicio de forma aislada, permitiendo diferentes ciclos de vida y versiones sin afectar a otros servicios.
- **Facilidad de Despliegue**: Al estar desacoplados a nivel de repositorio, los microservicios pueden ser desplegados y versionados de manera independiente.
- **Control Granular de CI/CD**: Los pipelines de CI/CD se definen por separado para cada repositorio, facilitando una mayor personalización y control sobre el proceso de integración continua.
- **Manejo Simplificado de Dependencias**: Cada microservicio gestiona sus propias dependencias sin riesgo de interferir con otros servicios, lo que permite mayor flexibilidad en la adopción de nuevas tecnologías o librerías.

### Interacciones entre Microservicios

Los microservicios en nuestra arquitectura se comunican entre sí utilizando dos principales enfoques para la interacción sincrónica:

- **WebClient (Spring WebFlux)**: Para llamadas no bloqueantes y asíncronas entre microservicios. WebClient nos permite realizar solicitudes HTTP con soporte para programación reactiva, mejorando la eficiencia y la capacidad de manejar un gran número de solicitudes simultáneas sin bloquear recursos.
- **FeignClient**: Utilizado para realizar llamadas HTTP a otros microservicios de manera más declarativa. FeignClient se integra fácilmente con Spring Cloud y permite simplificar las interacciones entre microservicios utilizando anotaciones.

### Principios de Diseño

- **Desacoplamiento**: Los microservicios están diseñados para ser completamente independientes, lo que facilita su despliegue y desarrollo sin afectar otros servicios.
- **Escalabilidad Horizontal**: La arquitectura permite escalar cada microservicio de manera independiente, según la demanda específica.
- **Comunicación a través de APIs**: Los microservicios se comunican entre sí mediante APIs REST documentadas y seguras, utilizando JSON como formato de intercambio de datos.
- **Resiliencia y Recuperación**: Se implementan patrones como circuit breakers para garantizar la tolerancia a fallos y la capacidad de recuperación automática.
- **Seguridad**: El uso de Firebase para la gestión de identidades y roles asegura que solo usuarios autorizados puedan acceder a cada microservicio, cumpliendo con estrictos requisitos de seguridad.
- **Despliegue Continuo**: Utilizamos pipelines de CI/CD con GitLab para automatizar el despliegue de los microservicios, lo que permite actualizaciones rápidas y controladas en producción.

### Ventajas de la Arquitectura

- **Desarrollo Independiente**: Los equipos pueden trabajar de manera autónoma en diferentes microservicios, sin bloquear el trabajo de otros equipos.
- **Escalabilidad y Rendimiento**: Al poder escalar servicios específicos, la arquitectura responde mejor a las necesidades de la aplicación en términos de tráfico y carga.
- **Mantenibilidad**: La separación clara entre servicios hace que el código sea más fácil de mantener y entender, facilitando la adopción de nuevas tecnologías en microservicios específicos sin afectar al sistema completo.
- **Tolerancia a Fallos**: Los errores en un microservicio no afectan al resto de la aplicación, garantizando mayor disponibilidad.
- **Adaptabilidad**: La arquitectura es flexible y puede adaptarse a nuevas funcionalidades y requisitos sin un rediseño completo del sistema.

### Desafíos

- **Complejidad de la Orquestación**: Gestionar múltiples microservicios implica desafíos adicionales en la configuración, orquestación y monitoreo, lo que es mitigado con el uso de Docker, Kubernetes y soluciones de CI/CD.
- **Consistencia de Datos**: En una arquitectura distribuida, mantener la consistencia de datos entre microservicios puede ser complicado, por lo que implementamos estrategias como la consistencia eventual.

Esta combinación de tecnologías y principios de diseño nos permite construir un sistema robusto, escalable y eficiente que responde a las necesidades de nuestra organización.
