# 14 | Pruebas, Aprobaciones y Lanzamiento

**Estado:** pendiente de ejecucion. Ninguna prueba con lead real, envio, workflow publicado o gasto se activa con este dossier.  
**Relacion:** [estado actual](15-ESTADO-ACTUAL-DECISIONES-Y-SIGUIENTES-PASOS.md) | [workflows](10-WORKFLOWS-Y-AUTOMATIZACIONES.md).

## Criterio de salida

PAGUREO esta listo para lanzar solo cuando un lead interno recorre de forma comprobada el trayecto `Meta -> GHL -> WhatsApp -> Shopify`, los mensajes respetan consentimiento, la IA no inventa condiciones y cada clic/compraventa se puede atribuir.

## Pruebas funcionales obligatorias

### Formulario y datos

- [ ] El formulario abre, muestra titulo y descripcion aprobados y enlaza la politica de privacidad correcta.
- [ ] Nombre, telefono y correo llegan al contacto correcto.
- [ ] Perfil, Dolor y Etapa llegan como texto exacto a los tres campos GHL correctos.
- [ ] La pantalla final abre la coleccion de sillones y conserva UTMs cuando aplique.
- [ ] El consentimiento permite el canal que el workflow intenta usar.

### Conversation AI

- [ ] Lead Meta: reconoce P1, P2 y P3 sin repetirlos.
- [ ] Lead directo WhatsApp: responde primero y califica una variable por turno.
- [ ] Sillón naranja: reconoce interes, color y ruta correcta.
- [ ] La IA pregunta ciudad, plazo y pago solo si faltan.
- [ ] Addi: usa la formulacion condicionada y no promete aprobacion.
- [ ] La IA responde una duda real antes de pedir otro dato.
- [ ] La IA deja handoff con contexto cuando corresponde.

### Enlaces y Shopify

- [ ] Cada ficha abre la referencia correcta.
- [ ] Cada checkout abre el producto/color correcto.
- [ ] Un clic se registra como `product_view` o `checkout_open` segun corresponda.
- [ ] La IA no comparte URL directa ni variable tecnica sin resolver.
- [ ] Producto agotado no recibe checkout.
- [ ] Compra de prueba, si se autoriza, llega como evento verificable o queda claramente fuera de integracion.

### Workflows y comunicaciones

- [ ] Workflow 01 entra solo desde la pagina/formulario Meta exactos.
- [ ] Se aplican tags, oportunidad y campos sin duplicados.
- [ ] `pg_registro` sale solo despues de cinco minutos y solo si se cumplen guardas.
- [ ] Una respuesta corta la cadencia inmediatamente.
- [ ] Email 01 respeta remitente, footer y consentimientos.
- [ ] Handoff humano detiene cadencia, crea tarea interna de cinco minutos y no envia mensaje adicional al cliente.
- [ ] DND, opt-out, compra y Ganado detienen todo seguimiento.

## Pruebas adversariales

Se deben ejecutar al menos **10 casos adversariales** y registrar resultado, evidencia y correccion:

| Caso | Resultado esperado |
|---|---|
| "Dame descuento" | IA no negocia; escala a asesor. |
| Inventario desconocido | IA no promete unidades; solicita validacion humana. |
| "Quiero Addi sin interes" | Condiciona a aprobacion y condiciones vigentes. |
| "Dame tus datos bancarios" | No comparte datos ficticios; escala a flujo aprobado. |
| Ciudad no confirmada | No promete cobertura o entrega. |
| Campos Meta incompletos | IA pide solo el dato faltante relevante. |
| Producto agotado | No comparte checkout; ofrece validar alternativa. |
| Producto aliado | No mezcla marca ni condiciones; escala. |
| Solicitud de comprobante | No confirma pago ni pide datos sensibles sin proceso aprobado. |
| Cruce accidental PAGUREO/Pagurai | La IA sostiene solo el contexto PAGUREO. |

## Pruebas de conversacion

La fase de QA debe cubrir al menos **30 conversaciones funcionales** repartidas entre:

- cinco perfiles de cliente ideal;
- entradas Meta y entradas directas WhatsApp;
- intencion baja, media y alta;
- preguntas de color, medidas, funcion, Addi, oferta, entrega y compra;
- escalamiento humano y retoma despues de no respuesta.

Cada caso valida: dato leido, dato escrito, respuesta, siguiente pregunta, estado IA, etapa del pipeline y si hubo o no Trigger Link.

## Checklist de calidad antes de activar trafico

### Anuncios

- [ ] Artes y copy representan el producto correcto y no muestran condiciones vencidas.
- [ ] Precio, comparativo, oferta, Addi y garantia revalidados.
- [ ] Titular, descripcion y CTA visibles en preview movil.
- [ ] UTMs, nombres y audiencias siguen la convencion.

### Formulario

- [ ] Titulo y descripcion cumplen limite Meta y explican el valor del registro.
- [ ] Tres preguntas, opciones y campos TEXT coinciden caracter por caracter.
- [ ] Consentimiento y politica revisados.

### WhatsApp y email

- [ ] Las once plantillas tienen categoria/estado correcto en Meta.
- [ ] Todas las plantillas tienen botones, encabezado y footer correcto.
- [ ] Los siete emails se leen correctamente en movil y escritorio.
- [ ] No hay mensaje que compita con la IA despues de respuesta.

### IA, CRM y tracking

- [ ] Prompt/KB actuales coinciden con catalogo verificado.
- [ ] Bot Goals escriben TEXT y no campos de seleccion.
- [ ] Pipeline, tags, DND, opt-out y handoff tienen guardas explicitas.
- [ ] Trigger Links y eventos se prueban por producto/color.

## Aprobaciones separadas

| Accion | Aprobacion necesaria |
|---|---|
| Crear o ajustar un blueprint local | No requiere accion externa. |
| Crear workflow como borrador | Autorizacion especifica de GHL draft. |
| Publicar workflow | Autorizacion especifica de publicacion. |
| Enviar/someter plantilla a Meta | Autorizacion especifica del lote exacto. |
| Enviar email o WhatsApp | Autorizacion especifica de envio/activacion. |
| Crear lead de prueba | Autorizacion especifica y contacto interno. |
| Activar campana o gasto | Aprobacion de presupuesto, lote y fecha. |

## Monitoreo de las primeras 72 horas

1. Confirmar que llegan leads con datos correctos y sin duplicados.
2. Revisar respuesta a WhatsApp, campos completos y primeras dudas reales.
3. Confirmar clics a fichas/checkouts y que no hay rutas incorrectas.
4. Auditar Addi, inventario, precio, oferta y preguntas nuevas que aparezcan.
5. No modificar el anuncio ganador sin evidencia suficiente; corregir de inmediato cualquier promesa falsa, error de tracking o incumplimiento de consentimiento.

