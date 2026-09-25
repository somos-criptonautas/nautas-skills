---
name: glosario
description: Crear o editar términos del glosario de comunidad.criptonautas.co. Usar cuando se pida definir, agregar, corregir o ampliar un término (cripto, trading, privacidad, jerga de la comunidad).
---

# Glosario

Aplicar primero la skill `voz-del-foro` (incluye leer la voz de quien escribe).

## 1. Buscar antes de crear

`discourse_search` con el término y sus variantes (español, inglés, sigla). Si existe, se edita o se amplía; no se duplica.

## 2. Formato de una entrada

Tomar como modelo una entrada reciente del glosario (por ejemplo "Block Reward (Recompensa de bloque)"): leerla con `discourse_read_topic` para copiar **categoría y tags** exactos. No inventar tags: Discourse descarta en silencio los que la categoría no permite.

- **Título:** `Término en inglés (Término en español)` o solo el término si no tiene traducción usada. Sigla entre paréntesis si aplica: `Bitcoin Price Index (BPI)`.
- **Cuerpo:**
  1. Definición en 1–2 oraciones, en palabras cotidianas. Dato concreto si lo hay (cifras, fechas).
  2. Una línea en blanco.
  3. Frase de ejemplo en cursiva y entre comillas, como se diría en la comunidad.

```markdown
Lo que recibe el minero que completa un bloque: monedas nuevas más las comisiones de sus transacciones. Se reduce a la mitad en cada halving.

*"La recompensa baja a la mitad cada halving: menos emisión, oferta más escasa."*
```

## 3. Reglas

- Sin opinión dentro de la definición; si la comunidad tiene postura, va en la frase de ejemplo o con enlace a un topic.
- Sin enlaces externos salvo que el término no se entienda sin ellos.
- Cifras que cambian (recompensas, fees) con año: "desde 2024 es de…".
- Jerga propia (nautas, anonist, en la mira) también entra al glosario, con el mismo formato.

## 4. Publicar

Borrador y confirmación, según `voz-del-foro`.
