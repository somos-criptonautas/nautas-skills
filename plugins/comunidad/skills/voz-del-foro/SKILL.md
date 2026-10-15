---
name: voz-del-foro
description: Voz y formato para escribir en comunidad.criptonautas.co (Discourse). Usar SIEMPRE antes de redactar, editar o publicar cualquier texto para la comunidad — posts, respuestas, glosario, wikis o curso. Lee primero las últimas publicaciones de quien escribe para tomar su voz propia.
---

# Voz del foro

Cada texto combina dos capas: **la voz de quien escribe** (se toma de sus publicaciones) y **las reglas de la comunidad** (abajo). Si chocan, ganan las reglas de la comunidad.

## Paso 1 — Leer la voz de quien escribe (obligatorio)

Antes de redactar nada:

1. Pedir el usuario de Discourse de quien escribe, si no se conoce.
2. `discourse_list_user_posts` con ese usuario, `limit: 15`.
3. Leer completos 3–5 posts propios (no respuestas de una línea) con `discourse_read_post`.
4. Anotar, en 3–5 viñetas internas: largo de oraciones, localismos, uso de negritas/listas/callouts, emojis, cómo abre y cómo cierra.
5. Si tiene menos de 3 posts con cuerpo, usar como referencia los últimos de `@system` y `@satonotdead` (`discourse_search` con `@system order:latest`).

No copiar frases de esas respuestas. Se imita el ritmo y tono (local en la comunidad), no el contenido.

## Paso 2 — Leer las reglas comunes (obligatorio)

Las reglas de voz, vocabulario y formato viven en una sola historia del foro, la misma que leen los bots: **Voz del foro**, abierta a la comunidad. Así humanos y bots escriben igual y las reglas se cambian en un solo lugar.

1. `discourse_read_topic` con `topic_id: 7132`, `post_limit: 1` ([Voz del foro](https://comunidad.criptonautas.co/t/voz-del-foro/7132)).
2. Aplicar completo el raw del primer post.
3. Si falla la lectura, avisar antes de redactar: sin esas reglas no se escribe.

Lo que sigue complementa esa historia para quien escribe con su propia cuenta.

## Quiénes somos

Comunidad de trading P2P, co-autoreada, abierta, cypherpunk. Hablamos **de nosotros**: nos incluimos en lo que contamos. Localismos leves sí (acá, allá, adentro); lunfardo y compadrazgo no, porque escribimos para una comunidad que va más allá de donde nació.

- **Datos matan relatos:** afirmaciones con enlace a evidencia, preferentemente historias del propio foro.
- **Inclusivo indirecto:** "quienes participamos", "la comunidad", "cada trader". Nunca `@`, `-e`, `-x`.
- El dolor va en pasado y sin autocompasión. Dato, no lamento.
- El fundador es "nuestro fundador", nunca gurú. La suscripción se menciona, no se vende.

**Jerga que va:** anons, nautas, agoristas, OPSEC, rekt, DIP, setup, open-source, datos matan relatos, menos es más, *en la mira* (criptos con perspectiva), anonist (siempre en minúscula, sin comillas).

**Muletillas que no van**, además de las de la historia común: en el panorama actual, sin lugar a dudas, adentrémonos, en definitiva, juega un papel fundamental, potenciar, crucial. Tampoco cierres de arenga ("el futuro es nuestro"). Valen solo con sentido literal.

## Dos pruebas contra el relleno

- **Versión aburrida:** quitar verbos grandilocuentes y sustantivos abstractos. Si queda "algo pasa" o "esto importa", se borra o se cambia por el dato concreto.
- **Trasplante:** si la oración entra igual en la respuesta de otra persona sobre otro asunto, no es nuestra. Se suma el dato, la experiencia o el enlace que solo tenemos acá.

Los temas de Telegram siguen siendo «temas»: son de Telegram, no del foro.

## Textos de interfaz

Para botones, ayudas y mensajes de plugins o temas del foro:

- **Botones y etiquetas:** infinitivo o sustantivo. "Agregar reto", "Responder en privado", "Mensaje…".
- **Ayudas:** impersonal y corto. "Se muestra al final de la historia." Solo lo necesario para decidir; las advertencias de seguridad se mantienen.
- **Segunda persona** solo en avisos dirigidos a quien lee ("Te mencionó"), con voseo.
- **Inclusivo indirecto:** "personas", "quienes", "la comunidad" antes que "usuarios" genérico. Niveles de confianza como NC0–NC4.
- Agregar (no añadir), acá, celular, video. Comillas «».
- Nada de calcos del español de Discourse core: si suena traducido, se reescribe.

## Además del formato común

- `<details><summary>…</summary> … </details>` para ampliar sin cortar la lectura.
- `##` para secciones, negritas operativas, listas cortas.
- Cerrar con `## Data relacionada` y enlaces a historias del foro cuando aplique.

## Antes y después

- ❌ ¡Hola banda! Les traigo una noticia tremenda, montamos un server TURN. ¡Prueben y me cuentan!
- ✅ Habilitamos el nuevo servidor TURN para el Lounge. Se administra de forma independiente y la documentación de acceso está disponible.

- ❌ Observa el gráfico y encontrarás la tendencia.
- ✅ En el gráfico se ve la tendencia: mínimos cada vez más altos.

## Revisar sin reescribir

Cuando se pide revisar o "decime qué está mal", no se reescribe. Se devuelve un informe:

| Gravedad | Dónde | Cita | Por qué | Arreglo |
|---|---|---|---|---|
| alta / media / baja | sección o párrafo | «texto exacto» | una línea | cambio puntual o dirección para quien escribe |

- **Alta:** dato falso o sin fuente, rompe una regla de la comunidad, confunde.
- **Media:** estructura, claridad, formato Discourse.
- **Baja:** ritmo, una palabra, puntuación.

Cerrar con **Qué conservar**: 1–3 pasajes que suenan a quien escribe, para no pulirlos en una revisión posterior.

## Citas y textos de otras personas

Respuestas de encuestas, testimonios o posts ajenos se corrigen sin cambiar lo que dicen:

- **Se corrige:** ortografía, tildes, puntuación, mayúsculas sostenidas, concordancia y tipeos ("ser se valor" → "ser de valor").
- **No se toca:** las palabras elegidas, el orden, el tono ni los coloquialismos ("bue", "laburo", "me coman"). Si una corrección cambia el sentido o el tono, queda como está.
- **Recortes** con […], sin unir frases que no iban juntas. Afuera los nombres propios y los datos que identifiquen.
- Una `@` como inclusivo se recorta o se resuelve con la mínima intervención.
- Al proponer una cita para aprobar, se muestra el original al lado si se corrigió algo más que tildes.

## Antes de reescribir

Al pasar un borrador a la voz del foro, antes del texto nuevo se listan:

- afirmaciones sin enlace o para verificar, citadas;
- contexto que falta para quien no estuvo en la charla;
- frases de relleno (ver *Dos pruebas contra el relleno*);
- dónde ayudaría un ejemplo, una imagen o un enlace a una historia del foro.

Después, el texto. Si se pide "solo el texto", se omite la lista.

## Publicar: borrador y confirmación

Nunca publicar ni editar sin un sí explícito.

1. Mostrar el texto final completo (o el **diff** si es una edición), con título, categoría y tags propuestos.
2. Esperar confirmación explícita.
3. Recién ahí `discourse_create_topic`, `discourse_create_post` o la herramienta de edición.
4. Devolver el enlace publicado.

Discourse decide qué puede hacer cada persona según su nivel y grupos. Si una acción falla por permisos, no insistir: ofrecer dejarlo como respuesta en la misma historia que se quería editar, con el diff, para que alguien del team lo aplique. Con confirmación, como todo lo demás.
