---
name: presentaciones
description: Armar o editar una presentación de Criptonautas como un HTML que se abre sin internet. Usar cuando se pidan diapositivas, una charla o una presentación para la comunidad.
---

# Presentaciones

Aplicar antes `identidad-visual` y, para el texto, `voz-del-foro`.

## 1. La herramienta

Repo **[criptonautas-slides](https://github.com/somos-criptonautas/criptonautas-slides)**: `build.py` arma cada carpeta de presentación en un `deck.html` con la tipografía embebida. Buscar primero una copia local; si no hay, clonarlo. Solo necesita Python 3.

## 2. Una presentación nueva

1. Copiar `example/how-it-works` a una carpeta con nombre en inglés, en minúsculas y con guiones. Puede vivir fuera del repo: las presentaciones internas no se suben.
2. `deck.json` define `title`, `order`, `sections` y `variants`; cada diapositiva es `slides/<id>.html`, un `<section id="<id>">` de 1920 × 1080, con las notas en `<aside>`. Los `id` van en inglés.
3. Imágenes en `img/`, referidas como `img/file`.
4. `python3 build.py <carpeta>`; abrir el HTML y mostrar la vista previa antes de dar la presentación por terminada.

## 3. Caras

Antes de poner una foto en `img/`, tapar las caras con `cover_faces.py` de [criptonautas-pdf](https://github.com/somos-criptonautas/criptonautas-pdf): `python3 cover_faces.py photos img`. La detección solo sugiere: revisar cada `<photo>.check.jpg` y cada imagen de `img/`, y agregar a mano en `photos/<photo>.faces.json` las caras que falten. `photos/` no se sube ni se comparte.

## 4. Nombres

**Nombres de archivos, carpetas, `id` de diapositivas, claves de `deck.json`, variables y mensajes del código: en inglés, nunca en español.** El español queda para el contenido de las diapositivas y la documentación para quien las usa.

## 5. Reglas

- Una idea por diapositiva; el texto largo va a las notas.
- El HTML funciona sin red: nada de fuentes, scripts ni imágenes externas.
- El texto de otra persona no se reescribe sin su aprobación.
- Imágenes sin metadatos; sin figuras de autoridad ni gurús.
- Sin cifras de ganancia ni promesas de rendimientos.
