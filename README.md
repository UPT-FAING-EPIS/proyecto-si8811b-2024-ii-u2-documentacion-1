[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=17169109)
#  Proyecto “Sistema Web y Móvil para la Gestión y Justificación de Inasistencias de la Universidad Privada de Tacna”

## Integrantes
- Cesar Fabian Chavez Linares


```mermaid
graph TD
    A[Sistema de Autenticación] --> B[Gestión Básica de Asistencias]
    B --> C[Sistema de Justificaciones]
    C --> D[Sistema de Notificaciones]
    C --> E[Reportes y Estadísticas]
    E --> F[Funcionalidades Avanzadas]
```



```mermaid
graph TD
    A[Estudiante detecta necesidad de justificar inasistencia] -->B[Reúne documentación física]
    B -->C[Acude a oficina académica]
    C -->D[Presenta solicitud y documentos]
    D -->E[Personal revisa documentación]
    E -->F{¿Documentación completa?}
    F -->|No| B
    F -->|Sí| G[Registra solicitud]
    G -->H[Envía a docente para revisión]
    H -->I[Docente evalúa justificación]
    I -->J{¿Aprobada?}
    J -->|No| K[Notifica rechazo]
    J -->|Sí| L[Registra justificación]
    L -->M[Archiva documentación]

```
