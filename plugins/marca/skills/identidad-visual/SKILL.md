---
name: identidad-visual
description: Aplicar la identidad visual de Criptonautas al generar cualquier pieza — PDF, presentación, placa, portada, tema, sitio o imagen. Usar antes de elegir colores, tipografías o poner el logo, y antes de escribir CSS de marca.
---

# Identidad visual

El sistema vive en **[brand-kit](https://github.com/somos-criptonautas/brand-kit)** y se publica en [criptonautas.co/kit](https://criptonautas.co/kit). Esta skill no repite sus valores: dice de dónde se leen y qué reglas los acompañan.

## 1. Los valores se leen, no se copian

Antes de escribir un color, traer el archivo vigente:

| Qué | Dónde |
|---|---|
| Paleta como variables CSS | `dist/color/paleta.css` — prefijo `--cn-`, con bloque de modo oscuro |
| Paleta como datos | `dist/color/tokens.json` — un objeto por token, con `light` y `dark` |
| Tema del foro | `dist/color/discourse.json` |
| Paleta para editores de imagen | `dist/color/paleta.gpl` |
| Tipografías con su licencia | `dist/tipografia/` |
| Logo, símbolo y lockup | `dist/logo/` — color, oscuro, una tinta y negativo |
| Plantillas de portada, banner y avatar | `dist/plantillas/` |

En una hoja de estilo: `@import` o copiar `paleta.css` al proyecto y usar las variables. En un script: leer `tokens.json`. **Un hexadecimal escrito a mano en el código es una copia que se va a desincronizar** — ya pasó entre los PDF de captación y el kit.

Los nombres en castellano son los del sistema y se usan al hablar de ellos: Violeta Tinta (Accent 1), Rojo Óxido (Accent 2), Ink, Paper, Halftone.

## 2. Reglas de color

1. **Accent 1 puede setear texto. Accent 2 no**, ni en negrita ni en mayúsculas chicas: no llega a 4,5:1 sobre Paper. Sirve para gráficos, filetes y tipografía grande.
2. **Nada debe parecer que emite luz.** Los acentos de modo claro se quedan en L\* ≤ 60. Un valor nuevo exige recalcular su contraste contra Paper y contra `#181719`.
3. **Separación en escala de grises ≥12 puntos** entre dos colores que carguen significado en la misma pieza — incluidos los dos colores de las figuras del símbolo.
4. **Los estados de error llevan ícono o rótulo**, porque error y Accent 2 comparten familia de tono.
5. **Modo oscuro usa dos violetas:** el claro para texto y enlaces, el vivo para formas, botones y símbolo. El de formas nunca setea texto.
6. En anotaciones sobre imagen: Accent 1 marca el sujeto de atención, Accent 2 el contraejemplo.

## 3. Tipografía

| Superficie | Titulares | Lectura | Interfaz, meta, epígrafes |
|---|---|---|---|
| Comunidad (Discourse) | Inter | Lato | Lato |
| Blog (Ghost) | Inter Tight | Lora | Inter Tight |

Dos familias por superficie, nunca tres. Un tercer rol monoespaciado se admite para cifras y etiquetas tracked en tablas y gráficos.

Escala de un solo ratio, **1.25**, desde el cuerpo de cada superficie: h1 2.44 em / 800, h2 1.95 em / 800, h3 1.56 em / 700, h4 1.25 em / 700, cuerpo 1 em / 400, chico 0.82 em, rótulos en mayúscula 0.72 em / 700 con +0.12 em de tracking.

Reglas que no se negocian: cuerpo nunca por debajo de 16 px en móvil ni 17 px en escritorio · largo de línea entre 45 y 75 caracteres, y en pantalla ancha se angosta el texto, no la imagen · interlínea 1,5–1,65 en lectura y 1,1–1,2 en titulares · tracking negativo solo en titulares de 24 px o más, positivo solo en rótulos cortos en mayúscula · **un nivel menor nunca se ve más grande que el siguiente** (un epígrafe o un extracto no supera al texto que acompaña) · cifras con `font-variant-numeric: tabular-nums` donde la fuente lo soporte.

## 4. El logo

- **El nombre es lettering propio** reconstruido sobre base Gotham. **Nunca se compone con una tipografía**, ni con las de este sistema. En una pieza entra como SVG desde `dist/logo/`.
- Cada versión —horizontal y solo símbolo— viene en color, oscuro, una tinta y negativo. Sobre fondo violeta va la negativa.
- Espacio libre alrededor: el diámetro de una cabeza del símbolo. Tamaño mínimo: 24 px el símbolo, 120 px el horizontal.
- No se redibuja, no se recolorea fuera de las variantes publicadas, no se le agrega sombra, contorno ni degradado, y no se estira.
- El splash del foro anima solo con `transform` y `opacity`: Discourse descarta SMIL.

## 5. Imágenes

Sin figuras de autoridad ni gurús: la comunidad se representa como pares, sin rostro central. Rostros reales solo con permiso de quien aparece. Nada generado que se presente como foto de la comunidad. El texto dentro de una imagen se rotula en el editor sobre una placa de Paper, no se genera con el modelo.

## 6. Salidas

- **Cero metadatos.** Sin `<title>`, `aria-label`, `<metadata>` ni comentarios en los SVG; sin chunks `tEXt`, `tIME`, `pHYs` ni `caBX` en los PNG; sin productor, creador ni fechas en los PDF.
- **Reproducible:** la misma fuente da el mismo archivo, byte a byte. Fechas fijas en los builds, nada de reloj ni azar.
- `dist/` y `docs/` del kit son generados: se edita `src/` y se corre `make`. Nunca se editan a mano.

## 7. Qué no está cerrado

Dos puntos siguen en revisión y conviene no inventarlos: el valor vigente de Accent 2 —el que manda es el de `tokens.json`, no el que pueda tener copiado una pieza vieja— y la tipografía de los PDF de captación. Referencias del método: `color-system-v02.md` y `typography-guidelines.md`.
