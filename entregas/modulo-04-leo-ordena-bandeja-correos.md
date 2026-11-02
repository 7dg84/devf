# Entrega · Proyecto Clase 4 · Leo ordena su bandeja de correos y prepara respuestas base

Rol: Leo (Atención a clientes, Tienda Pino Real).  
Fecha de trabajo en el caso: Lunes 19 de octubre.

---

## 1. Tu proceso

Para estructurar la bandeja de entrada de Tienda Pino Real sin procesar cada correo desde cero, definí un flujo de 4 pasos con el asistente de IA:

1. **Paso 1: Extracción de datos clave (Tarea: Extraer)**  
   *Por qué:* Cada correo contiene datos estructurados y dispersos (nombre del cliente, número de pedido, fecha de compra o recepción, producto involucrado y solicitud). Pedí extraer exclusivamente estos campos en formato estructurado sin suponer información faltante para validar contra las políticas de negocio.
2. **Paso 2: Clasificación y priorización (Tarea: Clasificar)**  
   *Por qué:* Agrupar los correos en un conjunto acotado de categorías operativas (entre 3 y 6) y asignar niveles de urgencia (Alta, Media, Normal) basados en plazos críticos de la tienda (cancelaciones antes de despacho, mención de autoridades, plazos de garantía de 3 días para daños).
3. **Paso 3: Redacción de plantillas base parametrizadas (Tarea: Redactar)**  
   *Por qué:* Generar respuestas profesionales, empáticas y apegadas a las políticas oficiales para cada categoría estándar, dejando variables entre corchetes (`[nombre]`, `[estatus]`, `[número de guía]`) para que el operador complete los datos reales del sistema interno.
4. **Paso 4: Filtrado de excepciones humanas (Tarea: Clasificar / Evaluar)**  
   *Por qué:* Identificar aquellos correos que por política corporativa (mención de Profeco, alta hostilidad o ambigüedad) no deben responderse con plantillas automáticas y deben escalarse a supervisión.

---

## 2. Tu clasificación

Definí 4 categorías de atención:
1. **Atención Crítica / Escalación a Supervisión:** Riesgos legales, cancelaciones inmediatas antes de salida o casos sin trazabilidad.
2. **Incidencias de Producto y Devoluciones:** Daños físicos, piezas faltantes o cambios de mercancía.
3. **Administración y Pagos:** Cobros duplicados y solicitudes de facturación.
4. **Consultas de Envío y Preventa:** Rastreo de paquetes e información previa a la compra.

### Tabla de los 10 correos

| Correo | Remitente y Pedido | Categoría | Urgencia | Razón |
|---|---|---|---|---|
| **1** | Patricia Lara · Pedido 48213 | Consultas de Envío y Preventa | Normal | Pregunta por estatus de envío a Guadalajara tras compra el 7 de oct; dentro de tiempos normales de respuesta (24 h hábiles). |
| **2** | Héctor Mendoza · Pedido 48377 | Incidencias de Producto y Devoluciones | Alta | Horno recibido dañado ayer; reporta dentro del plazo de 3 días naturales y adjuntó fotos para reposición sin costo. |
| **3** | Daniela Ortiz · Pedido 47902 | Administración y Pagos | Normal | Solicita factura de compra del 28 de septiembre; compra fuera del mes calendario en curso (octubre). |
| **4** | Julián Ramos · Pedido 48401 | Incidencias de Producto y Devoluciones | Media | Solicita cambio de color de sábanas recibidas el viernes; dentro del plazo de 15 días naturales y sin abrir. |
| **5** | Silvia Cortés · Pedido 48120 | Atención Crítica / Escalación | **Alta (Inmediata)** | Amenaza con queja ante Profeco y redes tras falta de respuesta previa; por política debe atenderlo Marcela Reyes hoy mismo. *(Podría catalogarse como envío, pero la amenaza legal domina).* |
| **6** | Andrés Beltrán · Sin pedido | Consultas de Envío y Preventa | Normal | Consulta de preventa sobre existencia de cafetera roja y tiempos de entrega a Mérida (5 a 8 días hábiles). |
| **7** | Fernanda Ibarra · Pedido 48455 | Administración y Pagos | Alta | Cobro duplicado por $1,890 reportado al día siguiente; requiere revisión de 2 días hábiles y devolución bancaria. |
| **8** | Rodrigo Salinas · Pedido 48460 | Atención Crítica / Escalación | **Alta (Inmediata)** | Cancelación por error de dirección solicitada la misma mañana; solo procede si el pedido aún no sale del almacén. *(Podría ser administración, pero la urgencia logística lo vuelve crítico).* |
| **9** | Lucía Vargas · Pedido 48390 | Incidencias de Producto / Administración | Media | **Correo híbrido:** Solicita factura de compra del 12 de oct (en mes vigente) y reporta tornillos faltantes recibidos el jueves 15 oct (al límite del plazo de 3 días naturales). |
| **10** | Mauricio Duarte · Sin pedido | Atención Crítica / Escalación | Alta | Exige devolución y cese de contacto con hostilidad sin aportar número de pedido ni contexto; requiere mediación humana directa. |

---

## 3. Tus respuestas base

### Categoría 1: Consultas de Envío y Preventa
```text
Hola, [nombre]:

Gracias por comunicarte con Tienda Pino Real.

[Para rastreo de pedido:]
Te confirmamos que estamos revisando el estado de tu pedido [número de pedido]. Te recordamos que nuestros tiempos de entrega son de 3 a 5 días hábiles en ciudades principales y de 5 a 8 días hábiles en el resto del país. El estatus actual de tu envío es: [estatus del pedido / número de guía]. Puedes rastrearlo en tiempo real aquí: [enlace de rastreo].

[Para preventa y disponibilidad:]
Con gusto te informamos que [disponibilidad del producto en color/modelo]. Si realizas tu compra hoy, el tiempo estimado de entrega para [ciudad/código postal] es de [3 a 5 días hábiles / 5 a 8 días hábiles].

Quedamos atentos a cualquier duda adicional.

Saludos cordiales,
Leo · Atención a Clientes, Tienda Pino Real
Horario de atención: Lunes a viernes de 9:00 a 18:00
```

### Categoría 2: Incidencias de Producto y Devoluciones
```text
Hola, [nombre]:

Lamentamos mucho los inconvenientes con tu pedido [número de pedido].

[Para producto dañado o piezas faltantes dentro de 3 días naturales:]
Hemos recibido tu reporte junto con las fotos correspondientes. De acuerdo con nuestra garantía, programaremos la reposición sin costo de [producto o pieza faltante]. En un plazo de [número de horas/días] te enviaremos la confirmación del nuevo envío y su número de guía.

[Para cambios o devoluciones por preferencia dentro de 15 días naturales:]
Te confirmamos que tu solicitud de cambio/devolución procede, ya que el producto está sin uso y en su empaque original dentro de los 15 días naturales posteriores a la entrega. Los pasos a seguir son:
1. Empaca el producto en su caja original.
2. Utiliza la guía de paquetería prepagada adjunta: [enlace o archivo de guía].
3. Una vez que el producto llegue a nuestro almacén, [se procesará el cambio por el artículo deseado / se gestionará tu reembolso, el cual toma de 5 a 7 días hábiles].

Quedamos a tu disposición para dar seguimiento continuo a tu caso.

Atentamente,
Leo · Atención a Clientes, Tienda Pino Real
```

### Categoría 3: Administración y Pagos (Facturación y Cobros)
```text
Hola, [nombre]:

Gracias por contactar al departamento administrativo de Tienda Pino Real.

[Para facturación dentro del mes de compra:]
Hemos recibido tus datos fiscales para el pedido [número de pedido]. Tu factura electrónica (archivos PDF y XML) será emitida y enviada a este correo en un plazo no mayor a [plazo, ej. 24 a 48 horas hábiles].

[Para facturación fuera del mes de compra:]
Lamentamos informarte que, conforme a nuestras políticas fiscales y de facturación vigentes, las facturas solo pueden emitirse durante el mismo mes en que se realizó la compra. Debido a que tu compra se efectuó el [fecha de compra, ej. 28 de septiembre], ya no es posible generar el comprobante fiscal en el mes actual. Agradecemos tu comprensión.

[Para aclaración de cobro duplicado:]
Hemos registrado tu aclaración por el cobro duplicado en el pedido [número de pedido] correspondiente a la tarjeta con terminación [últimos 4 dígitos]. Conforme a nuestras políticas, el área administrativa revisará el cargo en un máximo de 2 días hábiles. Una vez confirmado, tu banco reflejará la devolución en un lapso de 3 a 5 días hábiles. Te recordamos que por tu seguridad nunca te solicitaremos números completos de tarjeta ni códigos de seguridad.

Atentamente,
Leo · Atención a Clientes, Tienda Pino Real
```

---

## 4. Lo que no resuelve una respuesta base

Los siguientes casos deben ser derivados a una persona y **no** responderse con plantilla automática:

1. **Correo 5 (Silvia Cortés):**  
   *Por qué:* Menciona explícitamente una queja ante Profeco, difusión negativa en redes sociales y señala haber enviado tres correos sin respuesta previa. La política de Tienda Pino Real estipula con claridad: *"Quejas formales o mención de autoridades las atiende la supervisora, Marcela Reyes, el mismo día. No se contestan con respuesta base"*. Se escala de inmediato a Marcela Reyes con el historial previo.
2. **Correo 8 (Rodrigo Salinas):**  
   *Por qué:* Solicita cancelar un pedido realizado esa misma mañana debido a un error en la dirección. Las cancelaciones solo son válidas si el producto aún no abandona el almacén. Una respuesta base demoraría la gestión; requiere que un operador contacte inmediatamente al almacén por canal interno para detener el despacho antes de generar la guía física.
3. **Correo 10 (Mauricio Duarte):**  
   *Por qué:* Mensaje sin asunto, cargado de enojo, exigiendo devolución sin indicar número de pedido, correo registrado ni motivo. Una plantilla automatizada generaría mayor fricción y molestia. Debe responderlo un ejecutivo de soporte capacitado en desescalamiento para solicitar amablemente el número de orden o rastrear su cuenta por correo.

---

## 5. Tu revisión

Al comparar las respuestas generadas en la primera versión contra las políticas oficiales de Tienda Pino Real detecté y corregí los siguientes errores concretos:

1. **Error en facturación (Correo 3):** El asistente inicialmente redactó una respuesta aceptando emitir la factura para Daniela Ortiz con su RFC. Al revisar la política (*"Facturas solo durante el mes de la compra. Pasado el mes, ya no se pueden emitir"*), detecté que la compra fue el 28 de septiembre y hoy es 19 de octubre. Corregí la respuesta para explicar con respeto la imposibilidad fiscal de emitirla fuera de mes.
2. **Promesa excesiva en tiempos de envío (Correo 6):** El asistente indicaba entrega en 3 a 5 días para Mérida. Corregí el plazo a 5 a 8 días hábiles, dado que Mérida no es ciudad principal según la clasificación de cobertura nacional.
3. **Seguridad de datos (Correo 7):** El borrador inicial pedía *"adjuntar el comprobante con los datos completos de pago"*. Lo corregí para respetar la política estricta de seguridad: nunca solicitar números completos de tarjeta, NIP ni CVV, limitándose a validar con los últimos 4 dígitos ya provistos.
