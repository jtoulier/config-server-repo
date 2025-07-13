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
