# Manual del Usuario · Módulo 5: Análisis de Costos
**GesPro Administrativo v5.7.0 · Guía Práctica del Estudiante**

> **Tu misión en este módulo:** Descubrir cuánto te cuesta *de verdad* cada producto o servicio que vendes (importado, fabricado, servicio o mixto), calcular el precio de venta correcto para no perder margen, aprovechar la IA Gemini como analista y entender la utilidad real con Costo Promedio vs PEPS.  
> **🎬 Videos de repaso de este módulo (`-WhatsApp.mp4` disponibles):** `23-Analisis-de-costos` (`3:48`) · *complementos:* `22-Importaciones` (`2:39`) · `21-Reportes` (`1:38`).

---

## 1. ¿Por Qué Existe Análisis de Costos?

Uno de los errores más caros en cualquier empresa es fijar precios «a ojo» o multiplicar el costo de factura por 1,30 creyendo que se gana un 30 %. Cuando sumas flete marítimo, seguro, aranceles, agente aduanal, transporte al almacén, gastos generales de la empresa y comisiones de ventas, ese «30 %» suele convertirse en un **5 %… o en pérdida**.

En **Operaciones → Análisis de costos**, cada artículo o servicio tiene su **Ficha de costo** viva, con el origen exacto de cada cifra. Y cuando Contabilidad o Administración la aprueba, **actualiza el costo del artículo y revaloriza el inventario automáticamente**.

---

## 2. Las Cuatro Modalidades de Costeo

Al pulsar **«Nueva ficha de costo»**, GesPro soporta 4 formas de obtener lo que vendes y llena automáticamente lo que ya sabe tu sistema:

| Modalidad | Lo que GesPro llena SOLO desde tu sistema | Lo que tú revisas o completas |
|---|---|---|
| **Importado** | Precio de la última factura de compra, o los costos repartidos de una **Importación** (flete, seguro, aduana, impuestos). Sin importación ligada, toma el % histórico de gastos de tus importaciones anteriores. | Arancel específico del código arancelario y transporte local hasta el almacén. |
| **Elaborado** | La receta de **Manufactura**: cada material con su merma al costo de hoy, mano de obra y gastos de fabricación para el lote de la receta. | Cualquier gasto adicional fuera de la receta. |
| **Servicio** | Costo por hora real del personal activo en **Recursos humanos** (`sueldo ÷ 173,33 horas/mes`, sin cargas sociales). | Cantidad de horas que lleva prestar el servicio, insumos y servicios de terceros. |
| **Mixto** | Combina lo que aplique de compras, receta y horas de personal. | Ajustes específicos del paquete producto + servicio. |

> **Plus automático en las 4 modalidades:** Si tienes contabilidad con historial, GesPro calcula solo tus **Gastos generales y de administración** comparando los gastos de los últimos **3 meses completos** contra las ventas del mismo período (como % del precio de venta).

---

## 3. Dos Conceptos que Debes Dominar como la Palma de tu Mano

### A. La casilla **`Al costo`** (¡No mezcles inventario con gastos de venta!)
Cada renglón de una ficha tiene una casilla llamada **`Al costo`**:
- **✅ Marcada (`Al costo`):** Forma parte del **Costo del artículo** (lo que contablemente va al inventario): *Precio FOB, Flete, Seguro, Aranceles, Aduana, Transporte al almacén, Materiales, Mano de obra, Gastos de fabricación*.
- **⬜ Desmarcada:** **No** infla el valor del inventario; **solo cuenta para calcular el Costo completo y el Precio sugerido**: *Gastos generales y de administración, Comisiones de venta*.

### B. La Fórmula Exacta del Precio Sugerido (Margen sobre Precio)
En GesPro, un margen del **30 %** significa que el **30 % del precio final que paga el cliente** es ganancia neta después de cubrir costos, gastos generales y comisiones:

$$\text{Precio sugerido} = \frac{\text{Costo completo (por unidad)}}{1 - \text{Margen} - \sum \%\text{ sobre el precio}}$$

**Ejemplo real paso a paso:**
- Costo del artículo (FOB + flete + aduana): **$13,86**
- Gastos generales: **12 %** del precio de venta *(sin marcar `Al costo`)*
- Comisión al vendedor: **3 %** del precio de venta *(sin marcar `Al costo`)*
- Margen deseado: **30 %** sobre el precio de venta
- Cálculo de GesPro: `13,86 ÷ (1 − 0,30 − 0,12 − 0,03) = 13,86 ÷ 0,55 =` **$25,20**
- *Comprobación:* De $25,20, el 12 % son $3,02 (gastos generales), el 3 % son $0,76 (comisión), el costo es $13,86 → quedan **$7,56** de ganancia, que es exactamente el **30,0 %** de $25,20.

### Bases de cálculo disponibles en cada renglón
Cada renglón puede ser un **Importe** (`cantidad × unitario`, incluso en otra moneda convertida a la tasa de la fecha de la ficha) o un **Porcentaje** calculado sobre 4 posibles bases:
1. **del precio de compra (FOB)**
2. **del CIF** (`compra + flete + seguro`, la base legal de los aranceles)
3. **del costo del artículo**
4. **del precio de venta** *(se despeja automáticamente con la fórmula de arriba)*

---

## 4. Crear, Revisar (con IA) y Aprobar una Ficha de Costo

### Paso a paso individual
1. Entra a **Operaciones → Análisis de costos** y pulsa **«Nueva ficha de costo»**.
2. Elige el **Artículo o servicio**, la modalidad y con qué llenarla:
   - **Los datos del sistema y la IA:** GesPro carga los datos reales y **Gemini (IA)** propone estimaciones para los renglones faltantes.
   - **Los datos del sistema:** Solo cifras reales de facturas, recetas, importaciones y nómina.
   - **Nada (la escribo yo):** Ficha en blanco.
3. **Revisa las cifras en amarillo:** Todo lo que la IA estimó aparece resaltado en **amarillo** con etiqueta **`Estimado`** y su explicación debajo.
   - *Seguridad y privacidad:* La IA solo ve el artículo y cifras anónimas (nunca nombres de clientes ni proveedores), y **jamás aprueba nada por su cuenta**.
4. Edita cualquier cantidad, moneda, importe o porcentaje: los 4 indicadores superiores (*Costo del artículo, Costo completo, Precio sugerido y Costo de hoy*) se recalculan **en vivo mientras escribes**.
5. Escribe el **Margen sobre el precio (%)** que buscas. Debajo de los indicadores, GesPro te dice de inmediato: *«Precio 1 de hoy: X; con el costo completo de la ficha deja Y % de margen»* (¡alerta instantánea si estás vendiendo muy barato!).
6. Pulsa **«Guardar»**. Queda en **BORRADOR**.
7. **Aprobar (solo Contabilidad o Administrador):** Pulsa **«Aprobar…»**. Una ventana te muestra exactamente:
   - El costo nuevo vs el actual.
   - Cuánto cambia el valor del inventario y contra qué cuenta contable va el asiento.
   - La casilla opcional **«Actualizar también el Precio 1»** (si quieres adoptar de una vez el precio sugerido).

### Atajo masivo para importadores: Pestaña «Desde una importación»
1. Cuando una importación ya tiene aprobada su factura de mercancía y sus gastos (flete, seguro, aduana), abre la pestaña **«Desde una importación»**.
2. Elige la importación y el criterio de reparto: **«Según lo que costó cada artículo» (por valor)** o **«Por unidades» (por cantidad)**.
3. Revisa la tabla con el **Costo de llegada** de cada artículo y pulsa **«Preparar las fichas de todos»**: GesPro crea un borrador por cada artículo de golpe, listo para revisar y aprobar.
   - *Ventaja contable:* Al aprobar las fichas ligadas a una importación abierta, esos gastos **salen de la cuenta transitoria de la importación y pasan al costo del inventario**, de modo que al cerrar la importación ya no se mandan a gastos.

---

## 5. ¿Qué Pasa Exactamente al Aprobar una Ficha?

| Tipo de artículo | Efecto en Inventario / Kardex | Efecto en Contabilidad |
|---|---|---|
| **Producto CON existencia** | Su costo promedio pasa al de la ficha. En el **Kardex** aparece una línea **`REVALORIZACION`** sin cambiar unidades, mostrando el cambio de valor por almacén. | Asiento automático por `existencia × diferencia de costo` contra la cuenta transitoria de la importación, ajustes de inventario o apertura. |
| **Producto SIN existencia** | Guarda el costo de referencia en la ficha del artículo; la próxima compra volverá a promediar con su factura. | Sin asiento (existencia = 0). |
| **Servicio** | Actualiza el costo unitario del servicio (usado para medir su margen en reportes de rentabilidad). | Sin asiento (no tiene stock). |

*(La ficha aprobada anteriormente no se borra: pasa al historial con estado **`Reemplazada`**).*

---

## 6. Complemento Gerencial: Utilidad Bruta (Promedio vs PEPS) y Agentes

Para vigilar tus márgenes todos los días después de costear:
1. **Reportes → Utilidad bruta:** Compara tus ventas del período dos veces lado a lado:
   - **Costo promedio:** El oficial de tu contabilidad.
   - **PEPS (Primero en entrar, primero en salir):** Mide cuánto ganaste usando el costo original de las unidades más antiguas. *(Cuando los costos suben por inflación, PEPS muestra más utilidad contable; cuando bajan, menos).*
   - *Nota:* Es solo analítico; no modifica tus libros. También avisa si vendiste algo con costo `$0` (margen falso del 100 %).
2. **Agentes automáticos (`Configuración → Agentes`):**
   - **Rentabilidad (semanal):** Detecta artículos vendidos por debajo del costo, por debajo del margen mínimo o que cayeron ≥5 puntos porcentuales.
   - **Costos de compra e inventario sin movimiento (diario/semanal):** Avisa apenas entra una compra más cara que el promedio de los últimos 90 días (ej. >10 %) y te dice cómo quedó tu margen actual con el nuevo costo.

---

## ⚠️ 5 Errores Clásicos en Análisis de Costos (y Cómo Evitarlos)

| Error clásico | Consecuencia | Cómo hacerlo bien |
|---|---|---|
| Marcar `Al costo` en *Gastos generales* o *Comisiones de venta* | Inflas artificialmente el activo de inventario violando normas contables | Deja **desmarcada** `Al costo` en gastos generales y comisiones (solo afectan el precio) |
| Aprobar una ficha con cifras en **amarillo (`Estimado`)** sin verificarlas | Queda contabilizado un costo inventado por la IA o aproximado | Revisa y reemplaza cada renglón amarillo por tu tarifa/factura real antes de aprobar |
| Poner margen + gastos sobre precio que suman casi 100 % | El denominador se vuelve cero o negativo (el sistema te bloquea con error) | Mantén `Margen + % sobre precio < 95 %` |
| Cerrar una importación antes de repartir sus costos en `Análisis de costos` | Todos los fletes y aduanas se van al gasto del mes en vez del costo del producto | Primero reparte y aprueba las fichas en **Desde una importación**, luego cierra la importación |
| Confundir «recargo sobre costo» (×1,30) con «margen sobre precio» (÷0,70) | Crees que ganas 30 % cuando solo ganas 23 % | Confía en el **Precio sugerido** de GesPro (calcula margen real sobre precio de venta) |

---

## 🛠️ Reto Práctico del Estudiante (20 min)

1. Ve a **Operaciones → Análisis de costos → «Nueva ficha de costo»**. Elige un artículo inventariable en modalidad **Importado** (usa *«Los datos del sistema»* o *«Los datos del sistema y la IA»* si está activa).
2. Asegúrate de tener estos renglones (añade con **«Añadir renglón»** los que falten):
   - Precio de compra (FOB): importe real o `10,00` USD (`Al costo` ✅)
   - Flete: importe `2,00` USD (`Al costo` ✅)
   - Arancel: porcentaje `15 %` sobre **CIF** (`Al costo` ✅)
   - Gastos generales: porcentaje `12 %` sobre **precio de venta** (`Al costo` ⬜)
   - Comisiones de venta: porcentaje `3 %` sobre **precio de venta** (`Al costo` ⬜)
3. Escribe **30** en **Margen sobre el precio (%)**. Anota en tu cuaderno:
   - *Costo del artículo:* ________
   - *Costo completo:* ________
   - *Precio sugerido:* ________
   - *¿El Precio 1 actual estaba ganando o perdiendo frente al margen de 30 %?*
4. Guarda y **Aprueba** la ficha (revisa el cuadro de impacto en inventario). Luego abre el **Kardex** de ese artículo y ubica la línea **`REVALORIZACION`**.
5. Abre **Reportes → Utilidad bruta** y compara la columna de Costo Promedio vs PEPS.

---

## 📌 Chuleta Rápida (1 minuto)
- **`Al costo` ✅** = Entra al inventario (FOB, flete, seguro, arancel, aduana, materiales, mano de obra).
- **`Al costo` ⬜** = Solo para calcular precio (gastos generales, comisiones).
- **Amarillo (`Estimado`)** = Propuesta de IA; **revisa siempre antes de aprobar**.
- **Fórmula mágica:** `Precio = Costo completo ÷ (1 − Margen − % sobre precio)`.
- **Importaciones:** Reparte en **Desde una importación** → **Preparar las fichas de todos**.
