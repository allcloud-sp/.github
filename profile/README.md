# 📦 Instalación

## 🧩 1. GitHub CLI (obligatorio)

Windows (Winget)
winget install --id GitHub.cli

### 🔐 Login en GitHub

gh auth login


#### Seleccionar:  
-GitHub.com  
-HTTPS  
-Login vía navegador (recomendado)  

## 🧩 2. Extensión Visual Studio Code (.vsix)
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
