# 12 | Emails de Seguimiento

**Estado:** siete plantillas registradas como creadas y leidas de vuelta en GHL el 3 de agosto de 2026. El remitente, footer legal, Trigger Links y estado actual requieren verificacion antes de activar envios.  
**Relacion:** [workflows](10-WORKFLOWS-Y-AUTOMATIZACIONES.md) | [tracking](13-SHOPIFY-TRIGGER-LINKS-Y-ATRIBUCION.md).

## Reglas de la secuencia

- Cada email usa una imagen distinta de Shopify, seleccionada sin precio visible.
- Ningun correo contiene un precio fijo o comparativo. Eso evita que un cambio comercial deje una promesa desactualizada en circulacion.
- Cada CTA apunta a un Trigger Link interno de `product_view`, no a una URL directa.
- Los emails se envian solo con direccion valida, consentimiento aplicable, DND de email desactivado, sin compra, handoff, baja ni respuesta reciente.
- El footer de cumplimiento de GHL permanece habilitado. El remitente se configura en la subcuenta, no dentro del HTML.
- Una respuesta del lead corta la cadencia y la conversacion continua con IA o asesor.

## Mapa de secuencia

| Orden | Nombre | Timing | Objetivo | Activo visual |
|---|---|---|---|---|
| 01 | PGR \| 01 \| Tu espacio empieza aqui | Registro | Confirmar solicitud y abrir valor | Sillón naranja en uso junto a ventana |
| 02 | PGR \| 02 \| Tu rutina | Dia 2 | Conectar foco, pausa y espacio | Sillón crema en home office |
| 03 | PGR \| 03 \| Color y espacio | Dia 4 | Llevar eleccion de color a conversacion | Sillón azul en ambiente residencial |
| 04 | PGR \| 04 \| Financiacion Addi | Dia 6 / intencion | Explicar proceso de Addi sin prometer | Sillón gris en home office |
| 05 | PGR \| 05 \| Funciones reales | Dia 8 | Demostrar reclinacion y giro | Detalle de reclinacion naranja |
| 06 | PGR \| 06 \| Oferta y medidas | Dia 10 | Resolver encaje y luego oferta vigente | Ficha tecnica azul |
| 07 | PGR \| 07 \| Retomar tu espacio | Dia 14 | Pausar con respeto y facilitar regreso | Textura de tapizado naranja |

## Email 01 | PGR | 01 | Tu espacio empieza aqui

**Asunto:** Tu espacio no tiene que seguir trabajando en tu contra  
**Previsualizacion:** Conoce las funciones, colores y condiciones que puedes revisar con PAGUREO.  
**CTA rastreable:** `Ver sillón naranja`.

**Texto completo:**

> Hola {{contact.first_name}}, recibimos las respuestas que compartiste sobre tu rutina. Ahora puedes revisar con calma cómo PAGUREO puede acompañarte en tus momentos de foco, pausa y descanso.
>
> No es solo elegir un mueble. Es construir un lugar que se vea a la altura de lo que ya haces desde casa.
>
> **Te ayudaremos a decidir con información clara.** Podrás revisar colores disponibles, funciones, medidas, condiciones comerciales y las alternativas de financiación que apliquen a tu consulta.
>
> **Reclinación:** cambia de ritmo sin salir de tu espacio.  
> **Giro 360 grados:** más libertad para una rutina versátil.  
> **Tu estilo:** elige el color que encaje con tu ambiente.
>
> Si prefieres resolver una duda antes de avanzar, responde a este correo. Te orientaremos sobre el detalle que necesitas revisar.

## Email 02 | PGR | 02 | Tu rutina

**Asunto:** Tu jornada cambió. Tu espacio también puede hacerlo  
**Previsualizacion:** Alterna foco, pausa y descanso desde un espacio que acompañe tu ritmo.  
**CTA rastreable:** `Ver sillón crema`.

> Cuando tu casa también es oficina, sala de reuniones, estudio y lugar de descanso, pasar horas en el mismo punto termina haciendo que todo se sienta igual de rígido.
>
> PAGUREO te ayuda a construir una zona complementaria para leer, pensar, responder, hacer una pausa y volver a lo importante sin que tu espacio trabaje en tu contra.
>
> **Una pausa no debería obligarte a abandonar tu espacio.** La idea no es trabajar menos. Es tener un lugar que te permita cambiar de ritmo durante una jornada real.
>
> **Foco:** un rincón que acompaña tus bloques de trabajo.  
> **Pausa:** reclinación para cambiar de posición cuando la necesitas.  
> **Presencia:** un ambiente más claro para vivir y producir desde casa.
>
> Puedes responder este correo con la duda que hoy te frena: color, medidas, funciones o forma de pago.

## Email 03 | PGR | 03 | Color y espacio

**Asunto:** El color correcto también cambia la forma en que trabajas  
**Previsualizacion:** Elige una referencia que se sienta propia y deje de verse temporal.  
**CTA rastreable:** `Ver sillón azul`.

> El color no es un detalle al final. Es parte de la forma en que un rincón se siente cuando entras a trabajar, recibes una llamada o decides tomarte una pausa.
>
> Azul oscuro, naranja, crema o gris: cada referencia cambia la presencia del ambiente. Lo importante es elegir una que combine con tu ritmo, no solo con una foto.
>
> **Elegir bien es construir un entorno que te represente.** Antes de avanzar, puedes confirmar qué color encaja con tu ambiente y revisar la disponibilidad vigente.
>
> **Azul oscuro:** una presencia sobria para un espacio de concentración.  
> **Naranja:** un punto de energía para un ambiente con personalidad.  
> **Crema y gris:** alternativas para integrar la pieza con facilidad.
>
> Responde este correo con el color que mas te interesa y te ayudaremos a confirmar el siguiente paso.

## Email 04 | PGR | 04 | Financiacion Addi

**Asunto:** Una mejora que usas todos los días no tiene que aplazarse  
**Previsualizacion:** Revisa cómo funciona el proceso de financiación con Addi antes de decidir.  
**CTA rastreable:** `Ver sillón gris`.

> Si ya sabes que tu espacio necesita una mejora, pero quieres revisar alternativas antes de decidir, podemos orientarte sobre el proceso de financiación con Addi.
>
> Existen opciones desde 0 por ciento de interés, sujetas a aprobación y a las condiciones vigentes de Addi. Por eso primero se revisa la referencia que quieres, luego la alternativa aplicable y finalmente los requisitos reales.
>
> **Así puedes avanzar con más claridad.** Primero eliges la referencia que te interesa. Después nos indicas que deseas revisar financiación. El equipo te guía con las condiciones vigentes, sin asumir cupo, plazo ni aprobación.
>
> **Elige:** confirma la referencia que mejor encaja contigo.  
> **Consulta:** pide revisar el proceso y requisitos vigentes de Addi.  
> **Decide:** avanza solo con condiciones claras para tu caso.
>
> Responde este correo con la palabra ADDI y te orientaremos sobre el paso que corresponde a tu consulta.

## Email 05 | PGR | 05 | Funciones reales

**Asunto:** No trabajas en una sola posición. Tu espacio tampoco debería hacerlo  
**Previsualizacion:** Reclinación y giro 360 grados para una rutina que cambia durante el día.  
**CTA rastreable:** `Ver funciones del sillón`.

> No necesitas que todos tus momentos se vean iguales. Hay horas de concentración, llamadas, lectura, mensajes, descanso y vueltas a empezar.
>
> Por eso PAGUREO combina reclinación y giro 360 grados en una pieza que acompaña una rutina versátil. No promete resolver tu trabajo: te da un lugar más funcional para atravesarlo.
>
> **Mira el detalle que cambia el uso diario.** La reclinación te permite pasar de una posición activa a una pausa. El giro 360 grados te da libertad para moverte dentro del mismo entorno.
>
> **Reclinación:** cambia de ritmo cuando tu jornada lo pide.  
> **Giro 360 grados:** integra el sillón a un espacio que no es estático.  
> **Diseño acolchado:** una presencia funcional para casa, estudio o home office.
>
> Si quieres confirmar cómo encaja una función con tu espacio, responde este correo y cuéntanos qué deseas revisar.

## Email 06 | PGR | 06 | Oferta y medidas

**Asunto:** Una oferta tiene más sentido cuando sabes exactamente qué eliges  
**Previsualizacion:** Revisa medidas reales, disponibilidad y condiciones vigentes antes de avanzar.  
**CTA rastreable:** `Revisar ficha azul`.

> Una pieza puede verse bien en una foto y aun así no encajar en el lugar donde la vas a usar. Revisar medidas, funciones y disponibilidad te permite decidir con más seguridad antes de avanzar.
>
> La ficha pública muestra 96 cm de alto, 86 cm de ancho, 66 cm de diámetro de base y 163 cm de largo reclinado. Con esa información puedes evaluar mejor el espacio que tienes disponible.
>
> **Después puedes consultar la oferta vigente.** Cuando tengas clara la referencia y el encaje en tu espacio, el equipo puede confirmar las condiciones comerciales actuales y las opciones de financiación que apliquen.
>
> **96 cm de alto:** una medida clave para visualizar la presencia de la pieza.  
> **86 cm de ancho:** revisa el encaje antes de definir tu referencia.  
> **163 cm reclinado:** considera el espacio disponible cuando quieras cambiar de ritmo.
>
> Responde este correo si quieres consultar la oferta de la semana después de revisar las medidas.

## Email 07 | PGR | 07 | Retomar tu espacio

**Asunto:** Cuando tu espacio necesite una mejora, retomamos  
**Previsualizacion:** Puedes volver a la conversación sin empezar de cero cuando sea el momento.  
**CTA rastreable:** `Volver a ver PAGUREO`.

> Vamos a pausar este seguimiento para respetar tu tiempo. Si hoy no es el momento, no pasa nada: cuando quieras volver, podremos retomar desde la duda que tengas en lugar de empezar la conversación desde cero.
>
> Tu próximo espacio puede combinar función, presencia y comodidad. Lo importante es que la mejora tenga sentido para la rutina que realmente vives.
>
> **Cuando regreses, tendrás claridad sobre qué revisar.** Color, funciones, medidas, disponibilidad, oferta vigente y opciones con Addi: retomamos solo lo que necesites resolver para decidir.
>
> **Material:** revisa el detalle visual que más se siente en tu espacio.  
> **Función:** confirma cómo reclinación y giro encajan en tu rutina.  
> **Decisión:** vuelve cuando quieras con una pregunta concreta.
>
> Cuando quieras retomar, responde este correo o visita la referencia y te ayudaremos a continuar desde donde quedaste.

## Verificacion antes de activar envios

- [ ] Leer en GHL nombre, asunto, previsualizacion, HTML, imagen, CTA y Trigger Link de las siete plantillas.
- [ ] Confirmar remitente, dominio, inbox de respuesta y footer legal.
- [ ] Verificar que cada imagen sigue disponible y no muestra precio.
- [ ] Probar el email 01 con un contacto interno autorizado.
- [ ] Confirmar que un reply, DND, compra, baja u handoff detiene la cadencia.
- [ ] Confirmar que el contenido Addi y oferta vigente coincide con la condicion comercial real.

