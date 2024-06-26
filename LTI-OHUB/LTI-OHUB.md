# **SMART PEOPLE LTI** ![Icon](https://cdn-icons-png.flaticon.com/128/2896/2896418.png)

## Descripción del Software
**SMART PEOPLE LTI** es un sistema de seguimiento de candidatos (ATS) innovador que promete revolucionar la eficiencia de los departamentos de recursos humanos, mejorando en un 50% su efectividad en comparación con los sistemas ATS más vendidos en el mercado. Este software facilita la colaboración en tiempo real entre reclutadores y managers, automatiza tareas repetitivas y utiliza inteligencia artificial para optimizar la selección de candidatos.

## Valor Añadido y Ventajas Competitivas
### Valor Añadido:
- **Automatización Inteligente**: Automatiza tareas repetitivas utilizando IA, permitiendo que los reclutadores se enfoquen en tareas estratégicas.
- **Colaboración en Tiempo Real**: Mejora la comunicación y colaboración entre los miembros del equipo de recursos humanos.
- **Aprendizaje Automático**: Utiliza modelos de machine learning para aprender de los candidatos mejor seleccionados y mejorar continuamente el proceso de selección.

### Ventajas Competitivas:
- **Eficiencia Mejorada**: Asegura una mejora del 50% en la eficiencia de los departamentos de recursos humanos.
- **Integración Sencilla**: Se integra fácilmente con otros sistemas y herramientas de recursos humanos.
- **Interfaz Amigable**: Ofrece una interfaz intuitiva y fácil de usar.

## Funciones Principales
1. **Creación de Empleos**
2. **Publicación de Empleos**
3. **Recepción de Aplicaciones**
4. **Revisión de Aplicaciones**
5. **Realización de Pruebas en Línea**
6. **Programación de Entrevistas**
7. **Contratación de Candidatos**

### ¿Cómo Ayudan Estas Funciones?
- **Creación y Publicación de Empleos**: Facilita la creación de ofertas de trabajo y su publicación en múltiples plataformas.
- **Recepción y Revisión de Aplicaciones**: Centraliza y organiza todas las aplicaciones recibidas, permitiendo una revisión eficiente.
- **Realización de Pruebas y Programación de Entrevistas**: Automatiza el proceso de pruebas en línea y la programación de entrevistas, ahorrando tiempo y recursos.
- **Contratación de Candidatos**: Mejora el proceso de contratación mediante la colaboración en tiempo real y la evaluación basada en datos.

## Lean Canvas
- **Problema**: Ineficiencia en el proceso de selección de candidatos.
- **Segmento de Clientes**: Departamentos de recursos humanos de medianas y grandes empresas.
- **Propuesta de Valor**: Mejora en un 50% la eficiencia en la selección de candidatos mediante automatización e inteligencia artificial.
- **Solución**: Sistema ATS con funciones avanzadas de automatización, colaboración y aprendizaje automático.
- **Canales**: Venta directa, marketing digital, partnerships.
- **Flujos de Ingresos**: Suscripciones mensuales, licencias por usuario.
- **Recursos Clave**: Tecnología de IA, infraestructura en la nube, equipo de soporte técnico.
- **Actividades Clave**: Desarrollo de software, soporte al cliente, marketing y ventas.
- **Socios Clave**: Plataformas de empleo, empresas de tecnología de recursos humanos.
- **Estructura de Costos**: Desarrollo y mantenimiento del software, marketing, soporte al cliente.

## Casos de Uso Principales

### Caso de Uso 1: Publicación de Empleos
```mermaid
sequenceDiagram
    Actor RRHH
    RRHH ->> Sistema: Crear oferta de empleo
    Sistema ->> Redes Sociales: Publicar oferta
    Sistema ->> Sitio Web: Publicar oferta
    Redes Sociales ->> RRHH: Confirmación de publicación
    Sitio Web ->> RRHH: Confirmación de publicación
```

### Caso de Uso 2: Revisión de Aplicaciones
```mermaid
sequenceDiagram
    Actor Reclutador
    Reclutador ->> Sistema: Revisar aplicaciones
    Sistema ->> Base de Datos: Obtener aplicaciones
    Sistema ->> Reclutador: Mostrar aplicaciones
    Reclutador ->> Sistema: Seleccionar candidatos
```

### Caso de Uso 3: Programación de Entrevistas
```mermaid
sequenceDiagram
    Actor RRHH
    RRHH ->> Sistema: Programar entrevistas
    Sistema ->> Candidatos: Notificación de entrevista
    Candidatos ->> Sistema: Confirmación de asistencia
    Sistema ->> RRHH: Confirmación de entrevistas
```

## Modelo de Datos del Sistema
```mermaid
erDiagram
    CANDIDATO {
        int id
        string nombre
        string email
        string telefono
        string curriculum
    }
    EMPLEO {
        int id
        string titulo
        string descripcion
        string requisitos
        date fecha_publicacion
    }
    APLICACION {
        int id
        int candidato_id
        int empleo_id
        date fecha_aplicacion
    }
    ENTREVISTA {
        int id
        int candidato_id
        int empleo_id
        date fecha_entrevista
        string estado
    }

    CANDIDATO ||--o{ APLICACION: aplica
    EMPLEO ||--o{ APLICACION: recibe
    CANDIDATO ||--o{ ENTREVISTA: programa
    EMPLEO ||--o{ ENTREVISTA: agenda
```

## Diseño del Sistema a Alto Nivel

![image](https://github.com/oscarbuho888/AI4Devs-design/assets/13580205/ef29fe72-38df-4a1d-b720-ea2a9f8b443b)

## Diagrama C4
### Nivel 1: Contexto del Sistema
```mermaid
C4Context
    title Sistema SMART PEOPLE LTI

    Person(cliente, "Cliente", "Usuario del sistema de ATS")
    System(smart_people_lti, "SMART PEOPLE LTI", "Sistema de seguimiento de candidatos")

    Rel(cliente, smart_people_lti, "Usa")
```

### Nivel 2: Contenedor del Sistema
```mermaid
C4Container
    title Contenedores del Sistema SMART PEOPLE LTI

    Container(cliente, "Cliente", "Navegador Web", "Usuario del sistema de ATS")
    Container(smart_people_lti, "SMART PEOPLE LTI", "Aplicación Web", "Sistema de seguimiento de candidatos")
    ContainerDb(base_datos, "Base de Datos", "RDS", "Almacena datos de candidatos y empleos")

    Rel(cliente, smart_people_lti, "Usa")
    Rel(smart_people_lti, base_datos, "Lee y Escribe")
```

### Nivel 3: Componente del Sistema
```mermaid
C4Component
    title Componentes del Sistema SMART PEOPLE LTI

    Component(cliente, "Cliente", "Navegador Web", "Usuario del sistema de ATS")
    Component(aplicacion_web, "Aplicación Web", "Django", "Maneja la lógica de negocio")
    Component(api_rest, "API REST", "Django REST Framework", "Provee servicios REST")
    Component(base_datos, "Base de Datos", "PostgreSQL", "Almacena datos de candidatos y empleos")
    Component(ia_modulo, "Módulo de IA", "TensorFlow", "Optimiza la selección de candidatos")

    Rel(cliente, aplicacion_web, "Usa")
    Rel(aplicacion_web, api_rest, "Consume")
    Rel(api_rest, base_datos, "Lee y Escribe")
    Rel(api_rest, ia_modulo, "Provee Datos")
```

### Nivel 4: Diagrama de Código para "Aplicación Web"
```mermaid
C4Component
    title Aplicación Web de SMART PEOPLE LTI

    Container_Boundary(aplicacion_web, "Aplicación Web") {
        Component(controller, "Controller", "Django Controller", "Maneja las solicitudes HTTP")
        Component(service, "Service Layer", "Servicio", "Contiene la lógica de negocio")
        Component(repository, "Repository", "Repositorio", "Accede a la base de datos")
        Component(api_rest, "API REST", "Django REST Framework", "Provee servicios REST")
    }

    Rel(controller, service, "Llama")
    Rel(service, repository, "Usa")
    Rel(service, api_rest, "Consume")
```
