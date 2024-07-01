# Portada
**Grupo Uno**

**Caso de estudio: “Servicio Técnico de Celulares y Manejo de Stock con Inventario”**

David Durán V.

Alexandra Costa P.

# ÍNDICE

## INTRODUCCIÓN

### ANÁLISIS DE REQUISITOS

#### 1.	REQUISITOS FUNCIONALES 

##### 1.1 Gestión de Clientes:
Registrar clientes nuevos, visualizar datos de clientes ya registrados pudiendo editarlos y contar con el historial de reparaciones por cliente.

##### 1.2 Gestión de Reparaciones:
Registrar las reparaciones agendadas por los clientes, añadiendo detalles sobre el equipo a reparar, las fallas que ha manifestado y su posible diagnóstico. Seguir el estado de la reparación y etiquetar según su etapa (pendiente, en proceso, completada). Asignar técnicos especialistas según lo requiera cada caso y registrar todo lo que se hizo durante la reparación del celular.

##### 1.3 Gestión de Stock de Repuestos:
Inventario con información sobre los repuestos y accesorios que se tienen en stock, pudiendo actualizar dichos datos a medida que se realizan las reparaciones a los teléfonos móviles, contando además con un sistema de alertas que notifique la posible escasez de algún material.

##### 1.4	Facturación: 
Emitir boletas cuando se haya completado una reparación, apuntar los pagos efectuados por los clientes y mantener el registro de cada movimiento de dinero, ya sea por compras o por ventas.

###### 1.5	Reportes y Estadísticas:
Reportar las reparaciones que se estén realizando, designar un tiempo promedio de reparación y armar estadísticas sobre el inventario y las ventas.

#### 2.	REQUISITOS NO FUNCIONALES

##### 2.1	 Seguridad:
   - Autenticación y autorización robustas para proteger los datos, tanto de la empresa como la de los clientes.
   - Protección contra accesos no autorizados y ataques cibernéticos.

##### 2.2	Rendimiento:
   - Tiempos de respuesta rápidos para consultas y actualizaciones del estado de las reparaciones.
   - Manejar grandes volúmenes de datos sobre el historial de clientes y reparaciones.

##### 2.3 Usabilidad:
   - Interfaz de usuario fácil de usar, entendible y clara, tanto para clientes que deseen acceder al estado de reparación de su equipo, como para técnicos que estén realizando dicha reparación.
   - Soporte multiplataforma.

##### 2.4 Disponibilidad:
   - Aplicación con funcionamiento 24/7, respaldada en múltiples servidores.

##### 2.5 Escalabilidad:
   -Capacidad de soportar el incremento de usuarios en línea consultando, sin generar fallos en la aplicación.

##### 2.6 Mantenibilidad:
   - Código correctamente estructurado y comentado en cada segmento para hacerlo más legible y así manipularlo para su corrección o actualización.
##### 2.7 Cumplimiento Normativo:
   - Cumplir las normas ISO/IEC 27000 que garantizan la seguridad de la información.


### EJEMPLOS DE CASOS DE USO:

- Caso de Uso Funcional: El técnico registra una nueva reparación, especificando marca y modelo del celular, los síntomas reportados y el diagnóstico inicial. 

Aquí en el siguiente diagrama podemos ver un caso de uso donde se ve la relación, entre usuarios y personal tanto administrativo como personal de trabajo.

Para contextualizar el caso de uso solicitado “El técnico registra una nueva reparación, especificando marca y modelo del celular, los síntomas reportados y el diagnóstico inicial”: 

[Imagen del tecnico](assets/tecnico.jpg)

- Caso de Uso No Funcional: La aplicación debe asegurar que los datos de los clientes estén encriptados y solo accesibles a personal autorizado.
DISEÑO SEGURO

Arquitectura de Microservicios:
Divide la aplicación en servicios más pequeños y específicos, facilitando el mantenimiento, la escalabilidad e implementación de políticas de seguridad específicas para cada servicio. Y cada microservicio puede tener sus propios controles de acceso y autenticación, para que así puedan acceder a datos privados sólo los servicios que lo requieren.

Autenticación y Autorización Centralizadas:

Capa de API Segura:

* HTTPS (TLS/SSL): HTTPS es el protocolo seguro de transferencia de hipertexto que utiliza cifrado TLS/SSL para proteger todas las comunicaciones entre el cliente y el servidor. Esto asegura que los datos transmitidos no sean interceptados ni modificados por terceros malintencionados.

* Prevención de ataques DDoS: Los ataques de denegación de servicio distribuidos (DDoS) pueden saturar un servidor con solicitudes maliciosas, causando una interrupción del servicio. Para mitigar esto, se implementan mecanismos como el rate limiting (limitación de velocidad de las solicitudes) para limitar la cantidad de solicitudes que un cliente puede realizar en un período de tiempo determinado.

* Protección contra inyecciones de código: Inyecciones de código como SQL injection y XSS son ataques comunes en los cuales un atacante inserta código malicioso en una aplicación a través de los datos de entrada. Para prevenirlos, se utilizan prácticas de codificación segura y validación de datos de entrada para asegurar que no contengan comandos SQL o scripts maliciosos que puedan ejecutarse en el contexto del servidor.

• Implementar OAuth 2.0 para autenticación de usuarios y JWT (JSON Web Tokens) para asegurar las comunicaciones entre servicios y clientes.

### 4. Base de Datos Segura:
   - Utilizar bases de datos robustas que soporten cifrado de datos en reposo y en tránsito.
   - Aplicar principios de mínimos privilegios, asegurando que cada componente de la aplicación solo tenga acceso a los datos que necesite para funcionar.

### 5. Monitoreo y Auditoría:

   - Implementar herramientas de monitoreo y registro de eventos (logging) para detectar y responder rápidamente a posibles brechas de seguridad o comportamientos anómalos.
   - Establecer alertas para eventos de seguridad críticos (por ejemplo, intentos de acceso no autorizado).

### 6. Actualizaciones y Parches de Seguridad:

   - Mantener actualizados todos los componentes de la aplicación, incluyendo frameworks, librerías y sistemas operativos, para mitigar vulnerabilidades conocidas.
   - Implementar un proceso de revisión de código y pruebas de penetración periódicas para identificar y corregir posibles vulnerabilidades.


### 7. Resiliencia y Recuperación ante Desastres:

   - Implementar copias de seguridad regulares de la base de datos y de los datos críticos.
   - Tener un plan de recuperación ante desastres para restaurar la aplicación rápidamente en caso de fallos graves o ataques.

# IMPLEMENTACIÓN SEGURA

Implementar prácticas de codificación segura es fundamental para reducir vulnerabilidades y asegurar la robustez de tu aplicación web de gestión de reparaciones de celulares. Aquí tienes algunas prácticas específicas que puedes aplicar durante el desarrollo:

## 1. Validación de Entradas:
- Validación del lado del servidor. Validar y filtrar todos los datos recibidos para prevenir ataques como inyección de SQL, XSS (Cross-Site Scripting) y CSRF (Cross-Site Request Forgery).

- Validación del lado del cliente: La validación del lado del cliente puede mejorar la experiencia del usuario al detectar errores antes de enviar los datos al servidor.

# PRUEBAS Y VALIDACIÓN

## 1. Pruebas de Seguridad:

### a. Pruebas de Penetración (Penetration Testing):

- Contratación de especialistas: Contratar a equipos especializados en pruebas de penetración que puedan simular ataques de hackers reales. Estos profesionales pueden explorar vulnerabilidades conocidas (como inyecciones SQL, XSS, CSRF) y evaluar la resistencia de la aplicación frente a ellas.

- Escaneo de vulnerabilidades automáticas: Utilizar herramientas automatizadas como OWASP ZAP, Burp Suite, o Qualys para escanear la aplicación en busca de posibles vulnerabilidades. Estas herramientas pueden identificar problemas como configuraciones incorrectas de seguridad, puntos débiles en el código y más.

### b. Revisión de Código:

- Revisión manual del código: Realizar una revisión exhaustiva del código por parte de desarrolladores experimentados, con un enfoque en prácticas de codificación segura y buenas prácticas en el manejo de datos sensibles.

- Herramientas de análisis estático de código: Utilizar herramientas como SonarQube, Veracode o Checkmarx para realizar análisis estático del código y detectar posibles vulnerabilidades y malas prácticas de seguridad durante el desarrollo.

### c. Pruebas de Autenticación y Autorización:

- Pruebas de autenticación: Verificar que los mecanismos de autenticación implementados (por ejemplo, OAuth 2.0, JWT) sean robustos y seguros frente a ataques de suplantación de identidad y fuerza bruta.

- Pruebas de autorización: Asegurar que los roles y permisos estén correctamente implementados y que los usuarios solo tengan acceso a las funcionalidades y datos que corresponden a su rol específico.

## 2. Validación Exhaustiva:

### a. Pruebas Funcionales:

- Pruebas unitarias y de integración: Asegurar que todas las funciones y componentes de la aplicación estén probados adecuadamente, especialmente aquellas relacionadas con la gestión de datos sensibles y críticos.

- Pruebas de regresión: Ejecutar pruebas de regresión para verificar que las actualizaciones y cambios en el código no introduzcan nuevas vulnerabilidades o afecten la seguridad de la aplicación.

### b. Pruebas de Seguridad Funcional:

- Pruebas de sesión y gestión de cookies: Verificar que la gestión de sesiones y cookies sea segura, evitando riesgos como la suplantación de sesión (session hijacking) y la exposición de información sensible.

- Seguridad de la capa de transporte: Asegurar que todas las comunicaciones entre el cliente y el servidor estén protegidas mediante HTTPS para prevenir ataques de tipo man-in-the-middle.

## 3. Documentación y Reporte:

- Documentar los hallazgos: Mantener un registro detallado de todas las vulnerabilidades identificadas, las pruebas realizadas y las soluciones propuestas o implementadas.

- Generar informes de seguridad: Preparar informes de seguridad que resuman los resultados de las pruebas realizadas y proporcionen recomendaciones claras para mejorar la seguridad de la aplicación.

## 4. Capacitación y Concientización:

- Capacitación del equipo: Educar al equipo de desarrollo sobre prácticas de codificación segura y la importancia de la seguridad en el ciclo de vida del desarrollo de software.

- Concientización sobre seguridad: Sensibilizar a todos los miembros del equipo (desarrolladores, administradores, personal de soporte) sobre las amenazas comunes de seguridad y las mejores prácticas para mitigarlas.

# DOCUMENTACIÓN

## 1. Descripción General de la Aplicación:

- Propósito y Funcionalidad: Describir brevemente el propósito de la aplicación (gestión de reparaciones de celulares) y las principales funcionalidades que ofrece.

## 2. Requisitos de Seguridad:

- Lista de Requisitos de Seguridad: Enumera todos los requisitos de seguridad específicos que la aplicación debe cumplir, basados en estándares de seguridad como OWASP (Open Web Application Security Project) y normativas aplicables (por ejemplo, GDPR, CCPA).

## 3. Arquitectura y Diseño Seguro:

- Diagrama de Arquitectura: Proporcionar un diagrama de la arquitectura de la aplicación que incluya componentes clave como la capa de presentación, lógica de negocio, bases de datos, servicios externos, etc. Esto ayuda a visualizar cómo se manejan y protegen los datos en la aplicación.

- Descripción de Componentes de Seguridad: Para cada componente de la arquitectura, documentar las medidas de seguridad implementadas. Por ejemplo, la capa de API utiliza HTTPS para la comunicación segura, la autenticación se realiza mediante OAuth 2.0, etc.

## 4. Políticas de Seguridad y Privacidad:

- Políticas de Acceso y Control: Detallar las políticas de acceso y control de la aplicación, incluyendo roles y permisos de usuario, y cómo se gestionan.

- Política de Gestión de Contraseñas: Describir cómo se gestionan las contraseñas de los usuarios, incluyendo requisitos de complejidad, almacenamiento seguro (hashing + salting) y políticas de cambio periódico de contraseñas.

## 5. Gestión de Identidades y Sesiones:

- Autenticación y Autorización: Documentar cómo se implementa la autenticación y autorización en la aplicación. Especificar los mecanismos utilizados (por ejemplo, JWT, tokens de sesión), la duración de las sesiones y las medidas para proteger contra ataques de suplantación de identidad.

## 6. Controles de Acceso:

- Segregación de Datos: Describir cómo se separan y protegen los datos sensibles de los usuarios y clientes en la aplicación. Explicar cómo se aplican los principios de mínimos privilegios.

## 7. Pruebas de Seguridad:

- Resultados de Pruebas de Seguridad: Incluir un resumen de los resultados de las pruebas de seguridad realizadas, como pruebas de penetración, análisis estático de código, y pruebas de vulnerabilidades.

- Acciones Correctivas: Documentar cualquier vulnerabilidad identificada durante las pruebas de seguridad y las acciones correctivas tomadas para mitigar esos riesgos.

## 8. Mantenimiento y Actualizaciones:

- Proceso de Actualización: Describir el proceso para mantener actualizados los componentes de la aplicación, incluyendo frameworks, librerías y sistemas operativos, para mitigar vulnerabilidades conocidas.

## 9. Cumplimiento Normativo:

- Cumplimiento de Normativas: Documentar cómo la aplicación cumple con ISO2700 y qué medidas se han implementado para proteger los datos personales y sensibles.

## 10. Plan de Respuesta a Incidentes:

- Plan de Respuesta a Incidentes: Incluir un plan detallado para responder a posibles incidentes de seguridad, cómo detectarlos, cómo responder rápidamente y cómo comunicarlos tanto internamente como externamente.

## 11. Revisiones y Actualizaciones:

- Revisión y Actualización del Documento: Establecer un plan para revisar y actualizar esta documentación de seguridad de manera periódica, especialmente después de cada cambio significativo en la aplicación o su infraestructura.

## Ejemplo de Documentación:

- Ejemplo de Documentación de Política de Contraseñas:
  - Requisitos mínimos de complejidad de contraseña.
  - Proceso de almacenamiento seguro de contraseñas.
  - Política de cambio periódico de contraseñas (si es aplicable).
  
- Ejemplo de Documentación de Política de Acceso:
  - Roles y permisos de usuario.
  - Proceso de asignación y revocación de permisos.
  - Auditoría de accesos y registros de actividad.

# CONCLUSIÓN

Mediante el presente informe podemos concluir que, habiendo analizado el caso de uso que nos fue asignado, las prácticas de seguridad son realmente vitales para el correcto desempeño de este servicio, tanto para el tratamiento de datos sensibles que se albergan, como para mantener este servicio en el tiempo sin comprometer la integridad de la empresa y sus participantes.

Además, es crucial mantener establecido un correcto orden en el flujo de trabajo y de cada paso que le concierne, ya que cualquiera de estos procesos ejecutándose de manera anticipada, obviando su paso antecesor, podría generar graves conflictos en la consecución de las reparaciones, la entrega oportuna de los móviles ya arreglados, e incluso impactar negativamente en la satisfacción del cliente; finalmente, todo descontento en la clientela golpeará con severidad la imagen de la empresa, causando importantes pérdidas económicas y una probable quiebra. 

REFERENCIAS
