# Praxis

> Hecho por **Juan Lara** · Para la comunidad **SinergIA**

---

## Antes de empezar

Necesitas dos cosas:

1. Un editor de código instalado: **VS Code**, **Cursor**, **Windsurf** o **Antigravity**.
2. Tu cuenta de SinergIA (la misma con la que entras a la comunidad).

Eso es todo.

---

## Instálala en 30 segundos

Copia el comando que corresponda a tu sistema, pégalo en una terminal y dale Enter. Descarga la extensión a una carpeta temporal de tu computadora y la instala automáticamente.

### En Windows (PowerShell)

```powershell
$tmp="$env:TEMP\praxis.vsix"; iwr "https://github.com/juanlara-aidev/praxis/releases/latest/download/praxis.vsix" -OutFile $tmp; code --install-extension $tmp --force
```

### En Windows (cmd.exe)

```cmd
curl -fL -o "%TEMP%\praxis.vsix" "https://github.com/juanlara-aidev/praxis/releases/latest/download/praxis.vsix" && code --install-extension "%TEMP%\praxis.vsix" --force
```

### En macOS o Linux

```bash
curl -fL -o /tmp/praxis.vsix "https://github.com/juanlara-aidev/praxis/releases/latest/download/praxis.vsix" && code --install-extension /tmp/praxis.vsix --force
```

> ¿Usas Cursor, Windsurf o Antigravity? Reemplaza `code` por `cursor`, `windsurf` o `antigravity` en el comando.

Cuando termine, recarga la ventana del editor: `Cmd/Ctrl + Shift + P` → escribe **Reload Window** → Enter.

---

## Tu primer uso, paso a paso

1. **Abre tu editor.** Vas a ver un nuevo ícono ⚡ en la barra lateral de la izquierda. Dale click — se abre el panel de Praxis.

2. **Inicia sesión con SinergIA.** El panel te muestra un botón **Sign in with SinergIA**. Dale click: se abre tu navegador, inicias sesión con tu cuenta de SinergIA (si ya tienes la sesión abierta, ni te lo pide) y el panel se desbloquea solo. Praxis confirma que tu membresía está activa y te abre el dashboard.

3. **Activa Praxis en tu proyecto.** Abre la carpeta donde quieres crear tu app (puede estar vacía o tener archivos previos). Apenas inicies sesión, el panel te muestra una pantalla de bienvenida con un solo botón grande **START** al centro. Dale click — Praxis prepara todo en menos de un minuto. Después de eso, esa pantalla desaparece para siempre y queda el dashboard normal.

4. **¡Listo!** En menos de un minuto Praxis te dejó:
   - El proyecto Next.js completo configurado.
   - Un archivo `CLAUDE.md` con instrucciones para que Claude trabaje en tu codebase.
   - 9 skills activas de inicio (brief, prp, build-with-agent-team, bucle-agentico, praxis-init, infra-vps, frontend-design, playwright-cli y skill-creator).
   - Conexiones automáticas con Next DevTools y Playwright.
   - Un `README.md` en la raíz con los siguientes pasos (`npm install`, configurar tu `.env.local`, `npm run dev`).

Después de eso, abre el `README.md` que te dejé y sigues los pasos. En SinergIA tienes los videos que te explican cada parte.

---

## Cómo se actualiza

Praxis se actualiza sola. En la parte de arriba del panel de Praxis siempre vas a ver un pequeño botón de **Actualizar**:

- Cuando estás al día, el botón aparece tenue (casi invisible).
- Cuando hay versión nueva, el botón se pone azul brillante con el número de la versión nueva.

En cualquiera de los dos casos, click en el botón → se descarga la versión más reciente → te ofrece recargar la ventana → listo. Tarda 5 segundos.

> 💡 ¿Algo raro pasa con la extensión? Dale click al botón de Actualizar aunque estés al día. Reinstala la última versión y arregla la mayoría de los problemas (archivos corruptos, ajustes que no se cargaron, lo que sea).

---

## ¿Prefieres usar Codex o Gemini en lugar de Claude?

Praxis trabaja con tres agentes de IA: **Claude Code** (por defecto), **OpenAI Codex** y **Google Gemini**. Cambias de uno a otro con un click.

En la parte de arriba del panel verás un botón nuevo (icono de dos flechas en X) entre el botón de Actualizar y el de Refrescar. Click en ese botón y aparece un menú con tres opciones. Eliges la que quieres y Praxis adapta tu proyecto al instante:

- Renombra `.claude/` a `.agents/` (Codex) o `.gemini/` (Gemini).
- Renombra `CLAUDE.md` a `AGENTS.md` o `GEMINI.md`.
- Reescribe las referencias internas de las skills para que apunten a la nueva carpeta.

Cero cambios manuales, cero pasos en terminal. Si después quieres volver a Claude, presionas el botón otra vez y todo regresa exacto como estaba.

> ✅ **El switch respeta tus ediciones**: si modificaste un archivo de Praxis, el switch lo renombra junto con la carpeta pero **no toca su contenido**. Solo se reescriben referencias internas en archivos que coinciden byte-exact con la copia que Praxis instaló. En tu `CLAUDE.md` raíz, las refs solo se traducen dentro de los marcadores `<!-- PRAXIS:*_START/END -->` que Praxis genera — cualquier prose tuya fuera de esos marcadores queda intacta.

> 💡 Las conexiones (MCPs) de `.mcp.json` siguen siendo de Claude Code. Para usar MCPs con Codex o Gemini, configúralos según la documentación oficial de cada proveedor — Praxis no los migra entre formatos.

---

## ¿Y si ya tengo un proyecto que estaba trabajando?

Praxis sabe distinguir cuándo tu carpeta está vacía y cuándo ya tienes archivos. Si abres un proyecto que ya tenía cosas tuyas (un `CLAUDE.md` propio, un `README.md`, código en `src/`, etc.):

- Praxis te pregunta antes de tocar nada.
- **No se sobrescribe ningún archivo que ya tengas.** Tu `CLAUDE.md`, tu `README.md`, tu código quedan intactos byte por byte.
- Solo te agrega lo que falta: las skills en `.claude/skills/` que no tengas y las conexiones (MCPs) en `.mcp.json` que no estén configuradas.

Es seguro probarlo en un proyecto que ya estés desarrollando.

---

## Si algo se rompió

### "No se reconoce el comando `code` (o `cursor`, `windsurf`, `antigravity`)"

El comando del editor no está en el sistema. Abre tu editor, pulsa `Cmd/Ctrl + Shift + P`, escribe **Shell Command: Install 'code' command in PATH** y dale Enter (la versión correspondiente para Cursor/Windsurf/Antigravity tiene el mismo nombre con su prefijo). Después abre una terminal nueva y vuelve a intentar el comando de instalación.

### "Extract: UNC host '...' access is not allowed"

Te aparece si estás corriendo Windows dentro de Parallels, VMware o WSL. La carpeta donde descargaste el archivo apunta al disco del Mac/Linux y el editor lo bloquea por seguridad. **La solución es usar el comando de la sección "Instálala en 30 segundos"** — descarga el archivo a `%TEMP%` (que es una carpeta local de Windows) y se instala desde ahí. Si seguiste otro camino, copia el archivo `praxis.vsix` a `C:\Users\<tu-usuario>\` y ejecuta `code --install-extension "C:\Users\<tu-usuario>\praxis.vsix" --force` desde ahí.

### Cualquier otra cosa

Cuéntame en SinergIA. La comunidad probablemente ya pasó por lo mismo.

---

## ¿Tienes dudas o ideas?

- 💙 La **comunidad de SinergIA** en Skool: https://www.skool.com/sinergia
- 🐛 Para reportar bugs: [GitHub Issues del repo público](https://github.com/juanlara-aidev/praxis/issues)

---

Hecho por **Juan Lara** · Para la comunidad **SinergIA** 💙
