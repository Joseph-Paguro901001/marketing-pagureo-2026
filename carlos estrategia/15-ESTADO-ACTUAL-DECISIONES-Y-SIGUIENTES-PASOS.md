# 15 | Estado Actual, Decisiones y Siguientes Pasos

**Fecha de corte:** 27 de agosto de 2026.  
**Proposito:** permitir una aprobacion por bloques sin confundir un borrador local con una accion activa.  
**Relacion:** volver al [indice](00-INDICE-Y-GUIA-DE-REVISION.md) | ejecutar [pruebas](14-PRUEBAS-APROBACIONES-Y-LANZAMIENTO.md).

## Que esta configurado segun evidencia local o readback documentado

| Componente | Estado | Evidencia resumida | Limite actual |
|---|---|---|---|
| Conversation AI PAGUREO | **Configurado** | Prompt v6 sincronizado el 13 de agosto; agente documentado en Auto-Pilot/WhatsApp durante pruebas internas. | Requiere pruebas funcionales antes de leads reales. |
| Base de conocimiento PAGUREO | **Configurado** | KB y FAQs documentadas; catalogo/guiones disponibles como fuente. | Precio, stock, oferta y politicas deben revalidarse. |
| Trigger Links | **Configurado** | 13 enlaces documentados: 8 fichas y 5 checkouts. | La IA no puede insertarlos libremente; se requiere mecanismo oficial probado. |
| Emails PGR 01-07 | **Configurado** | Readback documentado del 3 de agosto: nombre, asunto, preview, HTML y CTA. | Verificar estado actual, remitente, footer y links antes de envio. |
| Formulario Meta | **Configurado segun reporte** | Carlos reporto envio/publicacion del 3 de agosto. | Falta readback de Meta y mapeo real a GHL. |
| Pipeline, tags y campos Fase GHL-1 | **Configurado segun registros historicos** | Existen registros de creacion; algunos snapshots posteriores muestran discrepancias. | Requiere inventario actual de GHL antes de activar. |

## Que esta en borrador

| Componente | Estado | Siguiente accion |
|---|---|---|
| Diez anuncios Meta | **En borrador** | Aprobar copy, arte, precio/offer y cargar manualmente. |
| Campanas C01-C06 | **En borrador** | Confirmar presupuesto, audiencias, creativos y lote inicial. |
| Lote WhatsApp de 11 plantillas | **En borrador** | Cargar/revisar categoria y aprobar en Meta antes de uso. |
| Workflow 01 Meta Lead | **En borrador** | Confirmar trigger/campos y construir/leer canvas en GHL. |
| Workflow 02 Handoff | **En borrador** | Definir responsable humano y construir como Draft. |
| Workflow 03 Tracking clic | **En borrador** | Probar trigger y construir solo la forma que GHL soporte. |
| Carrito abandonado | **Fuera de alcance por ahora** | Esperar evento Shopify validado. |

Existen cinco artefactos historicos `AI-T3` de checkout en Draft y sin inscritos. No pertenecen al lanzamiento; no se publican ni se reutilizan porque mezclan respuestas automaticas dentro del chat. Conversation AI conserva la conversacion y el mecanismo oficial conserva el enlace rastreable.

## Riesgos y contradicciones que no deben convertirse en promesa

- El precio publico y comparativo deben leerse de Shopify el dia de publicar. Las reuniones mencionan tickets historicos distintos.
- La garantia puede mencionarse como garantia del fabricante solo si la ficha/politica la confirma; la duracion de un ano requiere confirmacion expresa.
- Inventario por color no equivale a unidades disponibles. No usar "ultimas unidades" sin dato actual.
- Addi no permite prometer aprobacion, cupo, cuota, plazo o elegibilidad. La condicion "desde 0%" sigue sujeta a reglas vigentes.
- Entrega, cobertura, envio, devolucion y transferencia requieren fuente comercial actual y proceso humano validado.
- La prueba previa muestra que Conversation AI puede perder un Trigger Link escrito libremente; no se usa ese metodo para compartir checkout.

## Decisiones que Joseph debe responder

| Decision | Respuesta requerida | Responsable |
|---|---|---|
| Precio y comparativo | Valor publico, comparativo si aplica y vigencia | Joseph |
| Oferta semanal | Condicion exacta, fechas, productos y aprobacion | Joseph |
| Inventario | Disponibilidad real por color y alternativas | Joseph / operacion |
| Addi | Productos elegibles, mensaje autorizado y flujo de aplicacion | Joseph / comercial |
| Garantia y logistica | Duracion, exclusiones, ciudades, costos y tiempos | Joseph / operacion |
| Descuentos | Cuando puede negociar la IA y cuando escala | Joseph |
| Handoff | Nombre/horario del asesor y SLA de respuesta | Joseph |
| Meta | Aprobacion de los cinco anuncios iniciales, formulario y presupuesto | Joseph |
| WhatsApp/email | Aprobacion del lote, remitente y consentimiento | Joseph |
| Lanzamiento | Fecha, lote, tope de gasto y responsable de monitoreo | Joseph / Carlos |

## Orden exacto de activacion despues de la revision

1. Joseph confirma oferta, inventario, Addi, garantia, logistica, descuentos y responsable humano.
2. Se hace readback de Shopify, Meta y GHL; se corrigen contradicciones en KB, copies y formulario.
3. Se aprueban anuncios, artes, formulario, WhatsApp y emails como lotes separados.
4. Se construyen los tres workflows como Draft, con readback visual de triggers, filtros, acciones y salidas.
5. Se ejecuta lead interno y pruebas funcionales/adversariales.
6. Se obtiene autorizacion especifica para publicar workflows.
7. Se obtiene autorizacion especifica para activar gasto del lote inicial de anuncios.
8. Se monitorean las primeras 72 horas y se escalan cambios solo con evidencia.

## Matriz final de ejecucion

| Frente | Responsable primario | Dependencia | Aprobacion | Siguiente accion |
|---|---|---|---|---|
| Oferta/comercial | Joseph | Shopify y politica vigente | Joseph | Entregar confirmaciones actuales. |
| Ads y artes | Carlos / AIEAD | Aprobacion comercial | Joseph | Seleccionar cinco anuncios iniciales y artes. |
| Formulario | Carlos / AIEAD | Readback Meta -> GHL | Joseph para cambios externos | Probar los tres campos TEXT. |
| IA y KB | Carlos / AIEAD | Catalogo y politicas actualizados | Joseph para condiciones | Ejecutar pruebas internas. |
| WhatsApp | Carlos / AIEAD | Plantillas aprobadas, consentimiento y canal | Joseph / Meta | Cargar y verificar lote. |
| Email | Carlos / AIEAD | Remitente, footer y templates | Joseph para envio | Verificar 7/7 y prueba interna. |
| Workflows | Carlos / AIEAD | Datos, plantillas y responsable humano | Joseph para crear/publicar | Construir Drafts MVP. |
| Tracking | Carlos / AIEAD | Trigger Links y Shopify | Joseph para prueba de compra | Validar ficha/checkout por color. |
| Lanzamiento | Carlos + Joseph | Todo el preflight | Joseph | Autorizar fecha, gasto y monitoreo. |

## Punto de reinicio recomendado

Abrir primero este documento y recopilar las diez respuestas de Joseph. Con esas confirmaciones, continuar por [03 - Catalogo](03-CATALOGO-OFERTA-Y-REGLAS-COMERCIALES.md), [11 - WhatsApp](11-PLANTILLAS-WHATSAPP-Y-SEGUIMIENTO.md) y [14 - Pruebas](14-PRUEBAS-APROBACIONES-Y-LANZAMIENTO.md), en ese orden.

