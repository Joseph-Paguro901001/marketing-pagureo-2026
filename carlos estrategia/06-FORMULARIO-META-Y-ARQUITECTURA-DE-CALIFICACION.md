# 06 | Formulario Meta y Arquitectura de Calificacion

**Estado:** formulario reportado como enviado/publicado el 3 de agosto de 2026. El readback de Meta y el mapeo Meta -> GHL aun requieren verificacion.  
**Relacion:** [anuncios](05-ADS-COPIES-Y-MATRIZ-DE-CREATIVOS.md) | [funnel](07-FUNNEL-COMERCIAL-Y-EXPERIENCIA-DEL-LEAD.md) | [CRM](09-CRM-CAMPOS-TAGS-PIPELINE-Y-DATOS.md).

## Proposito del formulario

El formulario no oculta el producto. Convierte una visita fria en una solicitud con contexto y entrega una razon clara para completarlo: recibir disponibilidad por color, detalles para decidir, oferta vigente y opciones de financiacion que puedan aplicar.

La estrategia busca que la conversacion posterior sea relevante desde el primer mensaje. Meta captura perfil, dolor y etapa; la IA completa solo ciudad/zona, plazo y forma de pago si faltan.

## Configuracion de alta intencion

| Elemento | Especificacion |
|---|---|
| Nombre interno | `PAGUREO | Sillón | Alta intención` |
| Tipo | Mayor intencion, con pantalla de revision final |
| Datos de contacto | Nombre completo, telefono y correo |
| Politica de privacidad | `https://pagureo.com/policies/privacy-policy` |
| CTA de anuncio | Mas informacion |
| CTA final | Toca aqui para acceder |
| Destino final | Coleccion de sillones en PAGUREO |

## Regla editorial Meta

El titulo y la descripcion de introduccion deben ser breves, visibles en la primera pantalla y no superar **60 caracteres cada uno**. La descripcion no usa emojis, precio, listas largas ni texto que requiera desplazamiento. Debe explicar que gana la persona por completar el formulario.

### Introduccion documentada

**Titulo - 59/60 caracteres:**

```text
Recupera comodidad y foco con un sillón que se adapta a ti.
```

**Descripcion:**

```text
Completa el formulario y recibe la oferta de la semana, colores disponibles y opciones de financiación para transformar tu espacio.
```

La pregunta 3 y la pantalla final fueron actualizadas posteriormente. Este titulo y descripcion son la ultima version local documentada y requieren readback visual para confirmar que son las que estan en Meta.

## Preguntas finales y espejo en GHL

Todos los campos son `TEXT`, no opciones de seleccion. Esto permite que Conversation AI conserve el valor de Meta o lo complete/actualice desde Bot Goals cuando una persona llega por WhatsApp directo.

### Pregunta 1

**Cual describe mejor tu rutina hoy?**

1. Trabajo remoto para una empresa, equipo o clientes.
2. Soy freelancer, emprendedor o vendo online.
3. Desarrollo, diseño, creo contenido o juego desde casa.
4. Quiero mejorar mi espacio porque ya no representa como vivo y trabajo.

**Campo GHL:** `PAGUREO | Perfil de uso`  
**Field key tecnica:** `contact.pagureo__perfil_de_uso`

**Razon estrategica:** permite adaptar el lenguaje a profesional remoto, emprendedor, creador/developer/gamer o comprador de transformacion de espacio.

### Pregunta 2

**Que esta fallando primero en tu espacio actual?**

1. Paso muchas horas en la misma posicion y necesito mas comodidad.
2. Mi rincón se siente improvisado o no se ve profesional.
3. No tengo un lugar claro para pausar y desconectarme.
4. Los muebles que uso ya no acompañan mi ritmo de vida.

**Campo GHL:** `PAGUREO | Dolor principal del espacio`  
**Field key tecnica:** `contact.pagureo__dolor_principal_del_espacio`

**Razon estrategica:** permite que la IA abra con la prioridad funcional o emocional real, sin diagnostico medico ni discurso generico.

### Pregunta 3

**Que necesitas revisar y aclarar principalmente sobre el producto?**

1. Quiero elegir color y confirmar disponibilidad.
2. Quiero validar funciones, medidas y encaje en mi espacio.
3. Quiero conocer las opciones de financiacion disponibles.
4. Quiero consultar la oferta de la semana y avanzar si encaja.

**Campo GHL:** `PAGUREO | Etapa de decisión`  
**Field key tecnica:** `contact.pagureo__etapa_de_decisin`

**Razon estrategica:** identifica la duda que la IA debe resolver primero. No pregunta precio ni obliga una declaracion de compra.

## Datos que completa Conversation AI

| Dato | Por que se obtiene | Regla |
|---|---|---|
| Ciudad o zona | Validar cobertura y logistica cuando aplique | Preguntar solo si esta vacio o es relevante para avanzar. |
| Plazo de compra | Distinguir investigacion, evaluacion y alta intencion | Una pregunta corta, sin presion. |
| Pago preferido | Ruta a Addi, tarjeta/checkout o asesor | No prometer aprobacion, cupo o condiciones. |

La IA no repite una respuesta existente del formulario. Si el lead entrega informacion espontaneamente, la aprovecha y no formula una pregunta redundante.

## Pantalla final reportada

**Titulo:**

```text
Te falta solo un paso. Tu nuevo espacio empieza aqui.
```

**Descripcion:**

```text
Visita el sitio web para conocer cada detalle del producto, elegir tu color y descubrir una mejor forma de trabajar, pausar y descansar.

En breve te contactaremos via WhatsApp para reclamar la oferta de la semana y otros beneficios.
```

**Accion:** ir al sitio web, coleccion de sillones.  
**CTA:** `Toca aqui para acceder`.

## Consentimiento, privacidad y seguimiento responsable

- El formulario debe contener politica de privacidad vigente y autorizacion clara para la atencion solicitada.
- Utility se usa para confirmar una solicitud concreta; Marketing exige consentimiento y control de baja.
- Antes de cada seguimiento se valida DND, opt-out, respuesta reciente, compra y handoff humano.
- Una respuesta del lead detiene la cadencia automatica y devuelve el control a Conversation AI o al asesor.

## QA obligatorio antes de trafico

- [ ] Hacer readback visual del formulario final en Meta.
- [ ] Probar que P1, P2 y P3 llegan a GHL como texto exacto.
- [ ] Confirmar politica, consentimiento, telefono y correo.
- [ ] Probar pantalla final, CTA y URL de la coleccion.
- [ ] Crear un lead interno autorizado y validar formulario -> GHL -> Utility -> respuesta -> IA.
- [ ] Confirmar que ninguna pregunta de la IA repite un campo ya recibido desde Meta.

