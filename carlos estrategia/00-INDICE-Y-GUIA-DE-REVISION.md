# PAGUREO | Dossier Integral para Revision de Joseph

**Fecha del paquete:** 27 de agosto de 2026  
**Alcance:** venta directa de productos PAGUREO. Pagurai no hace parte de esta fase.  
**Nombre canonico del proyecto:** `PAGUREO`.

## Objetivo de este dossier

Este paquete permite revisar y aprobar, por bloques, la estrategia comercial de PAGUREO antes de activar trafico, automatizaciones o envios. Reune la version vigente de la campana, el formulario, la experiencia conversacional, el CRM, los seguimientos y el plan de lanzamiento.

No contiene secretos, tokens, IDs privados, datos de pruebas, datos bancarios ni transcripciones completas. Los acuerdos de reuniones se presentan como decisiones trazables.

## Como leerlo

1. Empiece por [01 - Resumen ejecutivo](01-RESUMEN-EJECUTIVO-DE-LA-ESTRATEGIA.md).
2. Revise y apruebe la oferta y sus limites en [03 - Catalogo y reglas comerciales](03-CATALOGO-OFERTA-Y-REGLAS-COMERCIALES.md).
3. Apruebe lo que vera el cliente: [05 - Anuncios](05-ADS-COPIES-Y-MATRIZ-DE-CREATIVOS.md), [06 - Formulario](06-FORMULARIO-META-Y-ARQUITECTURA-DE-CALIFICACION.md), [11 - WhatsApp](11-PLANTILLAS-WHATSAPP-Y-SEGUIMIENTO.md) y [12 - Emails](12-EMAILS-DE-SEGUIMIENTO.md).
4. Revise la operacion que ocurre despues del registro: [07 - Funnel](07-FUNNEL-COMERCIAL-Y-EXPERIENCIA-DEL-LEAD.md), [08 - Conversation AI](08-CONVERSATION-AI-ENTRENAMIENTO-Y-BASE-DE-CONOCIMIENTO.md), [09 - CRM](09-CRM-CAMPOS-TAGS-PIPELINE-Y-DATOS.md) y [10 - Workflows](10-WORKFLOWS-Y-AUTOMATIZACIONES.md).
5. Cierre con [14 - Pruebas y lanzamiento](14-PRUEBAS-APROBACIONES-Y-LANZAMIENTO.md) y [15 - Estado y siguientes pasos](15-ESTADO-ACTUAL-DECISIONES-Y-SIGUIENTES-PASOS.md).

## Leyenda de estados

| Estado | Significado |
|---|---|
| **Configurado** | Existe evidencia local o readback documentado de que se creo o sincronizo. La vigencia actual se confirma antes de activar trafico. |
| **En borrador** | El diseno esta listo para revision o carga, pero no debe operar todavia. |
| **Requiere verificacion** | Depende de una lectura actual de plataforma, una condicion comercial, una aprobacion o una prueba interna. |
| **Fuera de alcance** | No pertenece a la fase activa de PAGUREO; se menciona solo para prevenir una confusion. |

## Mapa del paquete

| Documento | Que permite revisar | Estado predominante |
|---|---|---|
| [01](01-RESUMEN-EJECUTIVO-DE-LA-ESTRATEGIA.md) | Objetivo, embudo y limites comerciales | Estrategia vigente |
| [02](02-INVESTIGACION-DE-MERCADO-Y-CLIENTE-IDEAL.md) | Cliente ideal, dolores, deseos y objeciones | Estrategia vigente |
| [03](03-CATALOGO-OFERTA-Y-REGLAS-COMERCIALES.md) | Productos, precio observado, Addi y claims | Requiere verificacion antes de lanzar |
| [04](04-ESTRATEGIA-DE-CAMPANA-META.md) | Presupuesto, pruebas, UTMs y medicion | En borrador |
| [05](05-ADS-COPIES-Y-MATRIZ-DE-CREATIVOS.md) | Diez anuncios y guia creativa | En borrador |
| [06](06-FORMULARIO-META-Y-ARQUITECTURA-DE-CALIFICACION.md) | Formulario de alta intencion y campos | Configurado segun reporte; mapeo por verificar |
| [07](07-FUNNEL-COMERCIAL-Y-EXPERIENCIA-DEL-LEAD.md) | Recorrido del lead y momentos de escalamiento | Estrategia vigente |
| [08](08-CONVERSATION-AI-ENTRENAMIENTO-Y-BASE-DE-CONOCIMIENTO.md) | Entrenamiento, segmentacion y controles de IA | Configurado segun readback documentado |
| [09](09-CRM-CAMPOS-TAGS-PIPELINE-Y-DATOS.md) | Pipeline, campos, tags y separacion de datos | Parcialmente configurado; requiere readback |
| [10](10-WORKFLOWS-Y-AUTOMATIZACIONES.md) | Cadencia, handoff y atribucion | En borrador / dependiente de validacion |
| [11](11-PLANTILLAS-WHATSAPP-Y-SEGUIMIENTO.md) | Cinco Utility y seis Marketing | En borrador para Meta |
| [12](12-EMAILS-DE-SEGUIMIENTO.md) | Siete correos, CTA y activos | Configurado segun readback documentado |
| [13](13-SHOPIFY-TRIGGER-LINKS-Y-ATRIBUCION.md) | Clicks rastreables y reglas de checkout | Configurado segun snapshot; requiere prueba |
| [14](14-PRUEBAS-APROBACIONES-Y-LANZAMIENTO.md) | Calidad, autorizaciones y salida a trafico | Pendiente de ejecucion |
| [15](15-ESTADO-ACTUAL-DECISIONES-Y-SIGUIENTES-PASOS.md) | Decisiones que debe tomar Joseph | Requiere aprobacion |

## Decisiones tomadas que guian todo el sistema

- La fase activa es **PAGUREO para venta directa**; Pagurai queda fuera de alcance.
- El embudo principal es `Meta Ads -> Meta Lead Form -> GHL -> WhatsApp IA -> Shopify`.
- La primera validacion se concentra en Bogota, con prioridad inicial en Bogota Norte; la cobertura real debe confirmarse antes de prometerla.
- El presupuesto de trabajo inicial documentado es COP 2.000.000 mensuales, equivalente a aproximadamente COP 66.000 diarios durante 30 dias.
- La inversion inicial se distribuye 60% a producto directo y 40% a dolores de trabajo remoto. Retargeting entra solo cuando exista audiencia suficiente.
- El lead responde tres preguntas en Meta y la IA completa solo los datos faltantes: ciudad/zona, plazo de compra y forma de pago.
- La IA conversa y califica; los workflows administran ingreso, consentimiento, cadencia, handoff y medicion. No se usaran workflows para simular una conversacion que debe manejar Conversation AI.
- Cada enlace hacia ficha o checkout debe ser un Trigger Link interno rastreable, nunca una URL directa compartida libremente.
- Addi se comunica unicamente como financiacion **desde 0% de interes**, sujeta a aprobacion y condiciones vigentes.

## Decisiones que necesita confirmar Joseph

1. Precio publico, precio comparativo, oferta de la semana y su vigencia real antes de activar anuncios.
2. Inventario y disponibilidad por color el dia de lanzamiento.
3. Alcance de entrega, costos, tiempos y ciudades cubiertas.
4. Duracion y condiciones reales de la garantia del fabricante.
5. Condiciones vigentes de Addi y que producto(s) califican.
6. Politica comercial de descuentos, compras multiples y negociaciones.
7. Responsable humano de escalamiento, horario de atencion y SLA de cinco minutos.
8. Remitente, dominio, footer legal y permisos para los correos.
9. Aprobacion final de artes, anuncios, formulario, plantillas y secuencia de email.
10. Autorizacion separada para publicar workflows, enviar mensajes y activar gasto.

## Registro de fuentes y jerarquia

| Nivel | Fuente | Uso permitido en este dossier |
|---|---|---|
| 1 | Snapshot de Shopify y catalogo maestro del 31 de julio de 2026 | Producto, precio observado, disponibilidad publica y rutas de compra. Revalidar antes de lanzar. |
| 2 | Politicas y condiciones comerciales confirmadas por PAGUREO | Addi, garantia, oferta, logistica, devoluciones y excepciones. |
| 3 | Evidencia y blueprints de GHL | Campos, tags, pipeline, prompts, enlaces rastreables y drafts. |
| 4 | Reuniones Fathom del 9 y 24 de julio de 2026 | Decisiones, responsables, alcance y criterios; no precios actuales. |
| 5 | FigJam, artes y carpeta de marketing | Mensaje, concepto creativo, tono y activos visuales. |
| 6 | Chats, guiones y FAQs | Lenguaje, objeciones y entrenamiento conversacional; no datos comerciales si contradicen niveles superiores. |

Las transcripciones completas no forman parte del paquete. La trazabilidad de cada decision que puede cambiar se conserva por fuente y fecha dentro del documento correspondiente.

