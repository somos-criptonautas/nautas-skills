---
name: wikis
description: Crear o editar wikis co-autoreadas de comunidad.criptonautas.co siguiendo sus plantillas (Conceptos, Guía paso a paso, Recursos, Experiencia). Usar cuando se pida escribir, ampliar, corregir o reordenar una wiki, guía o tutorial.
---

# Wikis

Aplicar primero la skill `voz-del-foro` (incluye leer la voz de quien escribe).

## 1. Buscar antes de crear

`discourse_search` con el tema y `tags:wiki`. Si ya existe una wiki sobre eso, se amplía; no se abre otra.

### Antes de redactar una wiki nueva

Si el pedido no lo aclara, preguntar una sola vez (máx. 4):

- para quién es: recién llegado o con experiencia;
- qué debería poder hacer después de leerla;
- qué ejemplo o experiencia propia aporta quien escribe;
- largo aproximado.

## 2. Dónde va

Una wiki **no va en la categoría wiki**: va en la categoría donde pertenece por tema (opsec, cripto, tech-apps…) con el tag **`wiki`**. El foro la muestra también en la vista de wiki.

Revisar qué tags admite esa categoría: Discourse descarta en silencio los que no permite. Si `wiki` no entra, avisar antes de publicar.

## 3. Elegir plantilla

Cada plantilla tiene su topic explicativo (leerlo si hay dudas). Secciones en este orden:

| Plantilla | Para qué | Secciones |
|---|---|---|
| **[Guía paso a paso](https://comunidad.criptonautas.co/t/wiki-guia-paso-a-paso-verificado/6880)** | Instrucción práctica con pasos y resultado verificable | intro · `[!tldr]` si es extensa · Objetivo esperado · Antes de empezar · `[!info]` advertencia · Paso a paso (`### 1`, `### 2`…) · Imágenes · Comprobación general · Problemas frecuentes · Data relacionada |
| **[Conceptos](https://comunidad.criptonautas.co/t/wiki-conceptos-de-que-se-trata/6881)** | Explicar un concepto o ideas que se confunden | intro · `[!tldr]` si es extensa · Qué es o qué explicamos · Por qué importa · Cómo funciona · Ejemplos y diferencias · Límites y excepciones · Imágenes · Data relacionada |
| **[Recursos](https://comunidad.criptonautas.co/t/wiki-recursos-ordenados-y-enlazados/6882)** | Herramientas, extensiones o enlaces agrupados | intro · Criterio de la lista · Recursos organizados (`###` por grupo) · Imágenes · Data relacionada |
| **[Experiencia](https://comunidad.criptonautas.co/t/wiki-experiencia-del-tropiezo-al-aprendizaje/6883)** | Vivencia de la comunidad: problema, solución, aprendizaje | intro · `[!tldr]` obligatorio, aprendizaje en una frase · Contexto general · Situación inicial y previa · Qué funcionó y qué no · Qué aprendimos · Imágenes · Data relacionada |

## 4. Formato

- **Intro** en texto plano, sin encabezado: 2–3 oraciones cotidianas antes de bajar a definiciones.
- **`[!info]` inicial** en wikis nuevas: aclara que es una guía inicial abierta a edición humana.
- **Secciones** con `###`. Subtítulos cortos (máx. ~8 palabras), no oraciones.
- **Secciones vacías** se borran, no quedan con "N/A".
- **Párrafos:** una idea por párrafo, aunque sea bajo el mismo subtítulo. No dejar un párrafo solo de una línea bajo un subtítulo: se une al anterior o falta contenido. Después de un callout, máx. 2 oraciones por párrafo.
- **Antes de empezar:** lista de requisitos sin enlaces; los enlaces van en el paso a paso o en Data relacionada.
- **Data relacionada:** enlaces inline `[Título descriptivo](url)`, sin etiquetas como "Foro:" o "Link oficial:".

## 5. Imágenes

El agente no sube archivos. Se proponen imágenes (repos oficiales, documentación técnica, capturas propias) y quien publica las sube como adjunto.

- Nada de hotlinks ni imágenes generadas por IA.
- Sin caption en la imagen; fuente al pie: `*Fuente: [nombre](url)*`.

## 6. Editar una wiki existente (co-autoría)

1. Leer el post completo con `discourse_read_post` (raw).
2. Cambiar solo lo necesario. No reescribir aportes de otras personas ni cambiar su tono; se corrige dato, formato o voz de comunidad.
3. Mostrar el **diff** (antes → después) por sección, con una línea de por qué.
4. Si el cambio es grande o discutible, proponerlo primero como respuesta en el topic.

## 7. Publicar y verificar

Borrador y confirmación, según `voz-del-foro`. Después de publicar, releer el post: callouts y tablas se rompen con facilidad.
