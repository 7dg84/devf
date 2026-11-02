# Entrega · Proyecto Clase 5 · Rosa comprueba que su asistente responde con el manual y no con lo que supone

Rol: Rosa (Operaciones, Distribuidora Valle Verde).  
Documento analizado: Manual de Procesos de Operaciones · Bodega Central · Versión 3.2 (Vigente desde el 1 de septiembre de 2026).

---

## 1. Tu prompt

```text
Eres el asistente de operaciones de la Bodega Central de Distribuidora Valle Verde y respondes consultas del personal de nuevo ingreso.

Instrucciones estrictas:
1. Responde única y exclusivamente utilizando como fuente el Manual de Procesos de Operaciones (Versión 3.2).
2. Para cada respuesta, indica obligatoriamente la sección exacta y el número de página donde se encuentra la regla.
3. Si la regla se contradice entre el cuerpo del manual y la tabla de control de cambios, aplica la regla de lectura de la Sección 1.4: manda la tabla de la Sección 11.
4. Si un dato, plazo o procedimiento NO aparece explícitamente en el manual, responde claramente: "Esta información no está en el manual" y orienta hacia el anexo o contacto correspondiente si existe.
5. No asumas, no extrapoles ni agregues información externa bajo ninguna circunstancia.
```

---

## 2. Tres preguntas de nuevo ingreso

### Pregunta 1: Tiempo máximo en andén
**Pregunta:** "¿Cuánto tiempo máximo puede estar la mercancía recibida en el andén antes de guardarse en su ubicación y qué procede si nos tardamos más?"  
**Respuesta del asistente:** La mercancía recibida no puede permanecer en el andén más de 6 horas hábiles antes de ubicarse. Si se supera ese tiempo, el supervisor de turno debe registrarlo como incidencia de tipo "retraso" en el formato OP-07. En el caso especial de producto de cámara fría, no puede esperar nada en el andén y debe ubicarse de inmediato.  
**Comprobación en el manual:**  
- **Sección y página:** Sección 2.5 ("Tiempo en andén"), página 4; y Anexo D ("Resumen de plazos y umbrales"), página 18.  
- **Resultado:** Coincide exactamente.

### Pregunta 2: Tolerancia de diferencias en recepción
**Pregunta:** "Al recibir a un proveedor, si el conteo físico no coincide con lo que dice la remisión, ¿cuál es el porcentaje de diferencia permitido y qué hacemos si falta más de eso?"  
**Respuesta del asistente:** La tolerancia permitida es de hasta el 2% por producto. En ese caso se recibe la mercancía y se anota la diferencia en el formato OP-12. Si la diferencia es mayor al 2%, se detiene la recepción de ese producto específico, el recibidor notifica al supervisor de turno, quien a su vez avisa al área de Compras. Está prohibido firmar la remisión del proveedor con diferencias mayores al 2% sin la autorización expresa de Compras.  
**Comprobación en el manual:**  
- **Sección y página:** Sección 2.3 ("Tolerancia de diferencias"), página 4; y Anexo D, página 18.  
- **Resultado:** Coincide exactamente.

### Pregunta 3: Plazo para reporte de daños por el cliente
**Pregunta:** "Si un cliente recibe producto dañado por la paquetería, ¿cuánto tiempo tiene para reportarlo y que le aplique reposición sin costo?"  
**Respuesta del asistente:** El plazo vigente es de 48 horas siguientes a la entrega, debiendo adjuntar fotografías del empaque y del producto. Pasado ese tiempo, el caso se trata como devolución normal y no como reposición por daño.  
**Comprobación en el manual:**  
- **Sección y página:** Sección 11 ("Control de cambios del manual"), página 14 (Versión 3.2 vigente desde el 1 de septiembre); contrastada con Sección 6.2 ("Plazo para reportar daños"), página 9, y Sección 1.4 ("Cómo leer este manual"), página 3.  
- **Resultado:** Coincide con la norma jerárquica del manual. Aunque la Sección 6.2 en página 9 menciona textualmente 24 horas, la nota de control de cambios de la Sección 11 en página 14 estipula que a partir de la versión 3.2 el plazo se amplió formalmente a 48 horas (pendiente de editarse en el texto corrido en la siguiente edición), y la regla de lectura de la página 3 establece que ante contradicciones manda siempre el control de cambios.

---

## 3. Pregunta de control (información fuera del manual)

**Pregunta:** "¿Cuál es el procedimiento y con cuántos días de anticipación debo solicitar mis vacaciones o un permiso de ausencia?"  
**Respuesta del asistente:** Esta información no aparece en el manual. Los procedimientos de vacaciones, permisos, nómina y contratación no están cubiertos por el Manual de Procesos de Operaciones. Para tramitarlos debes consultar directamente al área de Recursos Humanos en la extensión 2100.  
**Comportamiento del asistente:** El asistente no alucinó requisitos ni inventó días de preaviso. Identificó con precisión la exclusión formal señalada en el Anexo A ("Contactos"), página 15: *"Los temas de nómina, vacaciones y contratación no están cubiertos en este manual. Se consultan directamente con Recursos Humanos"*.

---

## 4. Tu revisión

Al contrastar exhaustivamente el manual de 20 páginas encontré una contradicción crítica entre la Sección 6.2 (página 9), que indica 24 horas para reportar daños, y la tabla de control de cambios de la Sección 11 (página 14), que amplía el plazo a 48 horas a partir de la versión 3.2 vigente. Decidí aplicar la regla prioritaria de la Sección 1.4 ("manda el control de cambios"), evitando que el asistente entregue información desactualizada al personal. Además, verifiqué que ante temas administrativos ajenos (vacaciones), el modelo restrinja su alcance y canalice a Recursos Humanos conforme al Anexo A, confirmando que la técnica RAG con instrucciones estrictas de anclaje previene eficazmente las alucinaciones.