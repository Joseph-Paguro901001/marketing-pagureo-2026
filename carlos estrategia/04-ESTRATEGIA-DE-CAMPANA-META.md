# 04 | Estrategia de Campana Meta

**Estado:** en borrador para revision comercial. No implica publicaciones ni gasto.  
**Relacion:** [anuncios](05-ADS-COPIES-Y-MATRIZ-DE-CREATIVOS.md) | [formulario](06-FORMULARIO-META-Y-ARQUITECTURA-DE-CALIFICACION.md) | [pruebas](14-PRUEBAS-APROBACIONES-Y-LANZAMIENTO.md).

## Objetivo y ventana de validacion

Generar leads que completen el formulario, respondan por WhatsApp y avancen a una ficha o checkout Shopify rastreable. La primera lectura valida el sistema durante 14 dias; la ventana comercial inicial se evalua a 30 dias.

No se busca cambiar todo de inmediato. Las primeras 48 a 72 horas sirven para confirmar entrega, tracking, calidad de lead y comportamiento inicial. Solo un error critico, un dato comercial incorrecto o un problema de consentimiento justifica una modificacion inmediata.

## Presupuesto de referencia

| Concepto | Propuesta inicial | Regla |
|---|---:|---|
| Presupuesto mensual | COP 2.000.000 | Requiere confirmacion antes de activar gasto. |
| Presupuesto diario aproximado | COP 66.000 | Ajustar al presupuesto real, sin forzar exactitud matematica. |
| Producto directo | 60% | Enfatiza producto, color, funciones y oferta vigente. |
| Dolores de trabajo remoto | 40% | Enfatiza espacio temporal, rutina estatica, presencia y pausa. |
| Retargeting | Hasta 20% | Solo cuando haya audiencia suficiente; sale del presupuesto, no se suma. |

## Arquitectura de campanas

| Campana | Proposito | Creativo recomendado | Audiencia | Estado |
|---|---|---|---|---|
| C01 Producto directo | Mostrar sillón, funciones, colores y ruta de informacion | Video de producto y foto 4:5 | Prospecting | En borrador |
| C02 Dolores de trabajo remoto | Abrir la necesidad de mejorar el espacio | Video problema-solucion y lifestyle | Prospecting | En borrador |
| C03 Educacion funcional | Demostrar reclinacion, giro y uso cotidiano | Video corto / carrusel | Prospecting | En borrador |
| C04 Diccionario A | Probar un concepto creativo de lenguaje y significado del espacio | Video/foto A | Prospecting | En borrador; requiere artes finales |
| C05 Diccionario B | Prueba A/B del concepto Diccionario | Video/foto B | Prospecting | En borrador; requiere artes finales |
| C06 Retargeting | Resolver una duda antes de decidir | Video/carrusel de objeciones | Visitantes, interaccion y formulario abierto | Condicionado a audiencia |

Los anuncios AD01 a AD10 se distribuyen entre estas campanas segun su angulo. La primera salida recomendada usa cinco anuncios priorizados: AD01, AD03, AD05, AD07 y AD09. Los demas se conservan como pruebas controladas o retargeting.

## Conjuntos y aprendizaje

### Conjunto A: producto directo

- Mensaje: funcion, diseno, color, demostracion, oferta vigente y Addi condicionado.
- Angulos: crecimiento profesional, base de operaciones, funcion, color y oportunidad.
- Objetivo: identificar personas que entienden el producto y avanzan con una duda concreta.

### Conjunto B: dolores de trabajo remoto

- Mensaje: espacio temporal, fondo de videollamadas, rutina estatica, falta de pausa y mejora cotidiana.
- Angulos: costo de seguir igual, presencia profesional, versatilidad y upgrade del entorno.
- Objetivo: abrir una conversacion con personas que aun no estan buscando el producto por nombre.

### Retargeting condicionado

- Audiencias: visitas a Shopify, interacciones de anuncios, apertura de formulario o conversacion no convertida.
- Mensaje: resolver color, medidas, funciones, disponibilidad, oferta o financiacion.
- Regla: no presionar; se usa para devolver claridad a una duda pendiente.

## Prueba de precio

Se prueban variantes con precio y sin precio unicamente despues de releer el precio actual y condiciones de oferta. La hipotesis no es que un anuncio con precio gane por volumen; puede generar menos leads, pero con mayor calidad e intencion de compra.

La variante sin precio siempre debe explicar el beneficio de llenar el formulario: recibir colores disponibles, detalles, oferta vigente y opciones de financiacion. No se debe presentar el formulario como una barrera artificial.

## Criterios de optimizacion

| Senal | Lectura | Accion posible despues de la ventana inicial |
|---|---|---|
| CTR bajo | Hook, creativo o audiencia no conectan | Cambiar angulo o primer plano creativo |
| Formulario abierto pero no completado | Intercambio de valor o friccion insuficiente | Ajustar titulo/descripcion sin romper el mapeo |
| Lead alto pero poca respuesta WhatsApp | Confirmacion o expectativa desalineada | Revisar Utility, consentimiento y primer mensaje de IA |
| Respuesta alta pero poco clic Shopify | La IA no resuelve duda o no lleva a siguiente paso | Revisar entrenamiento y contexto comercial |
| Clic a checkout sin ventas | Oferta, checkout, pago, logistica o confianza | Auditar ruta de compra antes de escalar gasto |
| Ventas con CAC aceptable | Hipotesis validada | Escalar gradualmente, conservando control de calidad |

## Convenciones de nombre y UTMs

**Campana:** `PGR_SILLON_C01_PRODUCTO_V1`  
**Conjunto:** `PGR_BOGOTA_NORTE_PRODUCTO_V1`  
**Anuncio:** `PGR_SILLON_AD01_TRABAJO_CRECIO_V1`  
**Formulario:** `PAGUREO | Sillón | Alta intención`

UTM base:

```text
utm_source=meta&utm_medium=paid_social&utm_campaign={{campaign.name}}&utm_content={{ad.name}}&utm_term={{adset.name}}
```

No se cambia el nombre de un anuncio ganador durante aprendizaje, salvo error critico. Se conserva estabilidad para que Meta, GHL y Shopify puedan leerse en conjunto.

## Matriz de medicion por etapa

| Etapa | Evento o dato | Fuente esperada |
|---|---|---|
| Anuncio | Impresion, alcance, CTR, CPM, CPC | Meta Ads |
| Formulario | Apertura, envio y respuestas de P1-P3 | Meta / GHL |
| Conversacion | Respuesta, campos completos, handoff | GHL / Conversation AI |
| Ficha | `product_view` por Trigger Link | GHL / Shopify |
| Checkout | `checkout_open` por Trigger Link | GHL / Shopify |
| Venta | Compra atribuible, CAC y ROAS | Shopify / Meta / GHL |

