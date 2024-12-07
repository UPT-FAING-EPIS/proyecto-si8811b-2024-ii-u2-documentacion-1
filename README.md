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

```mermaid
graph TD
    A[Estudiante accede a app móvil] -->B[Selecciona inasistencia a justificar]
    B -->C[Completa formulario digital]
    C -->D[Adjunta evidencias digitales]
    D -->E[Sistema valida información]
    E -->F{¿Información completa?}
    F -->|No| C
    F -->|Sí| G[Sistema registra solicitud]
    G -->H[Notifica automáticamente al docente]
    H -->I[Docente revisa en plataforma]
    I -->J{¿Aprobada?}
    J -->|No| K[Sistema notifica rechazo]
    J -->|Sí| L[Sistema actualiza registro]
    L -->M[Genera registro digital]
```

```mermaid
graph TD
    A[Core] --> B[Autenticación]
    A --> C[Gestión de Asistencias]
    A --> D[Justificaciones]
    A --> E[Notificaciones]
    A --> F[Reportes]
```

### Diagrama con objetos

```mermaid
stateDiagram-v2
    [*] --> Autenticación
    Autenticación --> ValidaciónCredenciales
    ValidaciónCredenciales --> Dashboard: éxito
    ValidaciónCredenciales --> Autenticación: fallo
    Dashboard --> GestiónJustificaciones
    GestiónJustificaciones --> EnvíoJustificación
    EnvíoJustificación --> ValidaciónDatos
    ValidaciónDatos --> NotificaciónDocente: éxito
    ValidaciónDatos --> GestiónJustificaciones: fallo
```

### Diagrama de Secuencia
```mermaid
sequenceDiagram
    participant E as Estudiante
    participant UI as Interface
    participant S as Sistema
    participant BD as BaseDatos
    participant D as Docente
    
    E->>UI: Inicia justificación
    UI->>S: Solicita formulario
    S->>BD: Consulta datos
    BD-->>S: Retorna datos
    S-->>UI: Muestra formulario
    E->>UI: Completa datos
    UI->>S: Valida datos
    S->>BD: Guarda justificación
    S->>D: Notifica nueva justificación
```

### Diagrama de clases
```mermaid
classDiagram
    class Usuario {
        +id: Integer
        +nombre: String
        +tipo: TipoUsuario
        +autenticar()
        +actualizarPerfil()
    }
    
    class Justificacion {
        +id: Integer
        +fecha: Date
        +estado: Estado
        +evidencias: List<Archivo>
        +enviar()
        +evaluar()
    }
    
    class Asistencia {
        +id: Integer
        +fecha: Date
        +estado: EstadoAsistencia
        +registrar()
        +actualizar()
    }
    
    Usuario "1" -- "*" Justificacion
    Usuario "1" -- "*" Asistencia
```
