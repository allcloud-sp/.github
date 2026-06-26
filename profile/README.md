# AllCloud — Extensión para Visual Studio Code

Extensión interna para gestionar repositorios de la organización `allcloud-sp` directamente desde Visual Studio Code.

---

# 📦 Instalación

## 🧩 1. Git (obligatorio)

**Windows (Winget)**

```bash
winget install --id Git.Git -e --source winget
```

### 🔐 Configuración de Git

```bash
git config --global user.name "Tu Nombre"
```

```bash
git config --global user.email "tu@email.com"
```

---

## 🧩 2. GitHub CLI (obligatorio)

**Windows (Winget)**

```bash
winget install --id GitHub.cli
```

### 🔐 Login en GitHub CLI

```bash
gh auth login
```

#### Seleccionar:
- GitHub.com
- HTTPS
- Login vía navegador (recomendado)

---

## 🧩 3. Extensión Visual Studio Code (.vsix)

Para usuarios de Visual Studio Code, existe una extensión en formato `.vsix` que integra la gestión de repositorios de la organización directamente en el editor.

### 📦 Descarga del VSIX

Descargar la última versión desde:

https://github.com/allcloud-sp/080-allcloud-extension-vscode/releases

### 📥 Instalación de la extensión

#### Opción 1: Desde VS Code
1. Abrir Visual Studio Code
2. Ir a **Extensions** (panel lateral)
3. Hacer clic en el menú `···`
4. Seleccionar **Install from VSIX...**
5. Elegir el archivo `.vsix` descargado

#### Opción 2: Desde la terminal

```bash
code --install-extension allcloud-github-X.X.X.vsix
```

---

## ⚙️ Funciones de la extensión

La extensión añade 4 comandos accesibles desde la **Paleta de comandos** (`Ctrl+Shift+P` / `Cmd+Shift+P`), buscando `AllCloud`:

---

### 🆕 AllCloud: Nuevo repositorio

Crea un nuevo repositorio en la organización `allcloud-sp` a partir del workspace actualmente abierto en VS Code.

**Pasos guiados:**

| Paso | Descripción |
|------|-------------|
| **1 / 4 — Tipo** | Selecciona el tipo de proyecto (`020` para Business Central / NAV, `080` para el resto) |
| **2 / 4 — Cliente** | Selecciona el cliente de la lista (se carga automáticamente desde el servidor) |
| **3 / 4 — Nombre del proyecto** | Escribe el nombre del proyecto (mínimo 2 caracteres). Se normaliza automáticamente: minúsculas, sin espacios, sin caracteres especiales |
| **4 / 4 — .gitignore** | Elige la plantilla de `.gitignore` a aplicar (`Business Central` o sin .gitignore) |

**Qué hace internamente:**

1. Verifica que GitHub CLI esté autenticado
2. Comprueba que el repositorio no exista ya en la organización
3. Avisa si el workspace ya contiene un repositorio git
4. Crea el archivo `.gitignore` según la plantilla elegida
5. Inicializa git localmente (`git init`, rama `main`, commit inicial)
6. Crea el repositorio remoto privado en `allcloud-sp` con el equipo asignado según el tipo
7. Hace push a `origin/main`
8. Muestra enlace directo al repositorio en GitHub

> El nombre final del repositorio sigue el formato: `tipo-cliente-proyecto` (ej: `080-allcloud-myapp`)

---

### 📥 AllCloud: Clonar repositorio de la org

Clona un repositorio existente de la organización `allcloud-sp` en tu equipo.

**Pasos:**

1. Carga la lista de hasta 200 repositorios de la organización
2. Permite buscar y seleccionar el repositorio deseado (búsqueda por nombre y descripción)
3. Elige el destino de la clonación:
   - Carpeta del workspace activo
   - Carpeta personal (`~`)
   - Otra carpeta (explorador de archivos)
4. Clona el repositorio
5. Ofrece abrirlo en la misma ventana o en una nueva

> Si la carpeta de destino ya existe, pregunta si quieres abrirla directamente.

---

# 📦 Normas de repositorios de la organización

Este documento define la **nomenclatura obligatoria** y reglas básicas para la creación de repositorios.

---

# 🏷️ Nomenclatura obligatoria

Todos los repositorios deben seguir este formato:

```
tipo-cliente-proyecto
```

---

## 🔤 Componentes del nombre

### 1. tipo (obligatorio)

Define el tipo de repositorio:

- `020` → Microsoft Business Central / NAV
- `080` → Todo el resto

---

### 2. cliente (obligatorio)

Nombre corto del cliente o sistema:

- `pool`
- `aquarium`
- `allcloud` — si el proyecto es interno

---

### 3. proyecto (obligatorio)

Descripción breve del objetivo:

- `finanzas`
- `tpv`
- `edi`
- `informes`

---

### Ejemplos válidos

```
020-allcloud-finanzas
080-pool-tpv
080-aquarium-informes
```

---

# ⚠️ Reglas importantes

- Todo en **minúsculas**
- Separado por **guiones** (`-`)
- Sin espacios
- Sin versiones en el nombre
