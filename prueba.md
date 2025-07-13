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

```mermaid
%%{init: {
  "theme": "default",
  "themeCSS": "
    .actor:nth-of-type(1) rect { fill: #ffe0b2; stroke: #ef6c00; }
    .actor:nth-of-type(2) rect { fill: #c8e6c9; stroke: #388e3c; }
    .actor:nth-of-type(3) rect { fill: #bbdefb; stroke: #1565c0; }
    .actor:nth-of-type(4) rect { fill: #f8bbd0; stroke: #ad1457; }
  "
}}%%
sequenceDiagram
participant Cliente
participant API Validación
participant Motor Crédito
participant Sistema

Cliente->>API Validación: Envía solicitud
API Validación-->>Cliente: Datos validados

alt Datos incompletos
    API Validación-->>Cliente: Error: falta información
    deactivate API Validación
else Datos completos
    API Validación->>Motor Crédito: Consulta estado financiero
    loop Verificar múltiples cuentas
        Motor Crédito->>Motor Crédito: Analiza cuenta[n]
    end
    alt Crédito aprobado
        Motor Crédito-->>Sistema: Enviar respuesta positiva
        Sistema-->>Cliente: ¡Crédito aprobado!
    else Crédito rechazado
        Motor Crédito-->>Sistema: Enviar respuesta negativa
        Sistema-->>Cliente: Lo sentimos, no aprobado
    end
end
