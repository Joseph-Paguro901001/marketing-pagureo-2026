# 13 | Shopify, Trigger Links y Atribucion

**Estado:** 13 Trigger Links documentados como creados y verificados individualmente el 31 de julio de 2026: ocho de ficha y cinco de checkout. Requiere prueba actual antes de trafico.  
**Relacion:** [catalogo](03-CATALOGO-OFERTA-Y-REGLAS-COMERCIALES.md) | [workflows](10-WORKFLOWS-Y-AUTOMATIZACIONES.md).

## Principio de medicion

Conversation AI no comparte URLs directas de Shopify. Comparte exclusivamente enlaces internos rastreables de GHL que llevan a Shopify. Asi se puede atribuir el interes por producto y distinguir entre explorar una ficha y abrir un checkout.

Los IDs tecnicos de los Trigger Links no se incluyen en este dossier. El sistema los conserva dentro de GHL y se verifican en el readback tecnico previo a lanzamiento.

## Dos eventos comerciales distintos

| Evento | Que significa | Uso comercial |
|---|---|---|
| `product_view` | El lead abrio una ficha de producto | Mide exploracion e interes por referencia. Puede mover oportunidad a `Enviado a tienda`. |
| `checkout_open` | El lead abrio una ruta de checkout | Mide intencion de compra. Puede mover oportunidad a `Checkout pendiente`. |

Abrir una ficha no equivale a querer comprar. Abrir checkout tampoco equivale a venta. Solo una compra confirmada desde fuente valida mueve el caso a Ganado.

## Mapa funcional de enlaces

| Producto | Ficha rastreable | Checkout rastreable | Estado comercial del snapshot |
|---|---|---|---|
| Sillón reclinable azul oscuro | Si | Si | Disponible publicamente; revalidar. |
| Sillón reclinable naranja | Si | Si | Disponible publicamente; revalidar. |
| Sillón reclinable crema en lino | Si | Si | Disponible publicamente; revalidar. |
| Sillón reclinable gris | Si | Si | Disponible publicamente; revalidar. |
| Escritorio ergonomico multifuncional | Si | Si | Disponible publicamente; revalidar. |
| Escritorio gamer ergonomico | Si | No | Agotado en snapshot; no enviar compra directa. |
| Escritorio elevable electrico | Si | No | Agotado en snapshot; no enviar compra directa. |
| Silla ergonomica acolchada | Si | No | Agotada en snapshot; no enviar compra directa. |

La fase activa prioriza los cuatro sillones. Los productos adicionales permanecen documentados para no confundir la capacidad de tracking con una autorizacion de venta.

## Regla previa a cada checkout

Antes de entregar un checkout, la IA o el proceso deterministico debe confirmar:

1. producto correcto;
2. variante/color correcto;
3. precio publico actual;
4. disponibilidad publica o confirmada;
5. intencion de compra de una unidad;
6. ciudad y ruta de pago si son necesarias para el siguiente paso.

Si falta cualquiera de estas condiciones, se comparte la ficha rastreable o se escala a un asesor. Nunca se entrega checkout para un producto agotado o una variante no confirmada.

## UTMs y atribucion

Los destinos se documentaron con una estructura de UTM coherente:

```text
utm_source=ghl
utm_medium=whatsapp_ai
utm_campaign=pagureo_ecommerce
utm_content=ficha_o_checkout_por_producto
```

Los anuncios Meta usan su propio origen de pauta. El objetivo es poder leer el recorrido completo: anuncio -> formulario/WhatsApp -> contacto GHL -> Trigger Link -> ficha/checkout Shopify -> compra.

## Dependencia tecnica conocida

En una prueba interna documentada, Conversation AI respondio correctamente el contexto comercial pero GHL retiro un Trigger Link insertado libremente en el mensaje. El selector oficial de Trigger Links si genero la ruta rastreable y Shopify abrio el checkout correcto, con clics registrados.

Por esta razon, el checkout debe entregarse mediante el mecanismo oficial y deterministico que GHL soporte, no como texto libre generado por la IA. La definicion exacta se prueba con un contacto interno antes de que la IA atienda leads reales.

## Pendientes de Shopify

- Revalidar productos, variantes, precios, inventario, imagenes y enlaces.
- Confirmar eventos de compra y si llegan a GHL.
- Verificar que `product_view` y `checkout_open` actualizan el dato correcto sin crear oportunidades duplicadas.
- Confirmar si existe integracion confiable de carrito abandonado. No activar esa automatizacion sin evento comprobado.
- Probar un checkout por cada color con contacto interno autorizado.

