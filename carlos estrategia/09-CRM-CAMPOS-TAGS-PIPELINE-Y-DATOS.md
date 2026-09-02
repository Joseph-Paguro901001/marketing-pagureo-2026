# 09 | CRM, Campos, Tags, Pipeline y Datos

**Estado:** blueprint operativo. Los elementos creados en GHL requieren readback actual antes de declarar el sistema listo para trafico.  
**Relacion:** [formulario](06-FORMULARIO-META-Y-ARQUITECTURA-DE-CALIFICACION.md) | [IA](08-CONVERSATION-AI-ENTRENAMIENTO-Y-BASE-DE-CONOCIMIENTO.md) | [workflows](10-WORKFLOWS-Y-AUTOMATIZACIONES.md).

## Principio de separacion

PAGUREO y Pagurai pueden vivir en la misma subcuenta, pero no comparten pipeline, base de conocimiento, workflow, mensajes o logica comercial. Todo elemento que pueda ejecutarse debe tener `brand_pagureo` y el pipeline de PAGUREO como condicion explicita.

Pagurai esta **fuera de alcance** de este dossier y no debe recibir datos de leads PAGUREO.

## Pipeline PAGUREO | Ventas Ecommerce

| Etapa | Cuando entra | Objetivo |
|---|---|---|
| Nuevo lead Meta | Se recibe el formulario | Registrar origen y contexto inicial. |
| WhatsApp pendiente | Espera confirmacion Utility o respuesta | Abrir la ventana de atencion sin duplicar mensajes. |
| En conversacion IA | El lead responde | Resolver duda, completar campos y orientar siguiente paso. |
| Calificado | Hay informacion suficiente e intencion identificada | Preparar ficha, checkout o asesor. |
| Enviado a tienda | Clic rastreable a ficha | Medir exploracion de producto. |
| Checkout pendiente | Clic rastreable a checkout | Medir intencion de compra y resolver friccion real. |
| Ganado | Compra confirmada por fuente valida | Cerrar atribucion y detener seguimiento. |
| Seguimiento | No compro, no respondio o debe retomar | Cerrar cadencia activa y dejar contexto para futuro. |
| No calificado | No corresponde a catalogo, cobertura o necesidad | Evitar insistencia y preservar motivo. |

No se mueve una oportunidad a Ganado por un mensaje, promesa de pago o comprobante no validado.

## Tags

| Tipo | Tag propuesto | Funcion |
|---|---|---|
| Marca | `brand_pagureo` | Guarda obligatoria para cada workflow PAGUREO. |
| Fuente | `source_meta_form` | Identifica registro desde formulario Meta. |
| Fuente | `source_click_to_whatsapp` | Identifica conversacion directa desde anuncio. |
| Consentimiento | `consent_whatsapp` | Evidencia operativa de autorizacion aplicable. |
| Consentimiento | `consent_email` | Evidencia operativa para email, cuando aplique. |
| Handoff | `handoff_human` | Detiene cadencia y deja caso para asesor. |
| Baja | `wa_optout` | Bloquea futuras plantillas de WhatsApp. |
| Cierre | `purchase_confirmed` | Detiene cadencias tras compra valida. |

Los tags no reemplazan DND nativo. Antes de enviar un WhatsApp o email, el workflow valida consentimiento, DND, opt-out y estado de conversacion.

## Campos de entrada Meta

| Campo visible | Tipo obligatorio | Fuente | Escribe IA? |
|---|---|---|---|
| Perfil de uso | TEXT | Pregunta 1 de Meta o Bot Goal | Si, si esta vacio o el contacto corrige. |
| Dolor principal del espacio | TEXT | Pregunta 2 de Meta o Bot Goal | Si, si esta vacio o el contacto corrige. |
| Etapa de decision | TEXT | Pregunta 3 de Meta o Bot Goal | Si, si esta vacio o el contacto corrige. |

## Campos comerciales editables por Conversation AI

| Campo | Tipo obligatorio | Contenido esperado | Escribe IA? |
|---|---|---|---|
| Producto | TEXT | Producto y color en una frase. | Si |
| Ciudad | TEXT | Ciudad o zona declarada. | Si |
| Plazo | TEXT | Momento de compra expresado. | Si |
| Pago preferido | TEXT | Shopify/tarjeta, Addi, transferencia u opcion explicita. | Si |
| Ultimo estado IA | TEXT | Estado controlado: conversacion, clic o escalamiento. | Si, por regla del agente/workflow |

**Regla permanente:** no crear estos campos como single option, dropdown, seleccion multiple o enumeracion. Conversation AI y Bot Goals deben poder escribir texto libre. La estandarizacion se logra con instrucciones, no bloqueando la capacidad de editar.

## Datos de atribucion y control

El CRM debe conservar, cuando los sistemas lo entreguen:

- origen, campana, conjunto, anuncio y formulario;
- producto, ciudad, intencion, pago y motivo de perdida;
- enlace de Shopify enviado y tipo de clic;
- respuesta, handoff, baja, DND, compra y fecha de ultimo contacto.

Los IDs privados de Meta, GHL y Shopify no son necesarios para la revision comercial y no se incluyen aqui.

## Permisos de escritura

| Actor | Puede escribir | No puede escribir o confirmar |
|---|---|---|
| Meta | Datos de contacto y respuestas del formulario | Inventario, pagos, compra o condiciones comerciales. |
| Conversation AI | Campos TEXT, contexto e intencion claramente declarada | Precio/inventario inventado, compra confirmada, datos sensibles o cambios de marca. |
| Workflow | Tags, oportunidad, tareas y estados operativos definidos | Respuestas de chat, negociaciones, checkout libre o compra sin evento. |
| Asesor humano | Condiciones excepcionales y cierre validado | No debe borrar trazabilidad de origen o consentimiento. |

