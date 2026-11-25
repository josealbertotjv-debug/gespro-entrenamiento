# Manual del Usuario · Módulo 2: Cuentas por Cobrar
**GesPro Administrativo v5.7.0 · Guía Práctica del Estudiante**

> **Tu misión en este módulo:** Facturar sin errores de numeración fiscal, controlar el crédito y los bloqueos por mora, cobrar en bolívares o divisas (con IGTF y retenciones de IVA/ISLR) y usar la cartera para cobrar más rápido.  
> **🎬 Videos de repaso de este módulo (`-WhatsApp.mp4` disponibles):** `10-Clientes` (`1:46`) · `05-Facturacion-de-clientes` (`2:04`) · `08-Cuentas-por-cobrar` (`1:58`) · `14-Comprobantes-de-pago` (`1:28`) · `12-Autorizaciones` (`1:13`).

---

## 1. Mapa del Módulo de Cuentas por Cobrar

Encontrarás estas secciones y pestañas clave:
- **Menú `Clientes`:** Directorio con ficha fiscal, crédito, vendedor asignado y detección de *Fichas incompletas*.
- **Menú `Facturación de clientes`:** Solo emitir, aprobar, imprimir y anular facturas/notas (ideal para facturadores que no tocan cobranza).
- **Menú `Cuentas por cobrar`** (6 pestañas):
  1. **Documentos** *(incluye las tarjetas «Pedidos por facturar» y «Pedidos vencidos sin facturar»)*
  2. **Panel de clientes** *(ranking de mejores clientes y qué productos compra cada uno)*
  3. **Reporte por cliente** *(días promedio reales de pago vs días de crédito y % pagado)*
  4. **Antigüedad de saldos** *(a quién llamar primero por tramos: corriente, 1-30, 31-60, 61-90, +90)*
  5. **Cobros** *(historial de cobros, anticipos y anulaciones)*
  6. **Retenciones recibidas** *(comprobantes de retención IVA/ISLR que entregan clientes contribuyentes especiales)*
- **Menú `Comprobantes de pago` y `Portal de clientes (/portal)`:** Bandeja donde llegan los pagos que reportan tus clientes escaneando el QR de su factura.
- **Menú `Autorizaciones`:** Bandeja del gerente para aprobar o rechazar facturas detenidas por morosidad.

---

## 2. Ficha del Cliente: Qué Llenar Bien desde el Día 1

![Listado de clientes](../presentacion/img/clientes-listado.png)

Al crear un cliente en **Clientes → Nuevo cliente**:
1. **Escribe primero el RIF/Identificación:** GesPro deduce automáticamente la **Condición fiscal** por el prefijo (`V/P` persona natural, `J/C` persona jurídica, `G` ente público, `E` extranjero residente). Si tienen el puente SENIAT o el botón **«Leer el RIF (PDF o foto)»**, rellena datos y dirección fiscal automáticamente.
2. **Vendedor (obligatorio):** Define qué vendedor sale impreso en la factura y quién cobra la comisión.
3. **Días de crédito y Límite de crédito:** Calcula automáticamente la fecha de vencimiento de cada factura.
4. **Bloqueo por facturas vencidas (⚠️ ¡Cuidado con el cero!):**
   - Escribir **`0`** significa **SIN TOPE** (nunca se bloquea).
   - Escribir **`1`** significa que con **1 factura vencida** ya no se puede aprobar una factura nueva sin permiso del gerente en **Autorizaciones**.
   - *Cada autorización vale para UNA sola factura.* Las notas de crédito nunca se bloquean porque bajan la deuda.
5. **Si el cliente también es proveedor:** Usa **una sola ficha** marcando tipo **«Cliente y proveedor»** para no duplicarlo.

---

## 3. Emitir y Aprobar una Factura (Paso a paso)

![Editor de factura de venta](../presentacion/img/cxc-factura.png)

### Opción A: Desde un Pedido (cotización aceptada o vendedor)
1. En **Cuentas por cobrar** (o **Facturación de clientes**), mira arriba la tarjeta **«Pedidos por facturar»**.
2. Pulsa **«Crear factura»**. Si era un cliente nuevo propuesto por el vendedor, revisa y confirma sus datos. Se crea el **Borrador** con los mismos renglones y precios del pedido.

### Opción B: Factura manual desde cero
1. Pulsa **«Nuevo documento»** y elige el cliente.
2. Agrega los artículos o servicios. El impuesto (IVA 16 %, 8 % o Exento) viene de la ficha del artículo.
3. **Control de precios:** Si cambias un precio respecto al de lista, el renglón te avisa debajo. Al pulsar **Guardar**, aparece una ventana de **repaso completo** señalando con `⚠` cualquier precio alterado antes de guardar.
4. **Equivalente en divisa:** Si facturas en bolívares y debes mostrar el equivalente en USD (Art. 25 Ley IVA), marca **«Equivalente en divisa»** y verifica la tasa BCV propuesta. Esa tasa queda **guardada para siempre** en esa factura (al reimprimirla meses después, no cambia).
5. **BORRADOR vs APROBADO (¡Regla vital!):**
   - Mientras es **BORRADOR** lleva número provisional (`BORRADOR-12`), **no gasta correlativo fiscal**, no descuenta inventario ni contabiliza. Puedes editarlo o eliminarlo libremente.
   - Al pulsar **«Aprobar y contabilizar»**, en ese instante: se asigna el **número de factura y número de control consecutivos**, se descuenta el inventario, se registra el costo de ventas y se crea el asiento cuadrado.
6. **Enviar por correo / Imprimir:** Desde la factura aprobada, pulsa **«Imprimir»** (sale con tu formato o sobre talonario preimpreso y con el **QR del Portal de Clientes** al pie mientras tenga saldo) o **«Enviar por correo»**.

> **¿Aprobaste una factura por error y NO la imprimiste?** Si es la **última de la serie**, no se envió por correo, no tiene cobros, despachos ni notas asociadas, un administrador puede abrirla y usar **«Eliminar (no impresa)»** para liberar el número. En cualquier otro caso, se usa **«Anular»** (genera asiento reverso y conserva el número anulado en el Libro de Ventas).

---

## 4. Notas de Crédito y Notas de Débito

- **Nota de crédito:** Devuelve mercancía o rebaja deuda del cliente. Siempre indica **«Factura que afecta»** (si la factura original era de tu sistema anterior, elige *«Emitida en otro sistema»* para no duplicar ventas).
- **Cruzar Nota de crédito con Factura:** Abre la nota de crédito aprobada y pulsa **«Cruzar con una factura»** para rebajar directamente el saldo de la factura sin pasar por cobros. *(Solo mismo cliente y misma moneda).*
- **Nota de débito:** Aumenta la deuda del cliente (intereses, recargos, ajustes).

---

## 5. Registrar Cobros, IGTF y Retenciones Recibidas

![Registro de cobro](../presentacion/img/cxc-cobro.png)

### 5.1 Cobro directo (con o sin IGTF)
1. Abre la factura y pulsa **«Registrar cobro»** (o ve a la pestaña **Cobros**).
2. Elige la **cuenta bancaria** donde entró el dinero, la fecha, el método y **copia la referencia bancaria exacta** *(clave para que el banco concilie solo después)*.
3. **Si la cuenta es en divisas y tu empresa es contribuyente especial:** GesPro calcula automáticamente el **3 % de IGTF** encima de lo aplicado a facturas (ej. para saldar una factura de $100, el cliente paga $103: $100 cancelan la factura y $3 van a *IGTF percibido por enterar*).
4. Reparte el monto entre una o varias facturas. Si el cliente pagó de más, elige si el sobrante queda como **Anticipo del cliente** o (si eres Tesorería/Contabilidad/Admin) como **Diferencial cambiario**.
5. **¿Te equivocaste en un cobro?** Un cobro no se edita: ábrelo y usa **«Anular y registrar de nuevo»** (te precarga todos los datos para corregir solo el error; no aplica si ya está conciliado con el banco).

### 5.2 Retenciones recibidas de clientes (Contribuyentes Especiales)
Cuando un cliente especial te retiene el **75 % o 100 % del IVA** (o ISLR):
1. Registra primero en **Cobros** únicamente el dinero neto que entró al banco. La factura quedará debiendo justo lo retenido.
2. Cuando llegue el comprobante del cliente, ve a **Cuentas por cobrar → Retenciones recibidas → «Registrar retención recibida»**.
3. Elige cliente, tipo (**IVA** o **ISLR**), número de comprobante (14 dígitos en IVA: `AAAAMM + secuencia`) y fecha.
4. Marca las facturas afectadas (GesPro propone el monto en bolívares según la ficha; ajústalo si el papel dice otra cifra), adjunta el PDF/foto y pulsa **«Registrar»**.
5. **Resultado automático:** La factura baja su saldo sin tocar bancos, se contabiliza tu crédito fiscal y el número sale directo en el **Libro de Ventas**.

---

## 6. Portal de Clientes y Bandeja de Comprobantes de Pago

![Bandeja de comprobantes de pago](../presentacion/img/comprobantes.png)

- Tus clientes entran a `/portal` (o escanean el **QR al pie de su factura**) solo con su **RIF/Cédula**, sin contraseñas. Allí ven sus facturas pendientes, tus cuentas bancarias y suben su comprobante de pago (y opcionalmente su comprobante de retención).
- Los reportes caen en **Tesorería → Comprobantes de pago** recorriendo estos estados:
  `RECIBIDO → EN REVISIÓN → VERIFICADO → APLICADO` *(o `RECHAZADO` con motivo visible para el cliente)*.
- **Ayudas automáticas:** Detecta referencias duplicadas, busca el abono en el extracto bancario con índice de confianza (y con Banco Mercantil verifica pagos móviles directo con el banco) y sugiere contra qué facturas imputarlo.
- **⚠️ Regla sagrada:** *Un comprobante es lo que el cliente dice, no lo que ocurrió.* **Nunca lo apliques** sin confirmar que el dinero entró al banco. Si lo aplicaste mal, usa **«Deshacer la aplicación»** para devolverlo a *Verificado*.

---

## 7. Inteligencia de Cobranza: Antigüedad, Panel y Reporte por Cliente

![Antigüedad de saldos](../presentacion/img/cxc-antiguedad.png)

| Herramienta en CxC | Pregunta que te responde al instante |
|---|---|
| **Antigüedad de saldos** | *¿A quién llamo primero hoy?* Clasifica cada deuda en Corriente, 1-30, 31-60, 61-90 y +90 días de mora. |
| **Panel de clientes** | *¿Quiénes son mis mejores clientes y qué producto compran?* Además, te **advierte en alerta si pocos clientes concentran más del 70 %** de tu facturación (riesgo comercial). |
| **Reporte por cliente** | *¿Quién me pide 30 días pero me paga a los 65?* Muestra **Días promedio reales de pago** (ponderado por monto), **% pagado** de lo facturado y el **producto principal** de cada cliente. Haz clic en cualquier columna para ordenar y exportar a Excel. |

---

## ⚠️ 5 Errores Clásicos en CxC (y Cómo Evitarlos)

| Error clásico | Qué pasa | Solución correcta |
|---|---|---|
| Poner `0` en «Bloqueo por facturas vencidas» pensando que bloquea con cero mora | `0` significa **SIN TOPE** (le venderá aunque deba 20 facturas) | Escribe **`1`** para frenar desde la primera factura vencida |
| Inventar o recortar la referencia al registrar un cobro | La conciliación bancaria no lo cruza sola y toca hacerlo a mano | Copia la **referencia completa exacta** de la transferencia/pago móvil |
| Registrar el monto total de la factura en el banco aunque el cliente retuvo IVA | El banco queda inflado y nunca concilia | Registra en **Cobros** solo lo que entró al banco, y lo retenido en **Retenciones recibidas** |
| Aplicar un comprobante del portal solo viendo la foto de WhatsApp | Si el pago rebotó o era falso, ya saldaste la deuda | Verifica primero en el extracto o banca en línea antes de pulsar **Aplicar** |
| Cobrar en dólares sin revisar el IGTF | Diferencias de 3 % en caja y sanciones fiscales | Verifica que la cuenta en divisas tenga marcado **«sujeta a IGTF»** y confirma el cálculo automático |

---

## 🛠️ Reto Práctico del Estudiante (25 min)

1. Abre **Cuentas por cobrar** → tarjeta **«Pedidos por facturar»** → crea la factura de tu pedido del Módulo 1 (`PED-…`), revisa el repaso de precios y pulsa **«Aprobar y contabilizar»**.
2. Pulsa **«Imprimir»** para ver la factura con su número fiscal, número de control y código **QR del Portal de Clientes**.
3. Pulsa **«Registrar cobro»** por el **50 %** de la factura en una cuenta bancaria (anota tu referencia exacta, ej. `COB-EQ1-101`). Si usas cuenta en USD y la empresa es contribuyente especial, observa cómo aparece el **3 % de IGTF**.
4. Ve a **Retenciones recibidas → Registrar retención recibida**, carga un comprobante de IVA de 14 dígitos (`20261100000015`) por el 75 % del IVA de esa factura y comprueba el nuevo saldo.
5. Entra a **Antigüedad de saldos** y **Reporte por cliente** y responde: *¿cuál cliente tiene más días promedio de pago?*

---

## 📌 Chuleta Rápida (1 minuto)
- **Borrador** = editable, sin número fiscal. **Aprobar** = número + control + inventario + asiento contable.
- **Bloqueo mora:** `0` = sin límite; `1` = bloquea con 1 vencida (destraba Gerencia en **Autorizaciones**).
- **Retenciones de clientes:** Cobro por el neto + comprobante de 14 dígitos en **Retenciones recibidas**.
- **Cobro equivocado:** No se edita → **«Anular y registrar de nuevo»**.
