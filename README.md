# nautas-skills

Skills y conexión a [comunidad.criptonautas.co](https://comunidad.criptonautas.co) para escribir, editar y publicar desde un agente de IA con la voz de la comunidad.

> [!NOTE]
> El agente trabaja con **nuestra propia cuenta** del foro. Puede hacer lo mismo que nuestro usuario, ni más ni menos: Discourse decide según nivel y grupos. Nunca publica sin mostrar antes el borrador y esperar un sí.

## Qué incluye

| Skill | Para qué |
|---|---|
| `voz-del-foro` | Tono y formato de la comunidad. Antes de escribir, lee nuestras últimas publicaciones para publicar o editar según nuestras convenciones, voz general y estilo personal. |
| `glosario` | Crear o editar términos del glosario sin duplicar, convenciones básicas aplicadas para mantener consistencia al publicar. |
| `wikis` | Wikis co-autoreadas con las plantillas del foro (Conceptos, Guía, Recursos, Experiencia). |
| `curso` | Proponer o aplicar ediciones al curso respetando numeración, TL;DR y navegación. |

La conexión usa el servidor MCP oficial de nuestro Discourse (`https://comunidad.criptonautas.co/mcp`). Cada persona entra con su propia cuenta por OAuth, desde un enlace: este repo no guarda claves ni accesos, todo se gestiona en el foro.

## Antes de empezar

- Cuenta activa en el foro.
- Uno de estos agentes: Claude Code, Claude Desktop, opencode o pi.

La primera vez que el agente usa el foro, abre un enlace para autorizar con nuestra cuenta. El acceso se revoca en el foro: Preferencias → Seguridad → Aplicaciones.

## Instalar en nuestro agente

### Claude Code

Dentro de Claude Code:

```text
/plugin marketplace add somos-criptonautas/nautas-skills
/plugin install comunidad@criptonautas
```

Reiniciar Claude Code, escribir `/mcp`, elegir `comunidad` y autorizar en el enlace. Skills y conexión quedan listas.

### Claude Desktop

1. **Conexión:** Configuración → Conectores → Agregar conector personalizado → URL `https://comunidad.criptonautas.co/mcp` → Conectar y autorizar.
2. **Skills:** descargar este repo, comprimir cada carpeta de `plugins/comunidad/skills/` en un `.zip` y subirla en Configuración → Capacidades → Skills.

### opencode

```bash
git clone https://github.com/somos-criptonautas/nautas-skills ~/nautas-skills
```

```bash
mkdir -p ~/.config/opencode/skills && ln -s ~/nautas-skills/plugins/comunidad/skills/* ~/.config/opencode/skills/
```

Sumar la conexión en `~/.config/opencode/opencode.json`:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "comunidad": {
      "type": "remote",
      "url": "https://comunidad.criptonautas.co/mcp",
      "oauth": {}
    }
  }
}
```

Autorizar:

```bash
opencode mcp auth comunidad
```

### pi

pi no trae MCP incorporado; se suma con [`pi-mcp-adapter`](https://github.com/nicobailon/pi-mcp-adapter), que además carga las skills de este repo.

```bash
pi install npm:pi-mcp-adapter
```

```bash
git clone https://github.com/somos-criptonautas/nautas-skills ~/nautas-skills
```

Sumar en `~/.config/mcp/mcp.json`, con la ruta completa (reemplazar `USUARIO`). Si el archivo ya existe, agregar solo `claudePlugins`:

```json
{
  "claudePlugins": [
    { "path": "/home/USUARIO/nautas-skills/plugins/comunidad", "mcp": true, "skills": true }
  ],
  "mcpServers": {}
}
```

Reiniciar pi y autorizar con `/mcp-auth comunidad`.

## Cómo se usa

Se pide en lenguaje natural. Ejemplos:

- *"Sumá al glosario el término slippage."*
- *"Armá una wiki tipo guía paso a paso para verificar una descarga con GPG."*
- *"Revisá la wiki de redes de transferencia y proponé qué actualizar."*
- *"En el tema 2.2.2 del curso falta un ejemplo de retesteo falso en una lateral: proponé la edición."*
- *"Pasá este borrador a la voz del foro."*

El recorrido es siempre el mismo:

1. **Lee nuestra voz y estilo:** nuestras últimas publicaciones en el foro.
2. **Busca en la comunidad** si ya existe algo sobre el tema.
3. **Muestra el borrador** (o el diff, si es una edición), con categoría y tags.
4. **Espera un sí** explícito.
5. **Publica** y devuelve el enlace para verificar.

SIEMPRE verificamos lo publicado, porque usamos la herramienta para agilizar y no para reemplazarnos. Somos una comunidad de humanos que usan herramientas, y eso no cambiará por utilizar IA.

Si nuestro usuario no tiene permiso para editar algo (el curso, por ejemplo), el agente ofrece dejar la propuesta como respuesta en el tema para que el staff la aplique.

## Cómo actualizar

- **Claude Code:** `/plugin marketplace update criptonautas`
- **opencode:** `git -C ~/nautas-skills pull`
- **Claude Desktop:** volver a subir los `.zip` de las skills que cambiaron
- **pi:** `git -C ~/nautas-skills pull`

## Proponer cambios a las skills

Las skills son texto en `plugins/comunidad/skills/*/SKILL.md`. Para mejorarlas: fork, cambio y pull request, o un tema en el foro con la propuesta. Criterio: menos es más, y cada regla nueva con un ejemplo real del foro.

## Créditos

Gracias a [KONVO](https://github.com/kirupa/KONVO), de Kirupa Chinnathambi. Adaptamos en nuestras palabras, sin copiar su texto, estas ideas:

- **`voz-del-foro`:** revisar sin reescribir (informe por gravedad con cita exacta y qué conservar), listar observaciones antes de reescribir, las pruebas de la versión aburrida y del trasplante, y la idea de una lista de muletillas (la lista en español es nuestra).
- **`wikis`:** preguntar antes de redactar una wiki nueva (para quién, qué debería poder hacer, experiencia propia, largo).

## Licencia

[CC BY-NC-SA 4.0](LICENSE): se puede copiar, adaptar y compartir libremente, citando a Criptonautas, con la misma licencia y **sin uso comercial**. En nuestra filosofía lo libre se comparte; comerciar, lo demás.
