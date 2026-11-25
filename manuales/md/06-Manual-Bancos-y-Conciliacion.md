# Manual del Usuario · Módulo 6: Bancos y Conciliación
**GesPro Administrativo v5.7.0 · Guía Práctica del Estudiante**

> **Tu misión en este módulo:** Controlar el saldo real de tus bancos y cajas en cada moneda, vigilar la pérdida por devaluación en bolívares, conciliar cualquier estado de cuenta en minutos hasta dejar la diferencia en **0,00** y activar el Agente de conciliación para que trabaje por ti todos los días.  
> **🎬 Videos de repaso de este módulo:** `13-Bancos-y-conciliacion` (`1:45`, resumen general, también en `-WhatsApp.mp4`) + `video/gespro-conciliacion.mp4` (`5:50`, los 7 pasos en detalle + Agente).

---

## 1. Mapa del Módulo de Bancos (5 Pestañas)

En **Tesorería → Bancos y conciliación** tienes todo el control del dinero:

| Pestaña | Qué haces allí |
|---|---|
| **Cuentas y saldos** | Lista de cuentas bancarias y cajas (corriente, ahorro, caja), moneda, consolidado a moneda base, contador **Sin conciliar** y columna **Devaluación** (en multimoneda). |
| **Libro bancario** | Todos los ingresos y egresos registrados por el ERP (cobros, pagos, nóminas, movimientos manuales) con filtros por fecha y estado de conciliación. |
| **Extracto del banco** | Carga automática del estado de cuenta real descargado del banco (Excel, CSV o TXT con o sin encabezados). |
| **Conciliación** | Tablero cara a cara (Libro a la izquierda, Extracto a la derecha) con cruce automático, cruce manual, notas del banco, devoluciones y cierre auditado. |
| **Pago masivo (archivo al banco)** | Armado y generación de archivos TXT/CSV de pago por lote a proveedores y nómina (`BORRADOR → GENERADO → ENVIADO → CONFIRMADO`). |

---

## 2. Cuentas, Devaluación y Reglas del Saldo Inicial

![Cuentas bancarias y movimientos](../presentacion/img/01-cuentas.png)

### Al crear una cuenta bancaria (`Nueva cuenta`)
- Escribe el **número de cuenta exactamente** como aparece en el estado de cuenta de tu banco (GesPro lo usa para impedir que importes por error el extracto de otra cuenta).
- Asocia su **moneda** (una vez tenga movimientos, la moneda queda fija), su **cuenta contable** (`11…`), su **plantilla de pago** (si harás lotes masivos) y marca **«sujeta a IGTF»** si corresponde.
- **Columna «Devaluación» (oro puro para gerencia):** Si operas en bolívares y dólares, GesPro muestra automáticamente cuánto perdió de valor cada saldo quieto en bolívares desde la última tasa BCV, tanto en **%** como en **dinero real**. *(Es un dato gerencial para decidir compra de divisas o pagos; no genera asiento contable).*

### ¿Se puede corregir el Saldo Inicial de una cuenta?
Depende del estado de la cuenta (en `Cuentas y saldos → Editar`):
- **Sin movimientos:** Sí, se corrige sin restricción.
- **Con movimientos sin conciliar:** Sí, con aviso (desplaza el saldo histórico en todas las fechas).
- **Con movimientos YA conciliados:** **BLOQUEADO.** Nunca se altera el saldo inicial bajo una conciliación ya firmada. Para ajustar una diferencia, usa el botón superior **«Movimiento manual»** (crea un movimiento con fecha, concepto y asiento auditable).

---

## 3. Conciliación Bancaria en 7 Pasos Exactos

> **🎬 Video de apoyo para repasar en casa:** `video/gespro-conciliacion.mp4` (5 min 50 s) recorre exactamente estos 7 pasos + el Agente automático.

![Panel de conciliación bancaria](../presentacion/img/07-panel-inicial.png)

### Paso 1 · Revisar la cuenta y el libro
1. En **Cuentas y saldos**, ubica la cuenta con movimientos en la columna **«Sin conciliar»**.
2. Revisa en **Libro bancario** que ya hayas registrado los cobros y pagos del período antes de empezar.

### Paso 2 · Importar el extracto del banco
1. Ve a **Extracto del banco → «Importar extracto»**.
2. Selecciona la cuenta y sube tu archivo (**Excel, CSV o TXT** tal como lo baja tu banco — incluso texto posicional sin encabezados como Banco Mercantil, con separador `;`, `,` o tabulador, o pegando el texto).
3. **3 Validaciones automáticas antes de guardar:**
   - Confirma que la **moneda** coincida con la cuenta.
   - Confirma que el **número de cuenta** del archivo sea el de la cuenta elegida (si te equivocaste, te dice cuál parece ser la correcta).
   - Comprueba la matemática del extracto: `Saldo inicial (SI) + Créditos − Débitos = Saldo final (SF)`.
   - *Tranquilidad total:* Las líneas `SI` y `SF` no se cargan como movimientos (se usan para prellenar el saldo final) y **reimportar el mismo archivo nunca duplica líneas**.

### Paso 3 · Abrir la conciliación
1. Pulsa el botón directo desde el resumen de importación, o ve a **Conciliación → «Nueva conciliación»**.
2. Selecciona la cuenta, la **fecha de corte** (ej. último día del mes) y escribe el **saldo final exacto según el banco**.
3. Pulsa **«Abrir conciliación»**. Se abre el tablero con la fórmula arriba:
   $$\text{Saldo según banco} + \text{Depósitos en tránsito} - \text{Cheques pendientes} = \text{Saldo según libros}$$
   Y abajo dos columnas frente a frente: **tu Libro a la izquierda** y **el Extracto del banco a la derecha**.

### Paso 4 · Ejecutar el «Cruce automático»
![Cruce automático](../presentacion/img/08-cruce-auto.png)
- Pulsa **«Cruce automático»** en la cabecera.
- En segundos, GesPro empareja todas las partidas que coinciden por **importe exacto, tipo (ingreso/egreso), tolerancia de fecha y similitud de referencia**. Normalmente resuelve el 80–95 % del mes en un clic y te deja a la vista solo las excepciones.

### Paso 5 · Emparejar a mano las excepciones
- Si un cobro o pago entró en el banco varios días después o con otra referencia, haz clic en la fila de la **izquierda (Libro)**, haz clic en su pareja de la **derecha (Extracto)** y pulsa **«Conciliar las dos partidas seleccionadas»**.
- *¿Te equivocaste?* Mientras la conciliación siga abierta, baja a la lista de conciliados y pulsa **«Deshacer»**.

### Paso 6 · Registrar comisiones y notas del banco (sin salir de aquí)
![Registrar nota del banco](../presentacion/img/10-registrar-nota.png)
- Cuando el banco cobró mantenimiento, comisión por transferencia, IGTF bancario o abonó intereses que aún no estaban en tu libro:
  1. Pulsa **«Registrar»** junto a esa línea del extracto.
  2. Elige la cuenta contable de contrapartida (ej. *Comisiones y gastos bancarios*).
  3. Pulsa **«Registrar y conciliar»**. GesPro crea el movimiento en el libro, **genera el asiento contable cuadrado** y lo concilia al instante.

### Paso 7 · Transferencias devueltas y Cierre en 0,00
![Conciliación cuadrada](../presentacion/img/12-cuadrada.png)

#### ¿Qué hago si el banco devolvió una transferencia?
A veces pagas a un proveedor, el banco rechaza/devuelve el dinero por el mismo monto y luego haces una segunda transferencia exitosa:
1. **NO anules el pago.** Abre el pago en `CxP → Pagos` (o el cobro en `CxC → Cobros`) y pulsa **«Corregir referencia»**: pon la referencia de la segunda transferencia (la buena) y el motivo. Así cruza automáticamente con el débito bueno.
2. En la conciliación te quedarán sueltas en el extracto la primera transferencia rechazada y su devolución (mismo monto, signos contrarios).
3. Selecciona una de ellas, pulsa **«Compensar con su devolución»**, confirma su pareja y escribe el motivo. **Se concilian entre sí SIN crear asientos contables ficticios.** *(Si el banco cobró comisión por el rechazo, regístrala aparte con el Paso 6).*

#### Cerrar con diferencia 0,00
- Cuando todo el extracto está conciliado y las únicas partidas restantes en tu libro son reales **en tránsito** (ej. un cheque emitido el día 30 que aún no han cobrado), el indicador de diferencia se pone en **verde (`0,00`)** y se habilita **«Cerrar conciliación»**.
- Al cerrar, la conciliación pasa al **Histórico** en estado **Cerrada** y **bloquea todas sus partidas y el saldo inicial** para que nadie pueda alterar un mes ya auditado. *(Si aparece algo después, se registra en el mes siguiente).*

---

## 4. El Agente de Conciliación Bancaria (Tu Asistente Diario)

![Agente de conciliación](../presentacion/img/14-agente-conciliacion.png)

No esperes al día 30 del mes para conciliar. En **Configuración → Agentes → Conciliación bancaria**:
1. Enciéndelo y configura tus horarios (ej. `8:00 a. m.` y `4:00 p. m.`) y las cuentas a vigilar.
2. **Qué hace solo por ti:**
   - Recuerda por correo y **GP Mensajes** a quien descarga los estados de cuenta si falta cargar el extracto del día.
   - Apenas alguien sube un extracto, ejecuta el **cruce automático** solo.
   - Envía un **informe separado por área** con lo que no cruzó: ingresos sin registrar → a **CxC**; egresos sin registrar → a **CxP**; comisiones/IGTF/intereses → a **Bancos** (¡incluso avisa si un monto coincide exactamente con una factura abierta!).
3. **Regla de seguridad:** El agente **prepara, cruza y avisa, pero nunca contabiliza ni cierra** sin decisión humana.

---

## ⚠️ 5 Errores Clásicos en Bancos (y Cómo Evitarlos)

| Error clásico | Qué pasa | Cómo hacerlo bien |
|---|---|---|
| Crear un asiento de gasto y otro de ingreso para una transferencia devuelta | Infla falsamente tus gastos e ingresos en el Estado de Resultados | Usa **«Compensar con su devolución»** en conciliación y **«Corregir referencia»** en el pago |
| Intentar cerrar la conciliación con diferencia distinta de `0,00` | El sistema bloquea el cierre (casi siempre faltan comisiones/notas del banco) | Revisa líneas pendientes del extracto y usa **«Registrar»** en comisiones/intereses |
| Importar un extracto en dólares dentro de una cuenta en bolívares | El sistema te detiene avisando la cuenta y moneda correcta | Verifica siempre la cuenta elegida arriba en el modal de importación |
| Querer anular un cobro o pago que ya está conciliado | GesPro lo impide para no romper una conciliación | Si está abierta, pulsa **«Deshacer»** en el cruce; si está cerrada, ajusta en el período siguiente |
| Dejar acumular un mes entero sin subir extractos | Cierres estresantes con cientos de partidas sin recordar de quién eran | Sube el extracto a diario o semanalmente y activa el **Agente de conciliación bancaria** |

---

## 🛠️ Reto Práctico del Estudiante (30 min)

1. Entra a **Tesorería → Bancos y conciliación → Cuentas y saldos**. Revisa qué cuentas tienen saldo en bolívares y lee su columna de **Devaluación** (si la empresa opera multimoneda).
2. Ve a **Extracto del banco → Importar extracto**. Selecciona la cuenta bancaria del Banco Mercantil (`BCO-03` en la demo) y sube el archivo real **`ejemplos/extracto-mercantil-agosto.txt`**. Verifica el resumen de validación (`SI + créditos − débitos = SF`).
3. Abre una **Nueva conciliación** con la fecha de corte y el saldo final del extracto.
4. Pulsa **«Cruce automático»** y observa cuántas partidas se cruzan en 1 segundo.
5. Practica **1 cruce manual** (una fila de la izquierda + una de la derecha) y pulsa **«Registrar»** en una línea de comisión bancaria asignándola a *Comisiones y gastos bancarios*.
6. *(Si tu conciliación llega a diferencia `0,00`)* Pulsa **«Cerrar conciliación»** y compruébala luego en el **Histórico**.

---

## 📌 Chuleta Rápida (1 minuto)
- **Los 7 pasos:** `1. Revisar libro → 2. Importar extracto → 3. Abrir conciliación → 4. Cruce automático → 5. Emparejar a mano → 6. Registrar notas del banco → 7. Compensar devoluciones y cerrar en 0,00`.
- **Transferencia devuelta:** En el pago usa **«Corregir referencia»**; en el extracto usa **«Compensar con su devolución»** (cero asientos falsos).
- **Cierre:** Solo cierra en **`0,00`**; al cerrar bloquea partidas y saldo inicial.
- **Automatiza:** Activa **Configuración → Agentes → Conciliación bancaria** para informes diarios por área.
