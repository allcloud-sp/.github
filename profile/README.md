# 📦 Instalación

## 🧩 1. Git (obligatorio)

Windows (Winget)  
```bash
winget install --id Git.Git -e --source winget
```

### 🔐 Configuración en Git

```bash
git config --global user.name "Tu Nombre"
```
```bash
git config --global user.email "tu@email.com"
```

## 🧩 2. GitHub CLI (obligatorio)

Windows (Winget)  
```bash
winget install --id GitHub.cli
```
### 🔐 Login en GitHub CLI
```bash
gh auth login
```

#### Seleccionar:  
-GitHub.com  
-HTTPS  
-Login vía navegador (recomendado)  

## 🧩 3. Extensión Visual Studio Code (.vsix)
  Para usuarios de Visual Studio Code, existe una extensión en formato .vsix que facilita:

  Creación de nuevos repositorios en GitHub
  Clonación de repositorios de la organización

### 📦 Descarga del VSIX

Descargar la última versión desde:

https://github.com/allcloud-sp/080-allcloud-extension-vscode/releases

### 📥 Instalación de la extensión

#### Opción 1: VS Code  
-Abrir Visual Studio Code  
-Ir a Extensions  
-Menú ...  
-Install from VSIX...  
-Seleccionar archivo  

#### Funciones de Visual Studio Code
- AllCloud: Nuevo repositorio  
- AllCloud: Clonar repositorio de la org


# 📦 Normas de repositorios de la organización

Este documento define la **nomenclatura obligatoria** y reglas básicas para la creación de repositorios.

---

# 🏷️ Nomenclatura obligatoria

Todos los repositorios deben seguir este formato: tipo-cliente-proyecto

---

## 🔤 Componentes del nombre

### 1. tipo (obligatorio)

Define el tipo de repositorio:

- `020` → Microsoft Business Central / NAV
- `080` → Todo el resto
  
---

### 2. cliente (obligatorio)

Nombre corto del cliente o sistema:

- pool
- aquarium
- allcloud `si el proyecto es interno`

---

### 3. proyecto (obligatorio)

Descripción breve del objetivo:

- finanzas
- tpv
- edi
- informes

---

# ⚠️ Reglas importantes

- Todo en minúsculas
- Separado por guiones (`-`)
- Sin espacios
- Sin versiones en el nombre
