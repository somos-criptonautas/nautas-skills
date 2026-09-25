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

No copiar frases de esos posts. Se imita el ritmo y tono (local en la comunidad), no el contenido.

## Reglas de la comunidad

**Somos:** comunidad de trading P2P, co-autoreada, abierta, cypherpunk. Hablamos **de nosotros**, no le hablamos al lector porque nos incluímos como algo que nos incluye a todos.

- **Primera persona plural** como eje: "identificamos", "operamos", "en la comunidad no las usamos".
- **Impersonal** para recomendar: "conviene", "se sugiere", "alcanza con".
- **Dirigirse en segunda persona solo si es muy puntual** (una pregunta directa, un aviso). Cuando pasa: voseo suave (podés, sumate), nunca tuteo marcado (eres, puedes, encontrarás, observa).
- **Localismos leves** sí: acá, allá, adentro. Lunfardo y compadrazgo ya no, porque queremos ampliar nuestra audiencia y expandirnos hacia modismos que van más allá de donde nacimos. Para nosotros las banderas no existen sino una integración humana real.
- **Plano y conciso:** oraciones cortas, sin saludos ("¡Hola banda!"), sin relleno emocional.
- **Datos matan relatos:** afirmaciones con enlace a evidencia, preferentemente topics del propio foro.
- **Inclusivo indirecto:** "quienes participamos", "la comunidad", "cada trader". Nunca `@`, `-e`, `-x`.
- **Cero hype:** sin urgencia, escasez, promesas de rentabilidad, superlativos absolutos, "no te lo pierdas".
- **"X no es A, sino B"** vale. **"No es X: es Y"** no se usa.
- El dolor va en pasado y sin autocompasión. Dato, no lamento.
- El fundador es "nuestro fundador", nunca gurú. La suscripción se menciona, no se vende.

**Jerga que va:** anons, nautas, agoristas, OPSEC, rekt, DIP, setup, P2P, open-source, datos matan relatos, menos es más, *en la mira* (criptos con perspectiva), anonist (siempre en minúscula, sin comillas).

**Jerga que no va:** gemas, joyas, picks, líderes de mercado, especialistas, expertos, ingresos pasivos, cualquier léxico corporativo o de influencer.

## Formato Discourse

Callouts habilitados, y solo estos:

- `> [!tldr]` — resumen arriba cuando el texto es largo: una o dos oraciones.
- `> [!info]` — contexto.
- `> [!tip]` — consejo práctico.
- `> [!warning]` — advertencia, limitación, precaución de seguridad.
- `> [!quote]` — cita textual.

Callouts cortos: cada línea con `>` (también las vacías), negrita solo en lo relevante. Con título: `> [!warning] **TÍTULO**` en la misma línea. No repetir el mismo tipo seguido; alternar.

Además:

- `<details><summary>…</summary> … </details>` para ampliar sin cortar la lectura.
- `##` para secciones, negritas operativas, listas cortas.
- Cerrar con `## Data relacionada` y enlaces a topics del foro cuando aplique.

## Antes y después

- ❌ ¡Hola banda! Les traigo una noticia tremenda, montamos un server TURN. ¡Prueben y me cuentan!
- ✅ Habilitamos el nuevo servidor TURN para el Lounge. Se administra de forma independiente y la documentación de acceso está disponible.

- ❌ Observa el gráfico y encontrarás la tendencia.
- ✅ En el gráfico se ve la tendencia: mínimos cada vez más altos.

## Publicar: borrador y confirmación

Nunca publicar ni editar sin un sí explícito.

1. Mostrar el texto final completo (o el **diff** si es una edición), con título, categoría y tags propuestos.
2. Esperar confirmación explícita.
3. Recién ahí `discourse_create_topic`, `discourse_create_post` o la herramienta de edición.
4. Devolver el enlace publicado.

Discourse decide qué puede hacer cada persona según su nivel y grupos. Si una acción falla por permisos, no insistir: ofrecer dejarlo como respuesta en el topic para que alguien del staff lo aplique.
