# Guía: Usar estilos CSS en Markdown con VS Code

## Requisitos previos

Antes de empezar, asegúrate de tener instalado:

- [Visual Studio Code](https://code.visualstudio.com/)
- La extensión **Markdown PDF** (autor: yzane)

---

## Paso 1 — Instalar la extensión Markdown PDF

1. Abre VS Code
2. Pulsa `Ctrl+Shift+X` para abrir el panel de extensiones
3. Busca `Markdown PDF`
4. Haz clic en **Instalar** en la extensión de **yzane**
5. Reinicia VS Code cuando lo pida

---

## Paso 2 — Crear la carpeta del proyecto

Crea una carpeta en tu ordenador para guardar tus documentos, por ejemplo:

```
Documentos/
└── mis-apuntes/
```

Abre esa carpeta en VS Code: **Archivo → Abrir carpeta**

---

## Paso 3 — Guardar los ficheros CSS

Dentro de la carpeta `mis-apuntes`, crea dos ficheros nuevos:

### `estilo-georgia.css`

```css
/* === Estilo Georgia para profesor de Tecnología === */

body {
  font-family: 'Georgia', serif;
  font-size: 15px;
  line-height: 1.75;
  color: #2c2c2c;
  max-width: 820px;
  margin: 40px auto;
  padding: 0 24px;
  background-color: #ffffff;
}

h1 {
  font-size: 26px;
  color: #1a3a5c;
  border-bottom: 3px solid #0077b6;
  padding-bottom: 8px;
  margin-bottom: 4px;
}

h2 {
  font-size: 19px;
  color: #0077b6;
  border-left: 4px solid #0077b6;
  padding-left: 10px;
  margin-top: 28px;
}

h3 {
  font-size: 16px;
  color: #1a3a5c;
  margin-top: 20px;
}

code, pre {
  font-family: 'Courier New', monospace;
  background: #e8f4fd;
  border: 1px solid #b0cde8;
  border-left: 4px solid #0077b6;
  border-radius: 4px;
  color: #1a3a5c;
}

code { padding: 2px 6px; font-size: 13px; }
pre  { padding: 12px 16px; overflow-x: auto; }

blockquote {
  border-left: 4px solid #b0cde8;
  margin: 16px 0;
  padding: 8px 16px;
  background: #f0f7fd;
  border-radius: 0 6px 6px 0;
  font-style: italic;
  color: #444;
}

table { width: 100%; border-collapse: collapse; margin: 16px 0; font-size: 14px; }
th    { background: #1a3a5c; color: #e8f4fd; padding: 9px 14px; text-align: left; }
td    { padding: 8px 14px; border-bottom: 1px solid #b0cde8; }
tr:nth-child(even) td { background: #f0f7fd; }

a {
  color: #0077b6;
  text-decoration: none;
  border-bottom: 1px dashed #0077b6;
}
```

### `estilo-times.css`

```css
/* === Estilo Times New Roman para profesor de Tecnología === */

body {
  font-family: 'Times New Roman', Times, serif;
  font-size: 15px;
  line-height: 1.75;
  color: #2c2c2c;
  max-width: 820px;
  margin: 40px auto;
  padding: 0 24px;
  background-color: #ffffff;
}

h1 {
  font-family: 'Times New Roman', Times, serif;
  font-size: 26px;
  color: #1a3a5c;
  border-bottom: 3px solid #0077b6;
  padding-bottom: 8px;
  margin-bottom: 4px;
}

h2 {
  font-family: 'Times New Roman', Times, serif;
  font-size: 19px;
  color: #0077b6;
  border-left: 4px solid #0077b6;
  padding-left: 10px;
  margin-top: 28px;
}

h3 {
  font-family: 'Times New Roman', Times, serif;
  font-size: 16px;
  color: #1a3a5c;
  margin-top: 20px;
}

code, pre {
  font-family: 'Courier New', monospace;
  background: #e8f4fd;
  border: 1px solid #b0cde8;
  border-left: 4px solid #0077b6;
  border-radius: 4px;
  color: #1a3a5c;
}

code { padding: 2px 6px; font-size: 13px; }
pre  { padding: 12px 16px; overflow-x: auto; }

blockquote {
  font-family: 'Times New Roman', Times, serif;
  border-left: 4px solid #b0cde8;
  margin: 16px 0;
  padding: 8px 16px;
  background: #f0f7fd;
  border-radius: 0 6px 6px 0;
  font-style: italic;
  color: #444;
}

table { font-family: 'Times New Roman', Times, serif; width: 100%; border-collapse: collapse; margin: 16px 0; font-size: 14px; }
th    { background: #1a3a5c; color: #e8f4fd; padding: 9px 14px; text-align: left; }
td    { padding: 8px 14px; border-bottom: 1px solid #b0cde8; }
tr:nth-child(even) td { background: #f0f7fd; }

a {
  color: #0077b6;
  text-decoration: none;
  border-bottom: 1px dashed #0077b6;
}
```

Tu carpeta debe quedar así:

```
mis-apuntes/
├── estilo-georgia.css
├── estilo-times.css
└── mi-documento.md
```

---

## Paso 4 — Crear el fichero de configuración

Dentro de `mis-apuntes`, crea la carpeta `.vscode` y dentro de ella el fichero `settings.json`:

```
mis-apuntes/
├── .vscode/
│   └── settings.json   ← este fichero
├── estilo-georgia.css
├── estilo-times.css
└── mi-documento.md
```

Contenido inicial de `settings.json` (con Georgia activado):

```json
{
  "markdown-pdf.styles": ["./estilo-georgia.css"],
  "markdown-pdf.displayHeaderFooter": false
}
```

---

## Paso 5 — Exportar a PDF

1. Abre tu fichero `.md` en VS Code
2. Pulsa `Ctrl+Shift+P`
3. Escribe `Markdown PDF: Export (pdf)`
4. Pulsa `Enter`

El PDF se generará en la misma carpeta con el estilo aplicado. ✓

---

## Paso 6 — Cambiar de estilo

Para cambiar de Georgia a Times New Roman (o viceversa), abre `.vscode/settings.json` y edita la línea del estilo:

**Georgia:**
```json
{
  "markdown-pdf.styles": ["./estilo-georgia.css"]
}
```

**Times New Roman:**
```json
{
  "markdown-pdf.styles": ["./estilo-times.css"]
}
```

Guarda el fichero y vuelve a exportar el PDF. El cambio es inmediato.

---

## Resumen rápido

| Paso | Acción |
|------|--------|
| 1 | Instalar extensión **Markdown PDF** en VS Code |
| 2 | Crear carpeta del proyecto y abrirla en VS Code |
| 3 | Guardar `estilo-georgia.css` y `estilo-times.css` en la carpeta |
| 4 | Crear `.vscode/settings.json` apuntando al CSS elegido |
| 5 | Abrir el `.md` y exportar con `Ctrl+Shift+P` |
| 6 | Para cambiar de estilo, editar `settings.json` y reexportar |

---

> **Consejo:** Si usas documentos en varias asignaturas o cursos, puedes crear una carpeta por asignatura, cada una con su propio `.vscode/settings.json` y así tener estilos distintos sin interferencias.
