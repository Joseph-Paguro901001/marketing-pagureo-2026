# 07 | Funnel Comercial y Experiencia del Lead

**Estado:** estrategia vigente. La activacion de cada envio, workflow y gasto requiere aprobacion separada.  
**Relacion:** [formulario](06-FORMULARIO-META-Y-ARQUITECTURA-DE-CALIFICACION.md) | [IA](08-CONVERSATION-AI-ENTRENAMIENTO-Y-BASE-DE-CONOCIMIENTO.md) | [workflows](10-WORKFLOWS-Y-AUTOMATIZACIONES.md).

## Principio de experiencia

Una persona no debe sentir que entro a un cuestionario. Debe sentir que PAGUREO entendio por que consulta y la ayuda a resolver la duda que le impide avanzar. La IA responde primero el mensaje real, aprovecha los datos existentes y formula una sola pregunta corta cuando necesita completar un campo.

## Ruta 1 | Meta Lead Form

```text
Anuncio Meta
  -> Formulario de alta intencion
  -> GHL crea/actualiza contacto, campos y oportunidad
  -> 5 min: Utility pg_registro si hay consentimiento y no hay respuesta
  -> Lead responde
  -> Conversation AI personaliza, completa datos faltantes y orienta compra
  -> Trigger Link de ficha o checkout Shopify
  -> compra, seguimiento responsable o asesor humano
```

### Lo que ya sabe la IA

El formulario entrega perfil de uso, dolor principal y etapa de decision. Por tanto, la IA no pregunta de nuevo "a que te dedicas", "que problema tienes" o "que quieres revisar" si esa respuesta ya existe.

### Como abre la conversacion

La Utility confirma que se recibio la solicitud. Cuando la persona responde, la IA usa una apertura conectada con sus respuestas:

- **Profesional remoto:** reconoce reuniones, clientes, rutina hibrida y presencia del espacio.
- **Freelancer/emprendedor/vendedor online:** conecta con una base de operaciones, productividad y entorno que acompanhe el negocio.
- **Developer/creativo/gamer:** conecta con bloques de foco, pantalla, versatilidad y pausa.
- **Deseo de transformar el espacio:** conecta con identidad, ambiente y un lugar que deje de sentirse temporal.

Despues responde la duda expresada. Solo entonces pregunta por el siguiente dato que realmente hace falta: producto/color, ciudad, plazo o pago.

## Ruta 2 | Anuncio directo a WhatsApp

```text
Anuncio Click-to-WhatsApp
  -> Mensaje entrante
  -> Conversation AI identifica origen y campos Meta ausentes
  -> responde intencion primero
  -> completa perfil, dolor, etapa, ciudad, plazo y pago de forma progresiva
  -> ficha o checkout rastreable / handoff humano
```

No hay interrogatorio ni menu rigido. Si el lead dice "quiero comprar el naranja", la IA confirma lo indispensable para cerrar: referencia/color, precio vigente, ciudad y pago. Si dice "quiero saber mas", aclara primero producto y despues recoge una pregunta a la vez.

## Secuencia comercial dentro de la IA

| Paso | Comportamiento esperado | Ejemplo de proposito |
|---|---|---|
| 1. Reconocer | Demostrar que entendio el contexto | "No buscas solo un sillón; buscas que tu espacio deje de quedarse corto para tu rutina." |
| 2. Diagnosticar | Una pregunta breve sobre la duda pendiente | "De lo que mencionas, quieres resolver primero color, medida o forma de pago?" |
| 3. Recomendar | Conectar necesidad con funcion confirmada | Reclinacion para pausa, giro para flexibilidad, diseno para el entorno. |
| 4. Probar | Dar seguridad sin inventar | Fuente vigente, disponibilidad confirmada, garantia del fabricante si aplica. |
| 5. Cerrar | Proponer un siguiente paso claro | Revisar color o avanzar a compra. |
| 6. Escalar | Entregar a humano cuando la regla lo exige | Descuento, inventario exacto, compra multiple, transferencia o condicion no verificada. |

## Ruta de pago y compra

### Checkout Shopify

La ruta normal de compra es Shopify. Antes de abrir checkout, la IA confirma:

1. producto y color;
2. precio publico vigente;
3. intencion real de compra;
4. ciudad si es necesaria para la logistica;
5. forma de pago preferida.

Despues comparte el **Trigger Link interno** que corresponda. La IA no pega URLs directas ni textos de variables tecnicas. El clic queda registrado como visita de ficha o apertura de checkout.

### Addi

Si el lead consulta financiacion, la IA explica que existen opciones con Addi desde 0% de interes, sujetas a aprobacion y condiciones vigentes. Puede recopilar el contexto comercial permitido, pero no pide cedula, tarjeta, CVV, OTP u otros datos sensibles. Si quiere aplicar, se entrega el caso al proceso o asesor autorizado.

### Transferencia, comprobante y envio

La conversacion puede llevar a una venta por transferencia solo cuando PAGUREO tenga datos de pago reales, politicas vigentes y un responsable humano de validacion. Este dossier no incluye datos bancarios, y la IA no debe usar datos ficticios.

La secuencia segura es:

1. Confirmar producto, precio, ciudad y deseo de pagar por transferencia.
2. Escalar o usar un proceso comercial aprobado para compartir datos reales.
3. Recibir comprobante y datos de envio solo por el canal/proceso autorizado.
4. Validacion humana de pago e inventario.
5. Confirmacion al cliente de que la informacion esta en verificacion.
6. Informar despacho o guia solo cuando la operacion lo confirme.

La IA nunca confirma pago, pedido, entrega o guia sin validacion humana o evento de plataforma.

## Handoff humano obligatorio

La IA se detiene y deja el caso para un asesor si ocurre alguno de estos casos:

- la persona pide un humano;
- descuento, negociacion, compra multiple o condicion especial;
- inventario, medida, envio, garantia, devolucion, factura u oferta no confirmada;
- transferencia, contraentrega, comprobante o pago fallido;
- producto de aliado, producto no identificado o articulo fuera de catalogo;
- tres mensajes sin poder avanzar con claridad.

La respuesta se limita a confirmar que se revisara la condicion correctamente. El workflow interno crea la tarea y entrega contexto; no debe enviar otro mensaje comercial en paralelo.

## No respuesta y reactivacion responsable

La cadencia alterna WhatsApp y email durante 14 dias, siempre que exista consentimiento y ninguna senal de salida. Se detiene de inmediato ante respuesta, compra, DND, opt-out, handoff o cierre de oportunidad. El ultimo contacto ofrece pausar y retomar sin empezar desde cero.

No se activa carrito abandonado hasta que Shopify devuelva eventos y se pruebe la integracion. No se persigue a una persona manualmente desde la IA.

