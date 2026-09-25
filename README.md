# nautas-skills

Skills y conexión a [comunidad.criptonautas.co](https://comunidad.criptonautas.co) para escribir, editar y publicar desde un agente de IA con la voz de la comunidad.

> [!NOTE]
> El agente trabaja con **nuestra propia cuenta** del foro. Puede hacer lo mismo que nuestro usuario, ni más ni menos: Discourse decide según nivel y grupos. Nunca publica sin mostrar antes el borrador y esperar un sí.

## Qué incluye

| Skill | Para qué |
|---|---|
| `voz-del-foro` | Tono y formato de la comunidad. Antes de escribir, lee nuestras últimas publicaciones para tomar nuestra voz. |
| `glosario` | Crear o editar términos del glosario sin duplicar. |
| `wikis` | Wikis co-autoreadas con las plantillas del foro (Conceptos, Guía, Recursos, Experiencia). |
| `curso` | Proponer o aplicar ediciones al curso respetando numeración, TL;DR y navegación. |

La conexión usa el [MCP oficial de Discourse](https://github.com/discourse/discourse-mcp). Este repo no guarda claves.

## Antes de empezar

- Cuenta activa en el foro.
- Node.js 18 o superior (para `npx`).
- Uno de estos agentes: Claude Code, opencode o pi.

## 1. Generar nuestra clave (una sola vez)

La clave queda en nuestra máquina, en `~/.config/nautas/discourse.json`.

```bash
mkdir -p ~/.config/nautas
```

```bash
npx -y @discourse/mcp@latest generate-user-api-key --site https://comunidad.criptonautas.co --save-to ~/.config/nautas/discourse.json
```

Abrir el enlace que aparece, aprobar en el foro y pegar el texto que devuelve. Si la clave se filtra, se revoca en el foro: Preferencias → Seguridad → Aplicaciones.

## 2. Instalar en nuestro agente

### Claude Code

Dentro de Claude Code:

```text
/plugin marketplace add criptonautas/nautas-skills
/plugin install comunidad@criptonautas
```

Reiniciar Claude Code. Skills y conexión quedan listas.

### opencode

```bash
git clone https://github.com/criptonautas/nautas-skills ~/nautas-skills
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
      "type": "local",
      "command": ["npx", "-y", "@discourse/mcp@latest", "--site", "https://comunidad.criptonautas.co", "--profile", "~/.config/nautas/discourse.json", "--allow_writes", "--tools_mode", "discourse_api_only"],
      "enabled": true
    }
  }
}
```

### pi

pi no trae MCP incorporado; se suma con [`pi-mcp-adapter`](https://github.com/nicobailon/pi-mcp-adapter).

```bash
pi install npm:pi-mcp-adapter
```

```bash
pi install git:github.com/criptonautas/nautas-skills
```

Sumar el bloque `comunidad` de [`plugins/comunidad/.mcp.json`](plugins/comunidad/.mcp.json) dentro de `mcpServers` en `~/.config/mcp/mcp.json` (si el archivo no existe, se copia tal cual). Reiniciar pi.

## 3. Cómo se usa

Se pide en lenguaje natural. Ejemplos:

- *"Sumá al glosario el término slippage."*
- *"Armá una wiki tipo guía paso a paso para verificar una descarga con GPG."*
- *"Revisá la wiki de redes de transferencia y proponé qué actualizar."*
- *"En el tema 2.2.2 del curso falta un ejemplo de retesteo falso en una lateral: proponé la edición."*
- *"Pasá este borrador a la voz del foro."*

El recorrido es siempre el mismo:

1. **Lee nuestra voz:** nuestras últimas publicaciones en el foro.
2. **Busca** si ya existe algo sobre el tema.
3. **Muestra el borrador** (o el diff, si es una edición), con categoría y tags.
4. **Espera un sí** explícito.
5. **Publica** y devuelve el enlace.

Si nuestro usuario no tiene permiso para editar algo (el curso, por ejemplo), el agente ofrece dejar la propuesta como respuesta en el tema para que el staff la aplique.

## Actualizar

- **Claude Code:** `/plugin marketplace update criptonautas`
- **opencode:** `git -C ~/nautas-skills pull`
- **pi:** `pi update --extensions`

## Proponer cambios a las skills

Las skills son texto en `plugins/comunidad/skills/*/SKILL.md`. Para mejorarlas: fork, cambio y pull request, o un tema en el foro con la propuesta. Criterio: menos es más, y cada regla nueva con un ejemplo real del foro.

## Licencia

[CC BY-NC-SA 4.0](LICENSE): se puede copiar, adaptar y compartir libremente, citando a Criptonautas, con la misma licencia y **sin uso comercial**. Lo libre no se vende.
