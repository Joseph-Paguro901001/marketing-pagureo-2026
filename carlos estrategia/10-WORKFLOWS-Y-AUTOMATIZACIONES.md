# 10 | Workflows y Automatizaciones

**Estado:** blueprints locales. El ingreso desde Meta aparece documentado como borrador; ningun workflow de este dossier debe publicarse, enviar o contactar personas sin aprobacion expresa.  
**Relacion:** [CRM](09-CRM-CAMPOS-TAGS-PIPELINE-Y-DATOS.md) | [WhatsApp](11-PLANTILLAS-WHATSAPP-Y-SEGUIMIENTO.md) | [emails](12-EMAILS-DE-SEGUIMIENTO.md).

## Principio de diseno

Conversation AI es la unica responsable de responder chats despues de una intervencion del lead. Los workflows no hacen preguntas, no negocian, no recomiendan productos ni envian checkouts libremente. Coordinan estados y envios autorizados cuando no hay conversacion activa.

## Workflow 01 | Meta Lead - Ingreso y cadencia

**Estado:** en borrador / requiere readback de trigger y canvas.  
**Objetivo:** transformar el formulario Meta en seguimiento ordenado, sin invadir una conversacion activa.

### Trigger

- Envio del Meta Lead Form final identificado por pagina y formulario exactos.
- Nunca usar `Contact Created` generico, porque puede capturar contactos ajenos a PAGUREO.
- Conservar el mapeo nativo de Perfil, Dolor y Etapa de decision.

### Bloques minimos

1. **Validar marca y consentimiento:** salir si no es PAGUREO, si existe DND, opt-out o dato de contacto invalido.
2. **Etiquetar y atribuir:** agregar `brand_pagureo` y `source_meta_form`; registrar origen/campana/anuncio si fueron entregados.
3. **Oportunidad:** crear o actualizar en `Nuevo lead Meta`, sin duplicar oportunidades.
4. **Espera controlada:** cinco minutos en zona horaria Bogota.
5. **Salida por respuesta:** habilitar "Remove from this workflow on response" antes de cualquier envio posterior.
6. **Utility de registro:** enviar `pg_registro` solo si hay consentimiento, no hay respuesta, no hay DND y la plantilla esta aprobada.
7. **Email 01:** enviar solo con email valido, consentimiento aplicable y footer/remitente verificados.
8. **Cadencia 14 dias:** alternar plantillas y emails segun la tabla siguiente; revalidar condiciones antes de cada envio.
9. **Salida final:** ante no respuesta, mover a `Seguimiento`; ante compra, cerrar; ante handoff o baja, detener.

### Cadencia definida

| Dia | WhatsApp | Email | Condicion adicional |
|---|---|---|---|
| 0 | `pg_registro` Utility | `PGR | 01 | Tu espacio empieza aqui` | Solicitud Meta y no respuesta. |
| 1 | `pg_rutina` | - | Consentimiento y sin conversacion activa. |
| 2 | - | `PGR | 02 | Tu rutina` | Email valido y sin salida. |
| 3 | `pg_color` | - | Sin compra, handoff ni baja. |
| 4 | `pg_addi` | `PGR | 03 | Color y espacio` | Addi vigente; si no, omitir o reordenar. |
| 6 | - | `PGR | 04 | Financiacion Addi` | Condiciones Addi vigentes. |
| 7 | `pg_funcion` | - | Sin respuesta reciente. |
| 8 | - | `PGR | 05 | Funciones reales` | Email valido. |
| 10 | `pg_oferta` | `PGR | 06 | Oferta y medidas` | Oferta vigente confirmada. |
| 14 | `pg_retomar` | `PGR | 07 | Retomar tu espacio` | Cierra cadencia. |

### Guardas antes de cada envio

- `brand_pagureo` presente;
- consentimiento del canal aplicable;
- DND y opt-out ausentes;
- sin respuesta nueva del contacto;
- sin `handoff_human`;
- sin compra confirmada ni oportunidad Ganado;
- email/telefono validos para el canal;
- Addi y oferta confirmados cuando el contenido los menciona.

## Workflow 02 | IA - Handoff humano

**Estado:** blueprint local.  
**Objetivo:** cuando la IA necesita ayuda humana, cortar la cadencia y dejar el caso listo para Joseph sin enviar un segundo mensaje al cliente.

### Trigger y guardas

- Trigger: cambio de `Ultimo estado IA` a `escalar_asesor`.
- Guardas: `brand_pagureo` presente y `wa_optout` ausente.
- Re-entry desactivado; un caso escalado se gestiona como caso humano.

### Bloques minimos

1. Agregar `handoff_human` si no existe.
2. Retirar de la cadencia PAGUREO activa si existe.
3. Cambiar estado de IA a `handoff_requested`.
4. Asignar el contacto al responsable comercial definido por Joseph.
5. Crear una tarea interna de cinco minutos: validar caso escalado.
6. Enviar notificacion interna con producto, ciudad, plazo, pago preferido y ultimo mensaje, sin secretos ni datos sensibles.
7. Finalizar.

No envia WhatsApp, no espera diez minutos, no escala por segunda vez y no cambia de etapa de oportunidad por fuerza.

## Workflow 03 | Tracking de clic Shopify

**Estado:** blueprint local; requiere confirmar capacidad real del trigger de GHL.  
**Objetivo:** registrar clicks de Trigger Links PAGUREO sin mensajes ni nuevas cadencias.

### Comportamiento

- Trigger: clic en Trigger Link interno de PAGUREO.
- Ficha: guardar `clicked_product_view` y mover oportunidad existente a `Enviado a tienda`.
- Checkout: guardar `clicked_checkout` y mover oportunidad existente a `Checkout pendiente`.
- Si no existe oportunidad PAGUREO, no crear una nueva solo por el clic.
- Un solo workflow puede servir si la interfaz soporta varios Trigger Links; de lo contrario se divide solo despues de probar la limitacion.

## Limites deliberados

No se crean en esta fase:

- workflows que respondan chats o hagan preguntas;
- workflows que compartan checkout sin contexto;
- carrito abandonado, compra ganada o confirmacion de pago sin eventos Shopify leidos y prueba interna;
- automatizaciones de Pagurai o cualquier workflow sin guarda de marca;
- un workflow separado de opt-out cuando GHL ya aplica DND y las guardas anteriores.

## Verificacion antes de construir o publicar

1. Revisar workflows genericos existentes para evitar reutilizacion accidental.
2. Confirmar trigger, filtros y acciones de cada canvas de PAGUREO.
3. Confirmar Page/Form Meta y los tres campos TEXT en GHL.
4. Confirmar estado de las once plantillas WhatsApp y siete emails.
5. Verificar remitente, footer legal y canal WhatsApp.
6. Probar lead interno de extremo a extremo.
7. Guardar cada workflow como `Draft` y hacer readback visual antes de pedir autorizacion de publicacion.

