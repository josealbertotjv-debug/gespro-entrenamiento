# Manual del Usuario · Módulo 4: Inventario
**GesPro Administrativo v5.7.0 · Guía Práctica del Estudiante**

> **Tu misión en este módulo:** Saber en todo momento qué mercancía tienes, dónde está, cuánto vale al costo promedio ponderado, qué está apartado por pedidos, cómo reponer faltantes y cómo documentar cada salida con Notas de despacho sin descuadrar la contabilidad.  
> **🎬 Videos de repaso de este módulo (`-WhatsApp.mp4` disponibles):** `15-Inventario` (`1:41`) · *opcionales:* `16-Manufactura` (`1:53`) · `17-Sucursales` (`1:20`).

---

## 1. Mapa del Módulo de Inventario (11 Pestañas)

En **Operaciones → Inventario** encontrarás pestañas organizadas para controlar el ciclo físico y valorado *(nota: quienes no tienen permiso de ver costos —como vendedores o cajeros— solo ven existencias y precios, nunca costos ni kardex)*:

| Pestaña | Para qué sirve |
|---|---|
| **Artículos** | Catálogo de productos y servicios, precios (Precio 1, 2 y 3), costo promedio, valorización, importación desde Excel/CSV y adjuntos del producto (garantías, fichas técnicas, certificados). |
| **Existencias por almacén** | Stock real sede por sede y el recuadro clave **«Apartado por pedidos»** (Existencia − Apartado = Disponible real). |
| **Kardex** | Historial movimiento por movimiento de cada artículo (entradas, salidas, costo promedio y saldo después de cada operación). |
| **Costo inicial** | Herramienta masiva para cargar costo a artículos migrados del sistema anterior con existencia en cero costo. |
| **Alertas de stock** | Productos que llegaron a su stock mínimo o están por debajo. |
| **Órdenes de compra** | Pedidos a proveedores (manuales o automáticos con **«Generar por faltantes»**). |
| **Recepción de mercancía** | Registro físico de la entrada de mercancía de órdenes aprobadas. |
| **Listas de precios** | Listas de precios de proveedores para comparar y presupuestar reposiciones. |
| **Transferencias** | Mover mercancía de un almacén a otro (sin asiento contable, porque el valor total de la empresa no cambia). |
| **Notas de despacho** | **Órdenes de entrega** (ventas) y **Guías de despacho** (donaciones, muestras con solicitante, traslados, consignación). |
| **Almacenes** | Gestión de almacenes, su sucursal asociada y su **Encargado de despachar** (recibe avisos en GP Mensajes). |

*(Módulos hermanos bajo Operaciones: **Manufactura** para recetas y órdenes de producción, y **Sucursales** para gestionar varias sedes).*

---

## 2. Catálogo, Costo Promedio y «Costo Inicial»

![Catálogo de artículos](../presentacion/img/inventario-articulos.png)

### Cómo calcula GesPro el costo (Costo Promedio Ponderado)
- Cada vez que entra mercancía por una compra (o producción), el costo promedio se recalcula automáticamente:
  $$\text{Nuevo costo promedio} = \frac{(\text{Existencia actual} \times \text{Costo anterior}) + (\text{Cantidad nueva} \times \text{Costo nuevo})}{\text{Existencia total}}$$
- Al vender, ese costo promedio es el que sale al **Costo de ventas** en contabilidad. Por eso el costo promedio **nunca se teclea a mano** en la ficha del artículo: tocarlo descuadraría el inventario contra el balance.

### 🚨 Alerta Roja: «Artículos con existencia y sin costo» → `Costo inicial`
Si migraste existencias desde un sistema viejo sin ponerles costo, esas unidades entraron en **$0,00**. Si compras mercancía nueva sin corregir eso primero:
- *Ejemplo del desastre:* 10 unidades a $0 + 10 unidades compradas a $20 = promedio de **$10** (falso).
- **Solución en 4 pasos (`Inventario → Costo inicial`):**
  1. Abre la pestaña **Costo inicial** (muestra todos los artículos con stock y costo $0).
  2. Escribe el costo unitario en la columna (o pulsa **«Plantilla»**, llénalo en Excel y súbelo con **«Subir archivo»**).
  3. Elige la fecha y pulsa **«Revisar y guardar»** para comprobar el asiento contable (*Debe: Inventario / Haber: Saldos de apertura*, no es ganancia del mes).
  4. Confirma **«Guardar los costos»**. En el Kardex aparecerá una línea **`COSTO INICIAL`** sin cambiar unidades.

### Papeles de cada artículo y Moneda de Precios
- Dentro de cualquier artículo puedes adjuntar hasta 6 MB en PDF o imagen (factura original, garantía, manual, certificado): viajan siempre con la ficha.
- Si tu contabilidad va en bolívares pero fijas precios en dólares (`MONEDA_PRECIOS = USD`), escribes el precio y costo en USD y GesPro convierte automáticamente a la tasa BCV del día al facturar o guardar el kardex.

---

## 3. El Kardex y la Mercancía Apartada (24 h hábiles)

![Kardex de inventario](../presentacion/img/inventario-kardex.png)

### Usar el Kardex como lupa de auditoría
Cuando algo no cuadra en almacén, **empieza siempre en `Inventario → Kardex`**:
- Elige el artículo (y opcionalmente almacén y rango de fechas — si filtras desde una fecha, el kardex arranca con el **saldo inicial arrastrado**).
- Cada fila te dice: fecha, tipo de movimiento (compra, venta, ajuste, transferencia, costo inicial, revalorización, despacho), documento origen, cantidad, costo unitario y saldo resultante.

### Existencias vs Disponible («Apartado por pedidos»)
- En **Existencias por almacén**, revisa el cuadro **«Apartado por pedidos»**: muestra Existencia total, unidades apartadas por pedidos firmes (con su hora exacta de vencimiento de 24 h hábiles) y lo realmente **Disponible**.
- GesPro impide vender o producir por encima de lo disponible para evitar sobreventas.

---

## 4. Ajustes, Transferencias y Reposición (Órdenes de Compra)

### Diferencia clave entre Transferencia y Ajuste
| Operación | Cuándo usarla | ¿Genera asiento contable? |
|---|---|---|
| **Transferir** (botón arriba o pestaña *Transferencias*) | Mover cajas del Almacén Principal al Almacén Sucursal Valencia | **NO** (el valor total del inventario de la empresa no cambia) |
| **Ajustar existencia** (botón arriba) | Conteo físico (sobrantes/faltantes), roturas, mermas, inventario inicial | **SÍ** (automático contra cuenta de mermas/ajustes o apertura) |

> **Ojo con Sucursales:** La sucursal a la que se acredita una venta sale del **Almacén** de donde se despacha la mercancía, no de quién hizo la factura. Si ves un aviso rojo de *«Almacenes sin sucursal»*, pulsa **«Asignarlos a la principal»**.

### Órdenes de compra y Recepción de mercancía
1. En **Alertas de stock** ves los artículos en o bajo el stock mínimo.
2. En **Órdenes de compra**, pulsa **«Generar por faltantes»**: GesPro arma automáticamente borradores agrupados por el proveedor habitual de cada artículo (también puede hacerlo el **Agente de Compras** según horario).
3. El encargado revisa, edita cantidades si hace falta y pulsa **«Revisar y aprobar»**.
4. Cuando llega el camión, en **Recepción de mercancía** (o desde la orden aprobada → **«Registrar recepción»**) se registra lo que entró realmente (puede ser recepción parcial).

---

## 5. Notas de Despacho (Órdenes de Entrega y Guías)

En **Inventario → Notas de despacho** salen los documentos físicos que acompañan a la mercancía (con número `DES-…`, logo y leyenda obligatoria **«SIN DERECHO A CRÉDITO FISCAL»** — Providencia SNAT/2024/000102):

| Motivo | Nombre del papel | Cómo nace | ¿Mueve inventario? | ¿Genera asiento? |
|---|---|---|---|---|
| **Venta** | Orden de entrega | **Sola** al aprobar una factura con mercancía | No (ya lo descontó la factura) | No (ya lo hizo la factura) |
| **Muestra** | Guía de despacho | Botón **«Nueva nota de despacho»** *(pide Solicitante)* | Sí (sale al costo promedio) | Sí (Gasto por muestras vs Inventario) |
| **Donación** | Guía de despacho | Botón **«Nueva nota de despacho»** *(pide Solicitante)* | Sí (sale al costo promedio) | Sí (Gasto por donaciones vs Inventario) |
| **Traslado** | Guía de despacho | Botón **«Nueva nota de despacho»** | Sí (de almacén origen a destino) | No |
| **Préstamo / Consignación** | Guía de despacho | Botón **«Nueva nota de despacho»** | Pasa al almacén destino (ej. Consignación) | No |

- **Control de muestras y donaciones:** En *Muestra* o *Donación*, el campo **«Solicitante»** es obligatorio (quién lo pidió: vendedor, gerente, médico…). Al buscar su nombre en la lista de Notas de despacho, GesPro suma arriba cuántas muestras pidió y cuánto costaron.
- Cuando el encargado del almacén entrega físicamente las cajas, abre la nota y pulsa **«Marcar despachada»**.

---

## 6. Bonus: Manufactura (si tu empresa fabrica o ensambla)

En **Operaciones → Manufactura**:
1. **Recetas:** Define los insumos, cantidades, merma esperada, mano de obra y costos indirectos por lote (soporta subensambles multinivel y bloquea recetas circulares).
2. **Orden de producción (3 pasos):**
   - **Planificar (Borrador):** Verifica si alcanza la materia prima nivel por nivel.
   - **Iniciar:** Saca los insumos del almacén y pasa su costo a *Producción en proceso*.
   - **Terminar:** Ingresa las unidades buenas que realmente salieron; el costo real del lote (insumos + mano de obra + indirectos) se divide entre las unidades buenas producidas y entra al inventario con su costo real.

---

## ⚠️ 5 Errores Clásicos en Inventario (y Cómo Evitarlos)

| Error clásico | Qué pasa | Cómo hacerlo bien |
|---|---|---|
| Comprar encima de inventario migrado con costo `$0` | El costo promedio se desploma a la mitad y falsea tus utilidades | Carga primero el costo real en **Inventario → Costo inicial** |
| Usar «Ajustar existencia» (salida + entrada) en vez de «Transferir» | Genera dos asientos innecesarios de merma/ajuste y ensucia resultados | Usa siempre **Transferir** para mover stock entre tus almacenes |
| Sacar muestras o regalos «de palabra» sin documento | Faltantes inexplicables en el conteo de fin de mes | Emite una **Nota de despacho (Muestra)** indicando el **Solicitante** |
| Ignorar el cuadro «Apartado por pedidos» | Crees que sobra mercancía y te sorprende que el sistema bloquee la venta | Mira siempre la columna **Disponible** (= Existencia − Apartado) |
| Dejar un almacén sin «Encargado de despachar» | Nadie recibe el aviso inmediato en GP Mensajes al aprobarse una factura | Configura el encargado en **Inventario → Almacenes → Editar** |

---

## 🛠️ Reto Práctico del Estudiante (25 min)

1. Abre **Inventario → Kardex**, selecciona el artículo que vendiste en el Módulo 2 y compraste en el Módulo 3. Anota su costo promedio actual y comprueba que ambos movimientos aparecen enlazados a sus documentos.
2. Pulsa **«Transferir»** (arriba a la derecha) y mueve **2 unidades** de un artículo desde el Almacén Principal a otro almacén.
3. Ve a **Notas de despacho → Nueva nota de despacho**, elige motivo **Muestra**, selecciona 1 unidad, escribe tu nombre como **Solicitante**, guarda, revisa el PDF (leyenda *Sin derecho a crédito fiscal*) y pulsa **«Marcar despachada»**.
4. Entra a **Órdenes de compra** y pulsa **«Generar por faltantes»** para observar cómo el sistema propone reposiciones por proveedor.

---

## 📌 Chuleta Rápida (1 minuto)
- **Algo no cuadra en stock:** Mira primero **Inventario → Kardex**.
- **Stock migrado en cero costo:** Usa **Inventario → Costo inicial** antes de comprar.
- **Mover entre almacenes:** **Transferir** (0 asientos). **Merma/conteo:** **Ajustar existencia** (sí contabiliza).
- **Salidas sin venta (muestras/donaciones):** **Notas de despacho** con **Solicitante** obligatorio.
