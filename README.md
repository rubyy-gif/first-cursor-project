# Cursor Extensions Guide (2026)

If you upgraded to a recent **Cursor** release and cannot find **View → Extensions**, you are not doing anything wrong. The UI changed. Extensions still exist; the menu path many VS Code tutorials use is often missing or hidden.

This guide explains what changed, how to open Extensions anyway, and how to install common AI extensions such as **Claude Code** and **Codex**.

---

## What changed in recent Cursor versions

Cursor is built on VS Code, but newer releases (especially with the **Glass** layout and **Cursor 3.x** / **Agents** window) reorganized the interface:

| What you might expect (VS Code) | What you may see in Cursor 3.x |
|--------------------------------|--------------------------------|
| **View → Extensions** in the menu bar | **Extensions** is often **not** listed under **View** |
| Extensions in the right “secondary” sidebar | Many extensions open as **editor tabs** or in the **left activity bar**, not beside chat |
| One familiar sidebar layout | **Agents window**, **Glass panels**, and a simplified or hidden menu bar |

**Important:** Extensions are not removed. Marketplace support remains. Only the **navigation path** changed.

References:

- [Cursor 3.0 changelog](https://cursor.com/changelog/3-0) — Agents window and interface updates
- [Cursor forum: extension sidebar changes (Glass)](https://forum.cursor.com/t/extension-no-longer-supported-in-second-sidebar/156491)

---

## How to open Extensions (when View → Extensions is missing)

Use any of these methods. They work even when the menu item is gone.

### 1. Keyboard shortcut (recommended)

| OS | Shortcut |
|----|----------|
| Windows / Linux | `Ctrl+Shift+X` |
| macOS | `Cmd+Shift+X` |

This opens the **Extensions** view directly.

### 2. Command Palette

1. Open the palette: `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (macOS)
2. Run one of:
   - `Extensions: Install Extensions`
   - `View: Show Extensions`
   - `Extensions: Show Installed Extensions`

### 3. Activity bar (left sidebar)

Click the **Extensions** icon (four squares, one detached).

If the icon is missing:

1. `Ctrl+Shift+P` / `Cmd+Shift+P`
2. Run `View: Reset View Locations`
3. Run `Developer: Reload Window`

### 4. Show the menu bar (if it is hidden)

On Windows, press **Alt** once to reveal the menu bar temporarily.

Or use the Command Palette:

- `View: Toggle Menu Bar`
- `Appearance: Toggle Menu Bar` (wording may vary by version)

Even with the menu bar visible, **Extensions may still not appear under View** in Cursor 3.x. Prefer **`Ctrl+Shift+X`**.

### 5. Install from the terminal (optional)

If the `cursor` CLI is on your PATH:

```powershell
# Windows (typical install path)
& "$env:LOCALAPPDATA\Programs\cursor\resources\app\bin\cursor.cmd" --install-extension anthropic.claude-code --force
& "$env:LOCALAPPDATA\Programs\cursor\resources\app\bin\cursor.cmd" --install-extension openai.chatgpt --force
```

```bash
# macOS / Linux (when `cursor` is in PATH)
cursor --install-extension anthropic.claude-code --force
cursor --install-extension openai.chatgpt --force
```

List installed extensions:

```bash
cursor --list-extensions
```

Reload after install: **Command Palette → `Developer: Reload Window`**.

---

## Install Claude Code and Codex

After you open Extensions (`Ctrl+Shift+X`), search and install:

| Extension | Publisher | Marketplace ID |
|-----------|-----------|----------------|
| **Claude Code for VS Code** | Anthropic | `anthropic.claude-code` |
| **Codex – OpenAI’s coding agent** | OpenAI | `openai.chatgpt` |

Marketplace links:

- [Claude Code](https://marketplace.visualstudio.com/items?itemName=Anthropic.claude-code)
- [Codex](https://marketplace.visualstudio.com/items?itemName=openai.chatgpt)

Sign in inside each extension with your **Anthropic** or **ChatGPT** account after installation.

### If Claude Code does not appear in Cursor search

Anthropic documents a dedicated **Install for Cursor** flow. Alternatives:

1. Use the marketplace link above and choose **Install** when prompted in Cursor
2. Command Palette → `Extensions: Install from VSIX` (if you have a `.vsix` file)
3. Run `claude` in the integrated terminal if the CLI is installed (extension optional for CLI-only use)

---

## Cursor Settings vs Extensions panel

Do not confuse these:

| Action | Opens |
|--------|--------|
| `Ctrl+Shift+X` | **Extensions** marketplace / installed list |
| `Ctrl+Shift+J` | **Cursor Settings** (account, models, import from VS Code) |

**Import from VS Code** (`Cursor Settings → General → Account`) copies extensions from VS Code; it does not replace the Extensions panel for browsing new extensions.

---

## Placing Claude Code / Codex on the right side (optional)

In Glass / Cursor 3.x, extension UIs often open as **editor tabs** instead of the old right auxiliary bar.

To pin an extension on the right:

1. Open the extension (it appears as a tab)
2. Drag the tab to the **far right edge** until you see a new editor group highlight, **or**
3. With the extension tab focused: Command Palette → `View: Move Editor into Right Group`

Optional setting in `settings.json`:

```json
"workbench.editor.openSideBySideDirection": "right"
```

---

## Troubleshooting

| Problem | Try |
|---------|-----|
| `Ctrl+Shift+X` does nothing | Confirm you are in the **IDE** window, not only the **Agents** window; switch with Command Palette → `Agents Window` / reopen the editor |
| Extension icon missing | `View: Reset View Locations` → `Developer: Reload Window` |
| Install succeeds but extension inactive | Reload window; check **Extensions → Installed** |
| `cursor` command not found | Command Palette → `Shell Command: Install 'cursor' command in PATH` (wording may vary) |

---

## Summary

- **Latest Cursor often has no View → Extensions menu item** — this is a UI change, not removal of extensions.
- Use **`Ctrl+Shift+X`** or the **Command Palette** to install and manage extensions.
- **Claude Code** (`anthropic.claude-code`) and **Codex** (`openai.chatgpt`) install like any other VS Code-compatible extension once the Extensions view is open.

---

## Contributing

Issues and pull requests are welcome if you find steps that differ on a specific Cursor version. Please include your **Cursor version** (Help → About) and **OS** when reporting.

## License

MIT
