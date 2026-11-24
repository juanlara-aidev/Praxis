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
   - 11 skills activas de inicio (brief, prp, build-with-agent-team, bucle-agentico, praxis-init, graphify, infra-vps, frontend-design, playwright-cli, skill-creator y agent-praxis).
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

## ¿Usas Codex, Cursor, Windsurf o Copilot en vez de Claude?

No tienes que elegir ni cambiar nada. Cuando inicias Praxis en un proyecto, te deja **las dos carpetas listas desde el principio**:

- `.claude/` con `CLAUDE.md` — para **Claude Code**.
- `.agents/` con `AGENTS.md` — el estándar que entienden **OpenAI Codex, Cursor, Windsurf, GitHub Copilot y Amp**.

Las dos tienen las mismas skills y el mismo contexto, así que abres tu proyecto con el agente que prefieras y todo funciona igual, al mismo tiempo. No hay botón que presionar ni pasos en terminal.

> 💡 Tú trabajas sobre `.claude/` (y tu `CLAUDE.md`): es la copia principal. La carpeta `.agents/` se mantiene sola, en espejo, cada vez que Praxis actualiza algo.

> 💡 Al iniciar desde Launchpad, GLM y DeepSeek abren el **panel visual de Claude Code** ya configurado para ese modelo (tu llave vive cifrada en el editor, nunca en tu proyecto). Codex abre su terminal con las mismas conexiones. Praxis no toca la configuración global de tus agentes ni muestra secretos. Si una conexión no es compatible, Doctor te dice cuál fue omitida y cómo repararla.

---

## Perfiles de cuenta: trabaja con la cuenta de IA de cada cliente

Si trabajas para varios clientes y cada uno tiene su propia cuenta de Claude o de Codex, un **perfil** te deja usar la de cada quien sin mezclarlas. El trabajo de un cliente gasta en la cuenta del cliente, y el tuyo sigue gastando en la tuya. Tus skills, tus ajustes y tu historial de sesiones se comparten entre perfiles, así que no tienes que volver a configurar nada.

Si no creas ningún perfil, no cambia nada: Praxis se ve y funciona igual que siempre, con tu cuenta de siempre (aparece como **Predeterminado**).

### Cómo crear un perfil

1. Abre el menú **⋯** del panel de Praxis y elige **Cuentas de IA…**.
2. Elige **Crear perfil…** y ponle el nombre del cliente. Usa letras y números, mínimo 2 caracteres.
3. Listo. En la parte de arriba del panel aparece un botón con la inicial del perfil. Ahí vive todo lo demás.

### Cómo iniciar la sesión del cliente

Abre el botón del perfil y elige **Iniciar sesión en Claude** o **Iniciar sesión en Codex**:

- **Claude**: Praxis te muestra un enlace. Ábrelo en la computadora donde está la cuenta del cliente (puede ser la de otra persona), autoriza, copia el código que te da y pégalo en el cuadro que aparece. El código no se ve en pantalla.
- **Codex**: Praxis te muestra un enlace y un código corto. Abre el enlace, escribe el código y autoriza. Si te pide activar el código de dispositivo, se activa en la seguridad de la cuenta de ChatGPT.

Cuando termina, Praxis te avisa con el correo (enmascarado) y el plan de esa cuenta. Así sabes que entraste a la cuenta correcta.

### Si prefieres importar una sesión que ya existe

Con **Importar una sesión…** eliges si es de Claude o de Codex y señalas el archivo de la sesión. Praxis lo guarda en el perfil sin mostrártelo y te dice a qué cuenta pertenece. Si el archivo no es una sesión de ese programa, no se guarda nada.

### Cómo atar un proyecto a un perfil

Dentro del botón del perfil, elige **Usar siempre en este proyecto**. Desde ese momento, cada vez que abras esa carpeta, Praxis usa ese perfil sin que lo pidas. Esa atadura queda solo en tu computadora, no se escribe nada dentro del proyecto. Cuando quieras quitarla, usa **Desatar**.

### Cómo cambiar de perfil en 2 clics

Clic en el botón del perfil de arriba, clic en el perfil que quieres usar. El panel muestra el correo y el plan de cada cuenta, y las barras de uso son las de la cuenta que elegiste.

### Qué cubre y qué no

Un perfil cubre todo lo que Praxis lanza por ti: Claude y Codex desde el panel, los sub-agentes (los ayudantes que trabajan por ti), GLM y DeepSeek, el panel oficial de Claude Code (menos en Windows, ver abajo) y las terminales nuevas que abras en ese proyecto (las terminales son las ventanas donde se escriben comandos).

Lo que **no** cubre:

- **La extensión de Codex de VS Code.** Es de otra empresa y Praxis no puede cambiarle la cuenta. Sigue usando la cuenta de siempre.
- **El panel oficial de Claude en Windows.** Ahí usa siempre tu cuenta predeterminada, porque Windows no deja que Praxis le cambie la cuenta. La terminal y los agentes de Praxis sí usan el perfil. En Mac, Linux y WSL el panel oficial sí usa el perfil.
- **Las terminales que ya estaban abiertas.** Cierra esas terminales y abre una nueva después de cambiar de perfil.
- **La barra de uso de Codex con una cuenta de perfil.** Sale solo cuando Codex responde en ese momento. Si no responde, ves que está conectado, sin barras.

> 💡 Si en Windows ves que un ajuste que cambiaste dentro de un perfil no llega a tu cuenta de siempre, es normal: ahí algunos archivos se copian en vez de compartirse. Los cambios van de tu cuenta de siempre hacia el perfil, no al revés.

### Si algo no sale

- **"Todavía no encuentro Claude Code en esta computadora"**: lanza Claude desde el panel una vez y vuelve a intentar.
- **"Algunos archivos de este perfil chocan con los de tu cuenta principal"**: no se cambió ni se perdió nada. Cuéntame en SinergIA y lo revisamos.
- **Borrar un perfil** (**Borrar este perfil…**) elimina sus sesiones en esta computadora. Tus proyectos y tu cuenta de siempre no cambian.

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

- 💙 La **comunidad de SinergIA**: https://snrgia.ai
- 🐛 Para reportar bugs: [GitHub Issues del repo público](https://github.com/juanlara-aidev/praxis/issues)

---

Hecho por **Juan Lara** · Para la comunidad **SinergIA** 💙
