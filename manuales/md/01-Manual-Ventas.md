# Manual del Usuario · Módulo 1: Ventas
**GesPro Administrativo v5.7.0 · Guía Práctica del Estudiante**

> **Tu misión en este módulo:** Dominar el recorrido completo de una venta —desde el primer contacto con un prospecto hasta el pedido en firme, el Punto de Venta en mostrador y la Tienda en línea— sin perder oportunidades ni prometer mercancía que no existe.  
> **🎬 Videos de repaso de este módulo (disponibles también en versión `-WhatsApp.mp4`):** `01-Vendedor` (`3:40`) · `02-Cotizaciones` (`1:46`) · `03-Punto-de-venta` (`2:05`) · `04-Tienda-en-linea` (`1:57`) · `Guia-del-vendedor` (`5:29`, móvil).

---

## 1. Mapa del Módulo de Ventas

En GesPro, todas las puertas por donde entra una venta viven en el grupo **Ciclo comercial** del menú lateral (y el portal móvil en `/vendedores`):

| Sección del menú | Para qué la usarás todos los días |
|---|---|
| **Vendedor (CRM)** | Prospectos, Embudo de negocios, Agenda de llamadas/visitas, Clientes 360, Cotizaciones, Pedidos, Carteras, Ruta y visitas, Comisiones, Automatización y Marketing. |
| **Cotizaciones** | Bandeja dedicada para emitir ofertas formales en PDF, controlar su fecha de validez y aprobar descuentos grandes. |
| **Punto de venta (POS)** | Venta rápida en mostrador con lector de código de barras, pago multimoneda con vuelto, impresora térmica y modo **sin conexión**. |
| **Tienda en línea** | Catálogo web público conectado a tu inventario real, cupones y pagos en línea (Stripe, PayPal, Binance Pay, Pago Móvil C2P Mercantil). |
| **Portal de vendedores (`/vendedores`)** | Pantalla móvil para vendedores de calle: asistente *«Mi día»*, levantar pedidos, cargar comprobantes de pago y dictar cierres de visita por voz. |

> **💡 Regla de oro de GesPro:** Un **Prospecto** no es cliente hasta que compra; una **Cotización** no aparta mercancía ni se factura directa; un **Pedido** aparta mercancía por **24 horas hábiles** pero todavía no toca la contabilidad. Nada entra en los libros hasta que Administración aprueba la factura.

---

## 2. Vendedor (CRM): Vende con orden y sin olvidar seguimientos

### 2.1 De Prospecto a Cliente (Paso a paso)
1. Entra a **Vendedor (CRM) → Prospectos** y pulsa **«+ Prospecto»**.
2. Escribe nombre, empresa, teléfono o correo y cómo llegó (*origen*). Si el teléfono, correo o RIF ya existen, GesPro te avisa para no duplicar.
3. Observa la **Puntuación de prospectos (0 a 100)**:
   - 🔥 **70 o más (Caliente):** llamar hoy primero.
   - 🌤️ **40 a 69 (Tibio):** seguimiento programado.
   - ❄️ **Menos de 40 (Frío):** nutrir o retomar.
4. Deja agendada la primera acción en **Agenda** (te ordena primero lo **vencido**, luego **hoy** y **esta semana**).
5. Cuando haya un negocio concreto, crea una **Oportunidad** (monto estimado y fecha de cierre). Muévela arrastrando la tarjeta en el **Embudo** (*arrastrar y soltar*).
6. Si el cliente compra, conviértelo en **Cliente** (pasa todo su historial y contactos). Si pierdes el negocio, elige siempre el **motivo de pérdida** (precio, competencia, plazos…): el Tablero usa esto para saber qué corregir.

### 2.2 Clientes 360 y Automatización
- En **Clientes 360**, haz clic en cualquier cliente y verás en una sola pantalla: lo que compra, cuánto debe, sus contactos, sus negocios y todo lo hablado con él.
- En **Automatización** puedes usar **Plantillas** de correo/WhatsApp (`{{nombre}}`, `{{empresa}}`, `{{vendedor}}`), **Secuencias** (ej. llamar hoy → escribir a los 3 días → visitar a la semana) y **Formularios web** que reparten prospectos por turno.
- En **Marketing**, arma **Segmentos** dinámicos (ej. *«clientes que no compran hace 60 días»*) y lanza campañas por correo o cola de WhatsApp midiendo aperturas, clics y ventas generadas.

---

## 3. Cotizaciones y Aprobación de Descuentos

### Cómo emitir una cotización sin sorpresas
1. Entra a **Cotizaciones** (o **Vendedor (CRM) → Cotizaciones**) y pulsa **«+ Nueva cotización»** (o pulsa **«Cotizar»** directo desde una Oportunidad del CRM).
2. Selecciona el cliente, la **fecha de validez** (30 días por defecto; sale impresa en grande en el PDF para evitar discusiones de precios viejos) y agrega los artículos del catálogo.
   - **Protección automática:** GesPro **no deja cotizar** artículos que no tienen existencia en ningún almacén.
3. Guarda y pulsa **«Descargar PDF»** para enviársela al cliente por correo o WhatsApp.

### ¿Qué pasa si das un descuento grande?
Si tu empresa activó **Configuración → Descuentos**, según el mayor descuento de un renglón se piden aprobaciones automáticas por **GP Mensajes**:
- **Desde 25 %:** aprueba el Aprobador 1.
- **Desde 50 %:** aprueban el 1 y el 2.
- **Desde 75 %:** aprueban los tres.
> Mientras espera aprobación, la cotización queda en estado *«Descuento por aprobar»* y **no se puede imprimir ni aceptar**.

### Cuando el cliente responde
- **Dijo SÍ:** Abre la cotización y pulsa **«El cliente la aceptó»**. Nace un **Pedido en firme** con los mismos renglones y precios (la cotización original queda intacta como prueba histórica).
- **Dijo NO:** Pulsa **«El cliente la rechazó»** e indica el motivo.
- **Venció sin respuesta:** Ya no se puede aceptar; emite una nueva a precios de hoy.

---

## 4. Pedidos, Mercancía Apartada (24 h hábiles) y Comisiones

![Pedidos de vendedores](../presentacion/img/pedidos.png)

### La regla de la mercancía apartada (¡muy importante!)
Cada **Pedido en firme** (de un vendedor, de la tienda en línea o de una cotización aceptada) **aparta automáticamente la mercancía durante 24 horas hábiles** (sábados y domingos no cuentan; ej. viernes 5:00 p. m. → lunes 5:00 p. m.):
- Mientras esté apartado, **nadie más puede vender esas unidades** (ni otra factura, ni POS, ni Tienda, ni Manufactura).
- Si el cliente **ya pagó** (pago en línea o comprobante cargado por el vendedor), la reserva **no vence**.
- Si pasan las 24 h hábiles sin facturarse, la mercancía se libera, el pedido pasa a **VENCIDO** y avisa por GP Mensajes. Para retomarlo, Facturación pulsa **«Hacer de nuevo»** (vuelve a apartar si aún hay stock).

### Comisiones sin discusiones a fin de mes
![Comisiones de vendedores](../presentacion/img/pedidos-comisiones.png)
- Se configuran en **Vendedor (CRM) → Comisiones** por vendedor: por **vender**, por **cobrar**, o ambas.
- Siempre se calculan sobre el monto **SIN IVA** (el IVA es del fisco, no ingreso de la empresa) y convertidas a la moneda base.
- Comisiona el vendedor asignado en la **ficha del cliente** al momento de facturar.

---

## 5. Punto de Venta (POS): Rápido, Multimoneda y Sin Conexión

### Tu rutina diaria en caja
1. **Abrir turno:** Entra a **Punto de venta**, elige tu caja y declara el **fondo inicial en efectivo**. *(Nadie puede vender sin turno abierto, y una caja solo la abre una persona a la vez).*
2. **Vender:** Escanea el código de barras (con lector USB o botón de cámara `📷`) o busca por nombre. Ajusta cantidad o descuento permitido (no puedes alterar el precio de lista).
3. **Identificar al cliente (opcional):** Si quiere la factura a su nombre, pulsa **«Con cédula o RIF»**; si no existe, créalo rápido con su nombre.
4. **Cobrar:** Pulsa **Cobrar**. Puedes combinar formas de pago (ej. parte en USD efectivo, parte en Bs punto de venta). Usa el botón **«Exacto»** para completar lo que falta.
   - Si cobras en divisas y la empresa es contribuyente especial, el **IGTF del 3 %** se calcula solo sobre lo que se queda la empresa (no sobre el vuelto).
   - Al confirmar, se emite la factura fiscal, se imprime el ticket térmico y se abre la gaveta automáticamente.
5. **Cerrar turno:** Al final del día, cuenta el dinero real por cada forma de pago y escríbelo. GesPro compara contra lo esperado y registra cualquier sobrante o faltante para el supervisor.

### ¿Qué hago si se cae internet en medio de la cola?
- **No detengas la caja.** El indicador superior se pondrá en **rojo** y podrás seguir vendiendo con el catálogo guardado al abrir el turno.
- El cliente recibe un **Comprobante Provisional (`PRV-…`)**.
- Al volver internet, GesPro envía y factura automáticamente cada venta (sin duplicarlas). *Nota: no puedes cerrar el turno mientras queden ventas sin sincronizar o por revisar.*

---

## 6. Tienda en Línea y Portal de Vendedores (`/vendedores`)

### Tienda en línea
- En **Tienda en línea → Configuración** eliges el almacén de venta, métodos de entrega y cuentas bancarias. En **Productos**, publicas los artículos (con foto y descripción; requiere precio de venta).
- En **Cupones**, creas descuentos por % o monto fijo con vigencia, compra mínima y límite por RIF/cédula.
- En **Pagos en línea**, se activan **Stripe (tarjeta), PayPal, Binance Pay y Pago Móvil C2P del Banco Mercantil**. Los pedidos pagados en línea llegan ya verificados a **Vendedor (CRM) → Pedidos**.

### Portal de vendedores (`/vendedores`)
![Portal de vendedores en el teléfono](../presentacion/img/portal-vendedores.png)
- **«Mi día»:** Lista inteligente priorizada de a quién llamar o visitar hoy (tareas vencidas, facturas vencidas, cotizaciones por vencer, clientes que ya les toca reponer).
- **Pedidos y pagos en la calle:** El vendedor solo ve **su propia cartera**. Puede levantar pedidos/cotizaciones y cargar la foto del comprobante de pago que le entregue el cliente.
- **Ruta y visitas (con asistente de voz):** Inicia jornada → pulsa **«Llegué»** (verifica geocerca GPS) → al salir pulsa **«Contar la visita»** para dictar en voz alta lo ocurrido y que el formulario se llene solo antes de guardar.

---

## ⚠️ 5 Errores Clásicos en Ventas (y Cómo Evitarlos)

| Error clásico | Qué pasa en GesPro | Cómo hacerlo bien |
|---|---|---|
| Intentar facturar una cotización sin aceptarla | El sistema no lo permite | Abre la cotización → **«El cliente la aceptó»** → luego se factura el Pedido en CxC |
| Dejar un pedido sin facturar más de 24 h hábiles | La reserva caduca y otro puede vender esa mercancía | Revisa el contador de **Pedidos por facturar** o registra el pago si el cliente ya pagó |
| Dejar un cliente sin «Vendedor» en su ficha | La factura sale sin vendedor y **no genera comisión** | Verifica siempre el campo obligatorio **Vendedor** en la ficha del cliente |
| Querer anular una venta de POS después de cerrar el turno | Ya no se puede anular en caja | Emite una **Nota de crédito** desde Cuentas por cobrar |
| Cotizar sin revisar existencia | El sistema bloquea artículos sin stock | Revisa disponibilidad real (existencia menos lo apartado) antes de ofertar |

---

## 🛠️ Reto Práctico del Estudiante (20 min)

1. Ve a **Vendedor (CRM) → Prospectos** y crea un prospecto nuevo con tus iniciales (ej. *«Comercializadora [Tus Iniciales]»*). Verifica su puntuación y agéndale una llamada para mañana.
2. Ve a **Cotizaciones → + Nueva cotización**, elige un cliente existente, agrega 2 artículos con stock y dale validez de 5 días. Descarga el PDF.
3. Abre esa cotización y pulsa **«El cliente la aceptó»**. Anota el número de Pedido `PED-…` que nació (lo necesitarás en el Módulo 2).
4. Entra a **Punto de venta**, abre turno, vende 1 artículo combinando **dos formas de pago** y visualiza el ticket.

---

## 📌 Chuleta Rápida (1 minuto)
- **Flujo estándar:** `Prospecto → Oportunidad → Cotización → [Aceptada] → Pedido (aparta 24 h hábiles) → Factura (en CxC)`.
- **Descuentos grandes en cotización:** 25 % / 50 % / 75 % piden aprobación por GP Mensajes.
- **POS sin internet:** Sigue vendiendo (`PRV-…`) y sincroniza solo al volver la red.
- **¿Dudas en un campo?** Pulsa el ícono **`ⓘ`** junto al título o el botón **`?`** arriba a la derecha.
