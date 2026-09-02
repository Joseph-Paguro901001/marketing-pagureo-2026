# 11 | Plantillas WhatsApp y Seguimiento

**Estado:** lote final en borrador local para carga/revision de Meta. No se debe enviar ni activar desde workflows hasta que cada plantilla tenga estado aprobado y se cumplan las guardas de consentimiento.  
**Relacion:** [funnel](07-FUNNEL-COMERCIAL-Y-EXPERIENCIA-DEL-LEAD.md) | [workflows](10-WORKFLOWS-Y-AUTOMATIZACIONES.md).

## Reglas de uso del lote

- Los nombres son cortos, sin fechas, versiones ni referencias de producto no confirmadas.
- En Meta se cargan variables numericas. GHL asigna el nombre o la URL resuelta al enviar; no se pegan merge fields tecnicos en el editor de Meta.
- No existe variable de sillón, referencia o inventario. Solo se personaliza el nombre y, en `pg_link`, una URL rastreable que la persona solicito expresamente.
- Utility se usa por una accion o solicitud concreta. No vende, presiona ni usa financiacion como promocion.
- Marketing exige consentimiento, ausencia de DND/opt-out, ningun chat activo, ninguna compra, ningun handoff y salida inmediata cuando la persona responde.
- Toda plantilla incluye encabezado, footer y maximo dos botones. Las de Marketing incluyen valor real: dolor reconocido, beneficio, razon para retomar y CTA claro.
- La negrita de WhatsApp usa un asterisco por lado: `*asi*`. No se usa Markdown de doble asterisco en el editor de Meta.

## Variables

| Variable Meta | Asignacion desde GHL | Uso |
|---|---|---|
| `{{1}}` | Nombre del contacto | Todas las plantillas que saludan al lead. |
| `{{2}}` | URL final de un Trigger Link ya resuelto | Solo `pg_link`, despues de que el lead pida el enlace. |

## Mapa de la secuencia

| Senal o momento | Plantilla | Categoria | Condicion estricta |
|---|---|---|---|
| Registro Meta sin respuesta | `pg_registro` | Utility | Confirma solicitud; no oferta ni financiacion. |
| Solicitud de foto, detalle, medida o funcion | `pg_info` | Utility | Solo material solicitado. |
| Solicitud expresa de financiacion | `pg_financia` | Utility | Confirma proceso; no promociones. |
| Solicitud expresa de enlace | `pg_link` | Utility | URL rastreable ya resuelta. |
| Solicitud de asesor | `pg_asesor` | Utility | Handoff pedido por la persona. |
| Dia 1 sin respuesta | `pg_rutina` | Marketing | Consentimiento, sin chat, compra, handoff o baja. |
| Dia 3 sin respuesta | `pg_color` | Marketing | Cancelar al responder. |
| Dia 4/segun interes | `pg_addi` | Marketing | Solo con condiciones Addi vigentes. |
| Dia 7 sin respuesta | `pg_funcion` | Marketing | Cancelar al responder. |
| Dia 10 sin respuesta | `pg_oferta` | Marketing | Solo con oferta vigente confirmada. |
| Dia 14 sin respuesta | `pg_retomar` | Marketing | Cierra la secuencia. |

## A. Utility

### U1 | `pg_registro`

**Categoria:** Utility  
**Encabezado:** `Tu solicitud de PAGUREO`  
**Uso:** persona que completo el formulario Meta y autorizo la atencion por WhatsApp.  
**Footer:** `PAGUREO | Información en proceso`

```text
Hola {{1}}. Recibimos tu solicitud de información de PAGUREO y registramos las respuestas que compartiste sobre tu espacio.

Cuando respondas a este chat, te ayudaremos a revisar el detalle que te interesa, resolver dudas sobre funciones, medidas o disponibilidad y explicarte el siguiente paso de atención.
```

**Botones:** `Revisar mi solicitud` | `Hablar con asesor`.

### U2 | `pg_info`

**Categoria:** Utility  
**Encabezado:** `Detalle solicitado de PAGUREO`  
**Uso:** persona que pidio foto, detalle, funcion o medida y el material corresponde a la solicitud.  
**Footer:** `PAGUREO | Material solicitado`

```text
Hola {{1}}. Te compartimos el material de PAGUREO que solicitaste para que puedas revisarlo con calma.

En este chat podemos aclarar la duda que originó tu solicitud, por ejemplo funciones, medidas, color o disponibilidad, antes de que decidas el siguiente paso.
```

**Botones:** `Tengo una duda` | `Hablar con asesor`.

### U3 | `pg_financia`

**Categoria solicitada:** Utility  
**Encabezado:** `Proceso de financiación`  
**Uso:** persona que pidio expresamente revisar financiacion.  
**Footer:** `PAGUREO | Información de financiación`

```text
Hola {{1}}. Registramos tu solicitud para revisar las alternativas de financiación de PAGUREO.

Por este chat te compartiremos el proceso, requisitos y condiciones vigentes que necesitas revisar para saber si puedes avanzar con Addi. La validación final depende de Addi.
```

**Botones:** `Revisar requisitos` | `Hablar con asesor`.

No incluir 0%, precio, descuento, invitacion de compra ni cuota. Si Meta la recategoriza como Marketing, se acepta la categoria antes de usarla.

### U4 | `pg_link`

**Categoria solicitada:** Utility  
**Encabezado:** `Acceso solicitado de PAGUREO`  
**Uso:** persona que pidio expresamente un enlace y GHL resolvio el Trigger Link correcto.  
**Footer:** `PAGUREO | Acceso solicitado`

```text
Hola {{1}}. Aquí tienes el acceso de PAGUREO que solicitaste: {{2}}

Este enlace te permite revisar la información y el proceso que pediste. Si necesitas confirmar algún detalle antes de continuar, responde por este chat.
```

**Botones:** `Necesito ayuda` | `Hablar con asesor`.

No cargar ni enviar si la variable `{{2}}` no se convierte en una URL rastreable real.

### U5 | `pg_asesor`

**Categoria:** Utility  
**Encabezado:** `Atención solicitada de PAGUREO`  
**Uso:** persona que pidio hablar con un asesor humano.  
**Footer:** `PAGUREO | Atención con asesor`

```text
Hola {{1}}. Registramos tu solicitud para hablar con un asesor de PAGUREO y dejamos el contexto de tu consulta para el equipo.

El asesor continuará la atención por este mismo chat para ayudarte con la información que necesitas revisar y el siguiente paso apropiado.
```

**Botones:** ninguno.

## B. Marketing

### M1 | `pg_rutina`

**Categoria:** Marketing  
**Encabezado/arte:** `wa-dia-2-valor-home-office.png`  
**Uso:** 24 horas sin respuesta, salvo intencion principal de financiacion.  
**Footer:** `PAGUREO | Escribe SALIR para no recibir más mensajes`

```text
Hola {{1}}. 💻

Entre reuniones, entregas y mensajes, pasar el día en un espacio improvisado no solo cansa: hace que cada pausa se sienta igual de desordenada.

*Tu espacio también puede impulsar la forma en que trabajas.*

Con PAGUREO ganas:
✅ *Reclinación para alternar concentración y pausa.*
✅ *Giro 360° para una rutina más flexible.*
✅ *Diseño sobrio que le da presencia a tu home office.*

No se trata de llenar un rincón. Se trata de dejar de adaptarte a un lugar que ya se quedó corto. ✨

¿Quieres revisar los colores disponibles?
```

**Botones:** `Ver colores` | `No recibir mensajes`.

### M2 | `pg_color`

**Categoria:** Marketing  
**Encabezado/arte:** `wa-producto-sillon-naranja.png`  
**Uso:** 72 horas sin respuesta.  
**Footer:** `PAGUREO | Escribe SALIR para no recibir más mensajes`

```text
Hola {{1}}. 🎨

Un espacio útil también puede sentirse propio. El color, la forma y el lugar que eliges para descansar entre tareas cambian la energía con la que vuelves a trabajar.

*Elegir bien no es solo decorar: es construir un entorno que te represente.*

Antes de avanzar puedes revisar:
✅ *Qué color se siente mejor en tu ambiente.*
✅ *Cómo combinar presencia visual y funcionalidad.*
✅ *La disponibilidad real antes de tomar una decisión.*

Tu oficina en casa deja de verse armada con lo primero que encontraste. 📍

¿Quieres que revisemos los colores disponibles?
```

**Botones:** `Ver colores` | `No recibir mensajes`.

### M3 | `pg_addi`

**Categoria:** Marketing  
**Encabezado:** `Financia tu mejora con Addi`  
**Uso:** 24 horas sin respuesta si indico financiacion; 96 horas para otro interes.  
**Footer:** `PAGUREO | Financiación sujeta a aprobación y condiciones de Addi`

```text
Hola {{1}}. 💳

Una mejora que vas a usar todos los días no tiene que quedarse aplazada solo por la forma de pago.

Con *Addi* puedes revisar opciones de financiación *desde 0% de interés*, sujetas a aprobación y condiciones vigentes.

Esto te permite:
✅ *Elegir con más calma el momento de compra.*
✅ *Revisar alternativas antes de descartar la mejora.*
✅ *Avanzar con información clara, sin asumir una aprobación.*

Tu espacio puede empezar a acompañar el nivel al que ya trabajas. ✨

¿Quieres revisar cómo aplicar con Addi?
```

**Botones:** `Quiero aplicar` | `No recibir mensajes`.

### M4 | `pg_funcion`

**Categoria:** Marketing  
**Encabezado/arte:** `wa-detalle-material-naranja.png`  
**Uso:** dia 7 sin respuesta.  
**Footer:** `PAGUREO | Escribe SALIR para no recibir más mensajes`

```text
Hola {{1}}. 🔄

Cuando una jornada cambia entre concentración, llamadas, lectura y una pausa corta, un mueble rígido termina obligándote a hacer todo igual.

*Tu día no tiene una sola posición. Tu espacio tampoco debería tenerla.*

PAGUREO está pensado para una rutina más versátil:
✅ *Reclínate cuando necesites cambiar de ritmo.*
✅ *Usa el giro 360° para moverte con libertad.*
✅ *Mantén un ambiente funcional sin estética de oficina genérica.*

Es una mejora que se nota en cada jornada, no solo el día que la compras. 🪑

¿Prefieres revisar funciones o medidas?
```

**Botones:** `Revisar funciones` | `No recibir mensajes`.

### M5 | `pg_oferta`

**Categoria:** Marketing  
**Encabezado:** `Consulta la oferta de la semana`  
**Uso:** dia 10 sin respuesta y solo con oferta vigente confirmada.  
**Footer:** `PAGUREO | Oferta y condiciones sujetas a vigencia`

```text
Hola {{1}}. 🔥

Si tu espacio ya se quedó pequeño para tu rutina, esperar no hace que la decisión sea más fácil: solo alarga los días en los que trabajas desde un lugar que no te acompaña.

*La oferta de la semana es el momento para revisar condiciones reales antes de decidir.*

Por este chat puedes confirmar:
✅ *Disponibilidad por color antes de avanzar.*
✅ *Funciones y medidas para tu espacio.*
✅ *Opciones de financiación con Addi, si aplican.*

Así eliges con claridad, no por impulso. ✨

¿Quieres consultar la oferta vigente?
```

**Botones:** `Consultar oferta` | `No recibir mensajes`.

### M6 | `pg_retomar`

**Categoria:** Marketing  
**Encabezado:** `Retoma cuando sea el momento`  
**Uso:** dia 14 sin respuesta; cierra la secuencia y no reactiva sin nueva senal.  
**Footer:** `PAGUREO | Escribe SALIR para no recibir más mensajes`

```text
Hola {{1}}. ⏸️

Vamos a pausar este seguimiento para respetar tu tiempo. Antes de hacerlo, te dejamos una forma simple de retomar cuando tu espacio vuelva a pedir una mejora.

*No tendrás que empezar la conversación desde cero.*

Cuando regreses podremos revisar:
✅ *Color y disponibilidad para tu ambiente.*
✅ *Funciones y encaje en tu rutina.*
✅ *Oferta vigente o alternativas con Addi, si aplican.*

Tu próximo espacio puede reflejar mejor todo lo que ya construyes desde casa. ✨

¿Quieres retomar ahora o prefieres dejarlo para más adelante?
```

**Botones:** `Retomar` | `No recibir mensajes`.

## Preflight de carga y uso

- [ ] Confirmar que las 11 plantillas tienen encabezado, footer y maximo dos botones.
- [ ] Confirmar que los nombres son exactos y no incluyen version o descripcion larga.
- [ ] Cargar Utility solo para la accion transaccional que corresponde.
- [ ] Asociar los tres artes Marketing correctos y revisarlos en vista movil.
- [ ] Confirmar Addi y la oferta de la semana antes de usar `pg_addi` o `pg_oferta`.
- [ ] Verificar estado de aprobacion/categoria en Meta antes de activar cada una.
- [ ] Probar variables con un contacto interno; nunca usar un Trigger Link sin resolver.

