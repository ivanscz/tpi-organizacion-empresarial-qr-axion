# Diccionario de datos

PK: clave primaria. FK: clave foránea. La regla de cupones no acumulables usa el campo `categoria` de CUPON.

## CLIENTE

Persona que usa la app AXION ON y activa cupones.

| Campo | Tipo | Descripción |
|---|---|---|
| `id_cliente` | Integer | Identificador único del cliente en la app (PK). |
| `dni` | String | Documento del cliente. Es un dato personal (Ley N.º 25.326): se guarda solo aquí y no se incluye en el QR. |
| `nombre_completo` | String | Nombre y apellido del cliente. |
| `fecha_registro` | Date | Fecha en que el cliente creó su cuenta en la app. |
| `activo` | Boolean | Indica si la cuenta está habilitada para activar y canjear cupones. |

## CUPON

Beneficio o descuento definido por la casa central.

| Campo | Tipo | Descripción |
|---|---|---|
| `id_cupon` | Integer | Identificador único del cupón (PK). |
| `descripcion` | String | Texto que ve el cliente, por ejemplo «10 % en lubricantes». |
| `tipo_descuento` | String | Forma del descuento: PORCENTAJE o MONTO_FIJO. |
| `categoria` | String | Rubro al que aplica el cupón, por ejemplo COMBUSTIBLE o LUBRICANTES. Permite controlar que no se combinen dos cupones de la misma categoría. |
| `valor_descuento` | Decimal | Valor del descuento: un porcentaje o un monto en pesos, según tipo_descuento. |
| `fecha_vencimiento` | Date | Último día en que el cupón puede activarse y canjearse. |

## CODIGO_QR

QR que la app genera cuando el cliente activa un cupón.

| Campo | Tipo | Descripción |
|---|---|---|
| `token` | String | Código único e irrepetible que se codifica en el QR (PK). No contiene datos personales. |
| `id_cliente` | Integer | Cliente que activó el cupón (FK a CLIENTE). |
| `id_cupon` | Integer | Cupón activado (FK a CUPON). |
| `fecha_generacion` | DateTime | Momento en que se activó el cupón y se generó el QR. |
| `fecha_expiracion` | DateTime | Fecha y hora hasta la cual el QR es válido. |
| `usado` | Boolean | Pasa a verdadero al confirmar el canje, en una sola operación, para que dos intentos simultáneos no usen el mismo QR. |

## CANJE

Registro de cada intento de canje en el POS.

| Campo | Tipo | Descripción |
|---|---|---|
| `id_canje` | Integer | Identificador único del intento de canje (PK). |
| `token` | String | QR que se escaneó (FK a CODIGO_QR). |
| `id_estacion` | Integer | Estación de servicio donde se escaneó el QR. |
| `fecha_hora` | DateTime | Momento exacto del escaneo. |
| `resultado` | String | APROBADO, RECHAZADO_USADO, RECHAZADO_VENCIDO o PENDIENTE (sin conexión, a la espera de confirmar). |
| `modo` | String | EN_LINEA o ALTERNATIVO (procedimiento manual autorizado por la empresa cuando falla la conexión). |
| `monto_descontado` | Decimal | Importe descontado en la venta, en pesos (0 si fue rechazado o está pendiente). |
