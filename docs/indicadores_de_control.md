# Indicadores de control y estándares de desempeño

El control compara los resultados con las metas de la Entrega 2 (M1 a M5) y corrige los desvíos. El avance se revisa **una vez por semana** con el tablero y el Gantt actualizado.

| Indicador y cómo se calcula | Estándar | Fuente y responsable | Acción si se desvía |
|---|---|---|---|
| **I1. Tiempo de canje con QR (M1)**<br>Segundos desde el escaneo hasta la confirmación del descuento. | 5 segundos o menos en al menos 9 de cada 10 canjes de prueba. | Mediciones en las pruebas P1 y P2 y en el piloto. Responsable: QA / Tester. | Revisar la consulta al servidor y la lectura del QR antes de pasar a la siguiente etapa. |
| **I2. Reducción del tiempo de atención (M2)**<br>Tiempo promedio con QR comparado con el circuito actual. | Reducción de al menos 30 % frente a la línea base medida en A1. | Muestras comparables antes y después. Responsable: Analista funcional y QA. | Repetir la medición con condiciones comparables; si persiste, simplificar el flujo en el POS. |
| **I3. Errores de carga manual (M3)**<br>Canjes con error de transcripción o de DNI sobre el total de canjes. | 0 códigos escritos a mano en 20 canjes de prueba. | Observación en la prueba de aceptación y reclamos que informe Finanzas. Responsable: Referente de estación. | Corregir la pantalla del POS y reforzar la capacitación. |
| **I4. Rechazo de cupones ya usados (M3)**<br>Intentos con un QR usado que el sistema rechaza. | 5 de 5 intentos con un QR ya usado rechazados (resultado RECHAZADO_USADO). | Tabla CANJE (campo resultado) y pruebas P1. Responsable: QA / Tester. | Detener el despliegue y corregir la validación en el servidor. |
| **I5. Canjes sin conexión**<br>Canjes PENDIENTE o ALTERNATIVO sobre el total de canjes. | 5 % o menos (valor propuesto, a ajustar con los datos del piloto). | Tabla CANJE (campos resultado y modo). Responsable: Líder técnico. | Revisar la conectividad de la estación y el procedimiento alternativo con la empresa. |
| **I6. Cumplimiento del plazo y la capacitación (M5)**<br>Semanas de desvío en las tareas críticas y porcentaje de playeros capacitados. | 0 semanas de desvío en la ruta crítica y 100 % de playeros capacitados antes de P3. | Revisión semanal del tablero y el Gantt; lista de asistencia a I1. Responsable: Líder técnico. | Reorganizar las tareas en paralelo o ajustar el plazo con el Gerente de Sistemas. |

Los valores son estándares propuestos para este trabajo académico; deben ajustarse con los datos reales del piloto.
