# Título Principal

Este es un párrafo introductorio que describe el propósito del documento. Aquí se puede incluir información general sobre el tema tratado.

## Subtítulo 1: Introducción

En esta sección se presenta una **descripción general** del tema. También se puede incluir *información contextual* para ayudar al lector a comprender mejor el contenido.

## Subtítulo 2: Características

A continuación se enumeran algunas características importantes:

- **Claridad** en la presentación
- *Organización* del contenido
- Uso de **negritas** y *cursivas*
- Inclusión de listas y numeraciones

## Subtítulo 3: Pasos para la implementación

1. Definir el objetivo del documento
2. Estructurar el contenido con títulos y subtítulos
3. Agregar párrafos explicativos
4. Utilizar **formato enriquecido** como *negritas* e *italicas*
5. Incluir listas con viñetas y numeraciones

## Subtítulo 4: Conclusión

Este documento demuestra cómo estructurar un archivo Markdown con múltiples elementos de formato. El uso adecuado de estos elementos mejora la legibilidad y comprensión del contenido.

| Categoría       | Subcategoría       | Detalles                                                                 |
|-----------------|--------------------|--------------------------------------------------------------------------|
| **Tecnología**  | Hardware            | - CPU: Intel i9<br>- RAM: 32GB<br>- SSD: 1TB                             |
|                 | Software            | - SO: Linux<br>- IDE: VS Code<br>- Lenguaje: Python                     |
| **Educación**   | Primaria            | - Grado 1<br>- Grado 2<br>- Grado 3                                      |
|                 | Secundaria          | - Ciencias:<br>  - Física<br>  - Química<br>- Matemáticas                |
| **Proyectos**   | Desarrollo Web      | - Frontend:<br>  - HTML<br>  - CSS<br>  - JS<br>- Backend:<br>  - NodeJS |
|                 | Ciencia de Datos    | - Librerías:<br>  - Pandas<br>  - NumPy<br>  - Scikit-learn              |


```mermaid
sequenceDiagram
    actor Cliente
    participant Servidor
    participant BD

    %% Estilos personalizados para los actores
    actor Cliente as Cliente
    participant Servidor as Servidor
    participant BD as Base de Datos

    %% Comentario
    Note over Cliente,Servidor: Inicio de la solicitud

    Cliente->>Servidor: Solicita datos
    alt Datos en caché
        Servidor-->>Cliente: Retorna datos desde caché
    else Datos no disponibles
        Servidor->>BD: Consulta datos
        BD-->>Servidor: Retorna datos
        Servidor-->>Cliente: Retorna datos consultados
    end

    opt Validación adicional
        Cliente->>Servidor: Enviar token de validación
        Servidor-->>Cliente: Confirmación
    end

    loop Reintentos
        Cliente->>Servidor: Reintento de solicitud
    end

    par Procesamiento paralelo
        Servidor->>BD: Guardar log
        Servidor->>Cliente: Confirmación de recepción
    and
        Servidor->>BD: Actualizar estadísticas
    end

    Note right of Cliente: Fin del proceso
