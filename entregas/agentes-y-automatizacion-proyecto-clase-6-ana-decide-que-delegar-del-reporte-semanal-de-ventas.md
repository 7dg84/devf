# Entrega · Proyecto Clase 6 · Ana decide qué delegar del reporte semanal de ventas

Rol: Ana (Gerente de Ventas, Distribuidora Solmar).  
Caso: Consolidación y validación del reporte semanal de ventas para Dirección Comercial.  
Metas semanales: Vendedor individual = $60,000 | Equipo = $180,000.  
Horario límite de recepción: Lunes 9:00 | Entrega a Dirección: Lunes 11:00.

---

## 1. Tu flujo (Las cinco piezas de automatización)

Siguiendo la plantilla metodológica de la lectura 6.1, el flujo para consolidar las ventas semanales se estructura en cinco piezas:

1. **Disparador (Trigger):**  
   *Evento y momento exacto:* Cada lunes a las 9:15 AM (tiempo fijo, 15 minutos después del límite de recepción de las 9:00 AM para dar margen de recepción de mensajes y correos).
2. **Registro (Input / Ingesta):**  
   *Estandarización de entradas heterogéneas:* El asistente recopila y parsea las tres fuentes de entrada (tabla de hoja de cálculo de Beto, mensaje de chat de Carla y correo de Mauricio). Extrae cada movimiento a una estructura normalizada con cinco campos: `Vendedor`, `Folio`, `Cliente`, `Monto (en pesos exactos)` y `Estatus`.
3. **Decisión (Lógica de negocio y filtros):**  
   *Reglas de admisión estricta:*  
   - Una venta cuenta **únicamente** si el pedido está marcado como **Facturado** dentro de la semana evaluada.  
   - Se excluyen automáticamente pedidos con estatus *Cancelado*, *Cotización*, o *En proceso de cierre*.  
   - Detección de duplicados: Si un folio ya fue registrado para el mismo vendedor, se toma solo una vez y el segundo se descarta.  
   - Casos no resueltos automáticamente: Si una partida carece de número de folio (como ocurrió con Mauricio) o el formato de monto es ambiguo, se señala con una bandera de advertencia (*flag*) para que Ana lo valide manualmente.
4. **Respuesta (Output / Acción):**  
   *Generación de borrador interno:* A las 9:30 AM, el asistente genera un borrador consolidado en formato de reporte ejecutivo dirigido a Ana. **No se envía al Director Comercial de forma directa**; queda en la bandeja de Ana para su validación humana (*Human-in-the-loop*).
5. **Evidencia (Auditoría y trazabilidad):**  
   *Tabla de exclusiones y bitácora:* Una sección anexa en el reporte que desglosa cada partida excluida, indicando vendedor, folio/cliente, importe restado y motivo de la exclusión ($65,000 excluidos en total esta semana). Ana revisa esta evidencia cada lunes entre 9:30 y 10:30 AM antes de autorizar el envío definitivo de las 11:00 AM.

---

## 2. Lo que no delegarías y por qué

1. **El envío final del reporte al Director Comercial:**  
   *Por qué:* La responsabilidad ejecutiva ante la dirección recae en Ana. Un asistente puede equivocarse ante ambigüedades no previstas (ej. capturas en miles sin decimales o dobles capturas atípicas). Ana debe dar el visto bueno formal.
2. **La resolución de discrepancias sobre comisiones o excepciones comerciales:**  
   *Por qué:* Si un vendedor solicita que se le cuente un pedido "en proceso de cierre" porque el cliente pagará hoy, esa decisión involucra criterio de liderazgo, políticas de compensación y evaluación de riesgo comercial, aspectos que jamás deben automatizarse.
3. **La retroalimentación y plan de acción con los vendedores:**  
   *Por qué:* El reporte muestra que Mauricio alcanzó solo el 69.5% de su meta y omitió los números de folio. El diálogo para corregir hábitos de captura y apoyar el cierre de ventas requiere empatía, negociación y criterio humano.

---

## 3. Tu prueba

### Entrada provista al asistente:
- **Criterio de decisión:** Solo cuentan pedidos con estatus Facturado. Excluir cancelados, cotizaciones, en proceso y folios repetidos. Meta individual: $60,000; Meta equipo: $180,000.
- **Datos de entrada:**
  - *Beto Ríos:* F-1041 ($12,400 Facturado), F-1042 ($18,900 Facturado), F-1044 ($9,500 Cancelado), F-1045 ($27,300 Facturado).
  - *Carla Núñez:* F-2210 ($31,000), F-2211 ($22,500), F-2211 ($22,500 duplicado), F-2213 ($15,800).
  - *Mauricio Pérez:* Papelería Central (24.5 Facturado), Cafetería Roma (17.2 Facturado), Hoteles del Valle (33.0 En proceso de cierre).

### Respuesta generada por el asistente:

#### Reporte Consolidado de Ventas Semanales — Distribuidora Solmar
Semana anterior | Fecha de corte: Lunes 11:00 AM

**1. Desempeño por Vendedor:**

| Vendedor | Ventas Validadas | Meta Semanal | % Cumplimiento | Estatus |
|---|---|---|---|---|
| Carla Núñez | $69,300.00 | $60,000.00 | 115.50% | Superó meta |
| Beto Ríos | $58,600.00 | $60,000.00 | 97.67% | Cerca de meta |
| Mauricio Pérez | $41,700.00 | $60,000.00 | 69.50% | Debajo de meta |
| **Total Equipo** | **$169,600.00** | **$180,000.00** | **94.22%** | **Déficit: $10,400** |

**2. Bitácora de Exclusiones y Ajustes (Evidencia de Auditoría):**

- **Beto Ríos:**
  - Folio F-1044 (Miscelánea Norte): **-$9,500.00** excluidos por estatus *Cancelado*.
  - *Monto original reportado:* $68,100.00 → *Monto auditado:* $58,600.00.
- **Carla Núñez:**
  - Folio F-2211 (Mercado Verde): **-$22,500.00** excluidos por *Folio duplicado* (se capturó dos veces la misma venta).
  - *Monto original reportado:* $91,800.00 → *Monto auditado:* $69,300.00.
- **Mauricio Pérez:**
  - Hoteles del Valle: **-$33,000.00** excluidos por estatus *En proceso de cierre* (no facturado en la semana).
  - *Advertencia adicional:* Mauricio reportó importes en miles (24.5 y 17.2) y no proporcionó los números de folio para cruce con facturación.
  - *Monto original reportado:* $74,700.00 → *Monto auditado:* $41,700.00.

**Total Excluido del Equipo:** **$65,000.00**

---

## 4. Tu revisión

Al contrastar los reportes individuales con las reglas corporativas y la salida del asistente, encontré y corregí tres aspectos determinantes:
1. **Estandarización de formato monetario:** Mauricio reportó en miles con decimales ("24.5, 17.2, 33.0"). Fue indispensable indicarle al modelo la conversión explícita a moneda nacional ($24,500, $17,200 y $33,000) para evitar que sumara cantidades como valores literales de 24.5 pesos.
2. **Falta de folios fiscales:** Detecté que Mauricio omitió los números de folio. Decidí admitir preventivamente sus dos ventas facturadas ($41,700) pero programé una solicitud directa de los folios antes de las 10:30 AM para confirmar la factura en el ERP antes de las 11:00 AM.
3. **Impacto en comisiones y meta:** Los tres vendedores sumaban $234,600 en bruto (superando holgadamente los $180,000). Sin embargo, tras aplicar el filtro estricto de auditoría ($65,000 excluidos por cancelaciones, duplicados y falta de facturación), la cifra real es $169,600 (94.22%), lo que impidió presentar un reporte inflado y falso a la Dirección Comercial.