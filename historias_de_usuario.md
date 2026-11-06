# Historias de usuario

Estados del tablero: **Por Hacer**, **En Progreso** y **Listo**. Las tareas (A, D, C, P, I) son las del Gantt de la Entrega 2.

## HU-1 - Canje por lectura de QR

> Como **playero**, quiero **escanear el código QR del cupón que muestra el cliente con el lector del POS**, para **aplicar el descuento sin pedir el DNI ni transcribir ningún código**.

**Criterios de aceptación**

- Al escanear un QR válido, el descuento se aplica en la venta en 5 segundos o menos (meta M1).
- El playero no escribe ningún código a mano (meta M3).
- Si el cupón está vencido o ya fue usado, el sistema lo rechaza y muestra el motivo.
- Dos cupones de la misma categoría no se combinan en una misma venta; sí se pueden canjear cupones de categorías distintas (por ejemplo, lubricantes y combustible).

**Tareas del Gantt:** A2, D2, C1, C2, C3, P1  
**Estado:** Listo  
**Nota:** Especificada y modelada (BPMN, diccionario de datos y criterios de aceptación). La programación sigue el Gantt de la Entrega 2.

## HU-2 - Falla de conexión y lectura

> Como **playero**, quiero **que el sistema me avise cuando no hay conexión con el servidor y me indique cómo continuar**, para **no confirmar un canje que no pudo verificarse y no demorar la atención al cliente**.

**Criterios de aceptación**

- Sin conexión, el sistema no confirma el canje automáticamente e informa la falla al playero.
- Si existe un procedimiento alternativo autorizado por la empresa, se aplica de forma manual y el canje se registra con modo ALTERNATIVO; si no existe, el canje queda PENDIENTE hasta recuperar la conexión.
- Si el QR no se puede leer, el playero puede volver a escanearlo.

**Tareas del Gantt:** D3, C4, P1, P3  
**Estado:** En Progreso  
**Nota:** Falta definir con la empresa cuál es el procedimiento alternativo autorizado (amenaza ya identificada en el FODA de la Entrega 2).

## HU-3 - Registro y trazabilidad de canjes

> Como **responsable de Finanzas y Control**, quiero **que cada intento de canje quede registrado con su resultado, la estación y la hora**, para **conciliar la caja y auditar los descuentos aplicados**.

**Criterios de aceptación**

- Se registran los canjes aprobados, rechazados y pendientes (entidad CANJE del diccionario de datos).
- Cada registro indica estación, fecha y hora, resultado, modo (EN_LINEA o ALTERNATIVO) y monto descontado.
- Un mismo QR no figura con más de un canje aprobado.

**Tareas del Gantt:** D2, C1, P1, P2  
**Estado:** Por Hacer  
**Nota:** Los datos ya están definidos; falta diseñar el reporte de conciliación para Finanzas.
