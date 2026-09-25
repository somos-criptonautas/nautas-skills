---
name: glosario
description: Crear o editar términos del glosario de comunidad.criptonautas.co. Usar cuando se pida definir, agregar, corregir o ampliar un término (cripto, trading, privacidad, tecnología, sociedad).
---

# Glosario

Aplicar primero la skill `voz-del-foro` (incluye leer la voz de quien escribe).

El glosario lleva **descripciones simples y al grano**: definiciones breves y neutrales, que describen el uso, sin narraciones. Guías, paso a paso y tutoriales van en wikis (skill `wikis`). Principios completos en [[INFO] Sobre nuestro Glosario](https://comunidad.criptonautas.co/t/info-sobre-nuestro-glosario/2366).

## 1. Buscar antes de crear

`discourse_search` con `#glosario` y el término en sus variantes (español, inglés, sigla, nombre completo). Si existe, se edita o se amplía; no se duplica.

## 2. Formato de una entrada

**Categoría:** glosario.

**Título:** la palabra o sigla tal como se usa.

- Siglas: solo la sigla. `DCA`, no `DCA (Dollar Cost Averaging)`.
- Traducción o contexto entre paréntesis cuando ayuda a encontrarlo o desambigua: `Block Reward (Recompensa de bloque)`, `Cache (IA)`.

**Tag:** la primera letra del título, en minúscula (`d` para DCA). Se aplica automáticamente; después de publicar, verificar que esté. Títulos que empiezan con número llevan `-`.

**Cuerpo:** según lo que el término necesite.

- **Término simple:** 1–3 oraciones.
- **Término amplio:** 2–4 párrafos cortos, una idea por párrafo.
- Si es sigla, el cuerpo arranca con el nombre completo en negrita: `**Dollar Cost Averaging:** estrategia de…`.
- Opcional: cerrar con una frase de ejemplo en cursiva y entre comillas, como se diría en la comunidad.

```markdown
**Dollar Cost Averaging:** estrategia de acumulación que invierte una cantidad fija a intervalos regulares sin importar el precio.

Reduce el riesgo de mal timing, pero también puede promediar a la baja una posición perdedora, que multiplica la pérdida.
```

```markdown
Lo que recibe el minero que completa un bloque: monedas nuevas más las comisiones de sus transacciones. Se reduce a la mitad en cada halving — desde 2024 es de 3.125 BTC por bloque.

*"La recompensa baja a la mitad cada halving: menos emisión, oferta más escasa."*
```

## 3. Reglas

- Sin opinión dentro de la definición; si la comunidad tiene postura, va en la frase de ejemplo o con enlace a un topic del foro.
- Sin enlaces externos salvo que el término no se entienda sin ellos.
- Un dato que cambia con el tiempo (recompensa por bloque, fees, límites) lleva desde cuándo vale, para que se note si quedó viejo: "desde 2024 es de 3.125 BTC", no "es de 3.125 BTC".
- No editar el índice de [INFO] Sobre nuestro Glosario: se actualiza solo.

## 4. Publicar

Borrador y confirmación, según `voz-del-foro`.
