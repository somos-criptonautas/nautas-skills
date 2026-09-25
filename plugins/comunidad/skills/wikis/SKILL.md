---
name: wikis
description: Crear o editar wikis co-autoreadas en la categoría wiki de comunidad.criptonautas.co siguiendo sus plantillas (Conceptos, Guía paso a paso, Recursos, Experiencia). Usar cuando se pida escribir, ampliar, corregir o reordenar una wiki.
---

# Wikis

Aplicar primero la skill `voz-del-foro` (incluye leer la voz de quien escribe).

## 1. Buscar antes de crear

`discourse_search` con el tema y `#wiki`. Si ya existe una wiki sobre eso, se amplía; no se abre otra.

## 2. Elegir plantilla

Cada plantilla tiene su topic explicativo en el foro (leerlo si hay dudas). Las secciones van en este orden:

| Plantilla | Para qué | Secciones |
|---|---|---|
| **Conceptos** (topic 6881) | Explicar una idea | intro · `[!tldr]` si es extensa · Qué es o qué explicamos · Por qué importa · Cómo funciona · Ejemplos y diferencias · Límites y excepciones · Imágenes · Data relacionada |
| **Guía paso a paso** (6880) | Algo que se hace y se verifica | intro · `[!tldr]` si es extensa · Objetivo esperado · Antes de empezar · `[!info]` advertencia · Paso a paso · Imágenes · Comprobación general · Problemas frecuentes · Data relacionada |
| **Recursos** (6882) | Lista curada de enlaces | intro · Criterio de la lista · Recursos organizados · Imágenes · Data relacionada |
| **Experiencia** (6883) | Del tropiezo al aprendizaje | intro · `[!tldr]` aprendizaje en una frase · Contexto general · Situación inicial y previa · Qué funcionó y qué no · Qué aprendimos · Imágenes · Data relacionada |

Formato que produce el formulario, respetarlo al publicar por MCP:

- La **intro** es texto plano, sin encabezado: 2–3 oraciones cotidianas antes de bajar a definiciones.
- Los **callouts** abren con el marcador y el título en la misma línea: `> [!tldr] …`. El marcador no se repite en el título.
- Cada **sección** es un `###`.
- Secciones opcionales vacías se omiten, no se dejan con "N/A".

## 3. Editar una wiki existente (co-autoría)

1. Leer el post completo con `discourse_read_post` (raw).
2. Cambiar solo lo necesario. No reescribir aportes de otras personas ni cambiar su tono; se corrige dato, formato o voz de comunidad.
3. Mostrar el **diff** (antes → después) por sección, con una línea de por qué.
4. Si el cambio es grande o discutible, proponerlo primero como respuesta en el topic.

## 4. Publicar

Borrador y confirmación, según `voz-del-foro`. La wiki se crea en la categoría wiki con la plantilla elegida.
