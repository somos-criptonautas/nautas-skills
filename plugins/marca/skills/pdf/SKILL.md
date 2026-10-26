---
name: pdf
description: Generar o editar un documento PDF de Criptonautas (guía, material de captación, resumen para la comunidad) desde Markdown con la maqueta compartida. Usar cuando se pida un PDF o un documento para descargar o imprimir.
---

# PDF

Aplicar antes `identidad-visual` y, para el texto, `voz-del-foro`.

## 1. La herramienta

Repo **[criptonautas-pdf](https://github.com/somos-criptonautas/criptonautas-pdf)**: texto en `.md`, diseño en `style.css`, un `Makefile`. Buscar primero una copia local; si no hay, clonarlo. No se arma una maqueta nueva ni un script suelto: se usa el repo.

Requisitos: `pandoc` y `pip install -r requirements.txt`.

## 2. Un documento nuevo

1. Copiar `sample.md` con un nombre en inglés, en minúsculas y con guiones. `sample.pdf` es la guía: leerla antes de escribir.
2. Una idea por sección, `# Título` abre página. Bloques `:::` según la tabla del README: un `panel` por página, un `aparte` y un `cta` por documento.
3. Fotos en `photos/`, insertadas desde `img/`. Cada generación las copia a `img/` con las caras tapadas por la máscara de anonist y sin metadatos (`cover_faces.py`).
4. `make html` para revisar; mostrar la vista previa y esperar el sí antes de la versión final.
5. `make final`: PDF sin metadatos y huella en `SHA256SUMS`. `pdfinfo` no debe mostrar productor, creador ni fechas.

## 3. Caras

- Las caras se tapan siempre, de forma automática, antes de cualquier vista previa.
- La detección solo sugiere: se saltea perfiles y caras chicas, y marca cosas que no son caras. Abrir cada `<photo>.check.jpg` y cada imagen de `img/`; si falta una cara, agregarla a mano en `photos/<photo>.faces.json` (`[centro_x, centro_y, tamaño]` en píxeles) y regenerar.
- `photos/` nunca se sube al repo ni se comparte: solo `img/`.

## 4. Nombres

**Nombres de archivos, carpetas, scripts, variables, clases nuevas, targets y mensajes del código: en inglés, nunca en español.** El español queda para el contenido de los documentos y la documentación para quien los usa.

## 5. Reglas

- El texto de otra persona no se reescribe sin su aprobación; las correcciones se proponen aparte.
- Datos propios y verificables o fuentes independientes. Sin cifras de ganancia ni promesas de rendimientos.
- Una imagen por página como mucho; ninguna captura muestra datos personales.
- Antes de publicar, buscar `{` en el `.md`: una llave suelta es un enlace pendiente.
- Se publica en una historia de la comunidad, con el `.md` como fuente y la huella al lado.
