---
name: curso
description: Proponer o aplicar ediciones al curso libre de trading en comunidad.criptonautas.co (temas numerados como 2.2.2, TL;DR por capítulo). Usar cuando se pida corregir, ampliar, actualizar o sumar ejemplos a un tema del curso.
---

# Curso

Aplicar primero la skill `voz-del-foro`. En el curso manda la **voz de la comunidad** (publicado como `@system`), por encima de la voz personal.

## 1. Ubicar el tema

`discourse_search` con el número o título (`2.2 Análisis técnico`). Leer el tema completo y, si la edición toca contexto, también el anterior y el siguiente.

## 2. Estructura que se respeta

- **Título:** `N.N Título` o `N.N.N Título`.
- **Arriba:** `> [!tldr]` de 1–2 oraciones.
- **Navegación:** al inicio, de dónde viene ("Este tema continúa [2.2 Análisis técnico](…)"); al final, a dónde sigue ("Con el método claro, lo que sigue son los [ciclos de mercado](…)").
- **Secciones numeradas:** `## N.N.N.1 …`, `### …`. Al insertar una sección, renumerar las siguientes y avisarlo.
- **Placeholders** (`[IMAGEN-…]`, `[VIDEO-…]`, `[ENCUESTA-…]`) no se borran ni se inventa su contenido. Se editan y/o actualizan.
- **TL;DR del capítulo:** tiene autochequeo con `[poll]` y `[details="Ver respuesta"]`. Si el tema cambia algo que el TL;DR resume, proponer también ese ajuste.
- Ejemplos de la comunidad con enlace al topic original ("de la charla sobre patrones de velas").

## 3. Qué no se toca sin avisar

- El sentido de una regla, principio o advertencia ("perderemos dinero", "no operar es una salida válida").
- Cifras de casos resueltos.
- Enlaces entre temas.

Si la edición cambia sentido, se marca explícitamente en el borrador: **cambia el sentido de …**.

## 4. Proponer o aplicar

1. Mostrar el **diff** por sección, con una línea de por qué.
2. Con confirmación explícita:
   - Si la persona tiene permiso de edición: aplicar la edición.
   - Si no (lo normal fuera del team): publicarlo como respuesta en el mismo tema, con el diff, para que el team lo aplique.
