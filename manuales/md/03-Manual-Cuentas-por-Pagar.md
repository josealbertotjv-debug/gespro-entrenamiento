# Manual del Usuario · Módulo 3: Cuentas por Pagar
**GesPro Administrativo v5.7.0 · Guía Práctica del Estudiante**

> **Tu misión en este módulo:** Registrar facturas de proveedores en segundos (incluso leyendo PDFs/fotos con IA), validar el comprobante previo, calcular retenciones de IVA e ISLR sin errores, controlar reintegros y enviar pagos masivos al banco respetando el control interno.  
> **🎬 Videos de repaso de este módulo (`-WhatsApp.mp4` disponibles):** `11-Proveedores` (`1:28`) · `06-Facturacion-de-proveedores` (`2:12`) · `09-Cuentas-por-pagar` (`1:31`) · `07-Pago-a-proveedores` (`1:48`).

---

## 1. Mapa del Módulo de Cuentas por Pagar

En el menú **Ciclo comercial** tienes herramientas especializadas para separar el registro de compras del pago:

| Sección del menú | Qué haces allí |
|---|---|
| **Proveedores** | Fichas fiscales, porcentajes de retención IVA, concepto ISLR (Decreto 1.808), datos bancarios obligatorios y alerta **«Sin datos para pagarles»**. |
| **Facturación de proveedores** | Solo cargar y asentar facturas/notas de proveedores (sin acceso a pagos). |
| **Cuentas por pagar** | Vista completa con 6 pestañas: **Documentos**, **Pagar facturas**, **Antigüedad de saldos**, **Pagos**, **Retenciones por reintegrar** y **Lotes al banco**. |
| **Pago a proveedores** | Centro de mando de Tesorería/Pagos: **Pagar facturas**, **Programación** (vencimientos vs dinero disponible), **Pagos realizados**, **Retenciones por reintegrar** y **Archivo al banco**. |
| **Operaciones → Importaciones** | Proyectos de importación con cuenta transitoria para acumular flete, seguro, aduana y facturas antes de cerrar o costear. |

---

## 2. Ficha del Proveedor: El Secreto para Pagar sin Tropiezos

![Listado de proveedores](../presentacion/img/proveedores-listado.png)

1. **Los 4 datos bancarios obligatorios:** Para incluir a un proveedor en un **Lote de pago al banco**, su ficha debe tener: **Banco**, **Número de cuenta**, **Titular** y **Documento**.
   - Revisa siempre la tarjeta **«Sin datos para pagarles»** en la parte superior de `Proveedores`: te muestra exactamente a quién y qué dato le falta antes del día de pago.
   - Si al proveedor se le paga en efectivo (o es un organismo sin transferencia), marca **«Se le paga en efectivo»** en *Forma de pagarle* (no pedirá datos bancarios ni entrará en lotes).
2. **Condición fiscal y retenciones (⚠️ ¡Clave para ISLR!):**
   - Configura su **% de retención de IVA** (75 % o 100 %) y su **concepto de ISLR** según el tabulador del Decreto 1.808.
   - **Proveedores extranjeros:** Nunca los dejes como «Extranjero» a secas; elige **«Persona natural no residente»** o **«Persona jurídica no domiciliada»** (de lo contrario GesPro no puede aplicar la tabla correcta de ISLR ni permite retenerles).

---

## 3. Registrar una Factura de Proveedor (2 Caminos: IA o Manual)

![Listado de cuentas por pagar](../presentacion/img/cxp-listado.png)

### Camino A · 🚀 Importar factura con IA (el más rápido)
1. En **Cuentas por pagar** (o **Facturación de proveedores**), pulsa **«Importar factura con IA»**.
2. Si conoces la moneda de la factura (o si pertenece a una **Importación**), indícalo. Adjunta el **PDF o foto** (hasta 8 MB).
3. En segundos, la IA lee proveedor/RIF, número de factura, número de control, fecha, moneda, renglones y totales, y crea un **Borrador** con el documento original adjunto.
   - Si el RIF no existía, abre la ficha nueva prellenada para que la guardes y cree la factura sola.
   - Los renglones cuyo código coincida exactamente con tu catálogo se enlazan solos al inventario; los demás entran como gasto/servicio para que los ajustes.
4. Abre el borrador, pulsa **«Ver factura original»** para comparar lado a lado, revisa cualquier advertencia en las notas y aprueba.

### Camino B · Registro manual
1. Pulsa **«Nuevo documento»**, elige el proveedor y escribe el **número de factura** y el **número de control** exactamente como vienen en el papel del proveedor *(en CxP estos números nunca son automáticos; van al Libro de Compras)*.
2. Agrega las líneas: si compras mercancía, selecciona el **artículo** y el **almacén** de destino; si es un servicio o gasto, elige la **cuenta contable** de gasto.
3. Guarda en **Borrador**.

### El Comprobante de Pago y Retención Previo (`CPR-…`)
- Apenas guardas el borrador de la factura del proveedor, GesPro genera automáticamente el **Comprobante previo (`CPR-…`)**: desglosa base imponible, IVA, retenciones de IVA/ISLR estimadas y el **neto real a pagar**.
- Pulsa **«Copiar enlace»** y envíaselo al proveedor (página de solo lectura válida por 30 días) para que confirme los cálculos antes de pagar. Si modificas la factura, el enlace viejo caduca y nace uno nuevo.
- Al pulsar **«Aprobar / Asentar»**: entra la mercancía al almacén (recalculando el **costo promedio**), nace la deuda en CxP y se genera el asiento contable.

---

## 4. Casos Especiales que Ahorran Dolores de Cabeza

### 4.1 «Pagada por un accionista»
Cuando un socio/accionista paga de su bolsillo una factura de proveedor:
1. Registra y aprueba la factura del proveedor **como siempre** (con el gasto en su cuenta real — **NUNCA** pongas la cuenta de accionistas en el renglón de gasto).
2. Haz las retenciones primero si aplican.
3. Abre la factura aprobada y pulsa **«Pagada por un accionista»** → indica quién pagó, fecha y monto.
- **Qué hace GesPro:** Salda la factura (nadie la pagará dos veces), mueve la deuda de *Proveedores* a *Cuentas por pagar Accionistas* y **no saca dinero de ningún banco**. Cuando la empresa le devuelva el dinero al socio, se registra un movimiento de banco contra esa cuenta.

### 4.2 «Retenciones por reintegrar» (Proveedor que exige el 100 %)
Algunos proveedores cobran la factura entera sin dejar descontar la retención y devuelven el monto retenido días después:
1. Al pagarle completo desde **Pagar facturas**, la retención se declara y entera igual al SENIAT, pero lo retenido queda abierto como deuda a tu favor en la pestaña **Retenciones por reintegrar**.
2. Cuando el proveedor te devuelva ese dinero, entra a **Retenciones por reintegrar** y pulsa **«Registrar reintegro»** (o regístralo desde el abono en la conciliación bancaria).
3. Si acuerdan rebajarlo de su próxima factura, pulsa **«Descontar de otra factura»**.

---

## 5. Pagar Facturas y Emitir Comprobantes Fiscales de Retención

1. Entra a **Pago a proveedores** (o **Cuentas por pagar → Pagar facturas**) y selecciona el proveedor.
2. Verás todas sus facturas pendientes, días vencidos y retenciones calculadas automáticamente:
   - **IVA:** según % de la ficha (75 % o 100 %; lo exento se separa automáticamente en *Sin derecho a crédito*).
   - **ISLR:** según el tabulador del **Decreto 1.808**. *(Para empresas no domiciliadas en filas T-2, GesPro aplica automáticamente la **Tarifa 2 acumulativa anual**: 15 %, 22 % y 34 % restando lo ya retenido en el año).*
3. Marca las facturas a pagar (puedes pagar el saldo completo o un monto parcial, y las retenciones se prorratean).
4. Elige la cuenta bancaria (solo muestra cuentas de la misma moneda), fecha, método y referencia. Verifica el neto a transferir y pulsa **«Generar pago»**.
5. **Emitir comprobantes fiscales:** Abre el pago en la pestaña **Pagos** → pulsa **«Emitir comprobante de IVA»** y/o **«… de ISLR»** → verifica fecha de emisión y escribe la **fecha de aplicación** (obligatoria) → imprime el PDF (con logo, firma y sello configurados en `Configuración → Retenciones`) o pulsa **«Enviar por correo»** al proveedor.

---

## 6. Pagos por Lote al Banco (Segregación de Tareas)

![Lotes de pago al banco](../presentacion/img/cxp-lotes.png)

Para pagar a 10, 30 o 100 proveedores sin teclear transferencias a mano:
1. **Compras / CxP** registra y postea los pagos (rebajan la deuda de cada proveedor).
2. **Tesorería** entra a **Bancos → Pago masivo (archivo al banco)** (o **Lotes al banco**), agrupa esos pagos y elige la plantilla del banco (ancho fijo o delimitado por `;`).
3. Revisa la **Vista previa** del archivo, genera el archivo de texto (queda con huella criptográfica SHA-256) y súbelo al portal del banco.
4. Sigue el ciclo de vida: `BORRADOR → GENERADO → ENVIADO → CONFIRMADO`.
   - *Regla de control interno:* Quien registra facturas/pagos en compras **no** es quien genera y envía el archivo al banco; GesPro impone esta separación por permisos.
   - Si anulas un lote antes de enviarlo, sus pagos vuelven a estar disponibles.

---

## ⚠️ 5 Errores Clásicos en CxP (y Cómo Evitarlos)

| Error clásico | Qué pasa | Cómo hacerlo bien |
|---|---|---|
| Elegir la cuenta de «Accionistas» en el renglón de gasto de la factura | No registra el gasto y baja falsamente la deuda del socio | Carga el gasto en su cuenta real, aprueba, y luego pulsa **«Pagada por un accionista»** |
| Dejar un proveedor del exterior como «Extranjero» a secas | El sistema bloquea la retención de ISLR por ambigüedad legal | Edita su ficha y elige *Persona natural no residente* o *Persona jurídica no domiciliada* |
| Llegar al día de pago sin revisar datos bancarios | El proveedor queda fuera del lote masivo al banco | Usa la tarjeta **«Sin datos para pagarles»** en `Proveedores` al crear la ficha |
| Aprobar una factura importada con IA sin mirar el original | Puede entrar una fecha, tasa o renglón mal interpretado | Pulsa siempre **«Ver factura original»** y lee los avisos antes de aprobar |
| Intentar cambiar la fecha de emisión de un comprobante de IVA a otro mes | El mes va incrustado en el número fiscal (`AAAAMM…`) | Anula ese comprobante y emite uno nuevo en el mes correcto |

---

## 🛠️ Reto Práctico del Estudiante (25 min)

1. Ve a **Proveedores**, pulsa el indicador **«Sin datos para pagarles»** (o abre un proveedor cualquiera) y asegúrate de que tenga sus 4 datos bancarios completos.
2. Entra a **Cuentas por pagar → Nuevo documento**, registra una factura de proveedor (inventa número `FAC-P-001` y control `00-99001`) comprando **10 unidades** de un artículo del catálogo hacia el almacén principal. Guarda en borrador.
3. Abre el borrador, revisa el **Comprobante previo (`CPR-…`)** y pulsa **«Aprobar y contabilizar»**.
4. Ve a **Pagar facturas**, elige ese proveedor, marca la factura, observa las retenciones de IVA/ISLR calculadas y pulsa **«Generar pago»**.
5. Abre el pago en la pestaña **Pagos**, emite el **Comprobante de retención de IVA** (poniendo fecha de aplicación de hoy) y revisa la vista previa del PDF.

---

## 📌 Chuleta Rápida (1 minuto)
- **Ahorra tiempo:** Usa **«Importar factura con IA»** (PDF o foto) y valida contra el original.
- **Antes de aprobar:** Revisa y comparte el **Comprobante previo (`CPR-…`)**.
- **Pagó un socio:** Aprueba normal → botón **«Pagada por un accionista»**.
- **Pagó completo sin retener:** Controla la devolución en **Retenciones por reintegrar**.
- **Lotes al banco:** Compras postea el pago → Tesorería genera el archivo (`BORRADOR → GENERADO → ENVIADO → CONFIRMADO`).
