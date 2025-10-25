# Comandos de Git

---

## 🎯 Conocimientos Previos

Git trabaja con tres áreas principales:
- **Working Directory** (Directorio de trabajo)
- **Staging Area** (Área de preparación)
- **Repository** (Repositorio)

---

## 🔧 Instalación de Git

```bash
sudo apt update
sudo apt policy git
sudo apt install git
```

### Verificar versión
`git -v`


### Ayuda
```bash
git --h
```

---

## ⚙️ Configuración de Git

Configurar Git a nivel global en `/home/usuario`:

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tuemail@example.com"
```

La configuración se guarda en el archivo `.gitconfig`

### Ver la configuración
```bash
git config -l
```

---

## 🚀 Primer Proyecto: HolaGit

### 1. Crear la carpeta del proyecto
```bash
mkdir HolaGit
cd HolaGit/
```

### 2. Abrir VSCode
```bash
code .
```

### 3. Inicializar Git
```bash
git init
```

Se crea una carpeta `.git` donde se guarda la referencia de todo lo que hacemos.

---

## 📝 Add y Commit

### 1. Crear el primer archivo
Crear `hellogit.py` con el siguiente contenido:
```python
print("Hola")
```

### 2. Ver el estado del proyecto
```bash
git status
```

### 3. Añadir el fichero al staging
```bash
git add hellogit.py
```

### 4. Ver nuevamente el estado
```bash
git status
```

### 5. Hacer el primer commit
```bash
git commit -m "Este es mi primer commit"
```

Se crea un Hash para identificarlo (ejemplo: `2fe5258`)

---

## 📊 Log - Historial de Commits

### Ver los commits
```bash
git log
```

### Crear un segundo archivo
Crear `hellogit2.py`

### Añadir y hacer commit
```bash
git status
git add hellogit2.py
git commit -m "Este es mi segundo commit"
```

### Ver el log actualizado
```bash
git log
```

Ahora tenemos dos estados en nuestra rama principal, con **HEAD** apuntando al último commit.

---

## ↩️ Git Checkout - Descartar Cambios

### 1. Modificar archivos
Editar `hellogit.py` y `hellogit2.py`

### 2. Ver cambios detectados
```bash
git status
```

### 3. Descartar cambios en un archivo
```bash
git checkout hellogit2.py
```

Esto descarta los cambios y vuelve al estado anterior.

### 4. Descartar cambios en otro archivo
```bash
git checkout hellogit.py
```

### 5. Hacer una nueva modificación válida
Modificar `hellogit.py` con un nuevo cambio que sí queremos guardar.

### 6. Añadir y hacer commit
```bash
git add hellogit.py
git commit -m "Actualización del print"
```

### 7. Ver logs simplificados
```bash
git log --oneline
```

---

## 🚫 Gitignore - Ignorar Archivos

### 1. Crear el archivo .gitignore
```bash
touch .gitignore
```

### 2. Ignorar archivos temporales
Crear un archivo de prueba:
```bash
touch uno.tmp
```

### 3. Editar .gitignore
Añadir la siguiente línea:
```
**/*.tmp
```

Los dos asteriscos `**` indican "en cualquier directorio".

### 4. Verificar que funciona
```bash
git status
```

El archivo `uno.tmp` no aparece.

### 5. Añadir .gitignore al repositorio
```bash
git add .gitignore
git commit -m "Se añade el fichero .gitignore"
git status
```

---

## 🔄 Desplazamientos en el Historial

### Ver el historial
```bash
git log --oneline
```

### 1. Volver a un commit anterior
```bash
git checkout 6b44a72
```

Solo aparecerán los archivos existentes en ese punto del historial.

### 2. Ver dónde está HEAD
```bash
git log --oneline
```

**HEAD** indica dónde estamos apuntando ahora.

### 3. Mostrar todos los commits
```bash
git log --all --oneline
```

### 4. Volver al último estado
```bash
git checkout 46c3bdc
```

No es necesario poner el Hash completo, solo los primeros caracteres.

Todos los archivos vuelven a aparecer. Git almacena todos los cambios, eso es el **control de versiones**.

---

## 🎓 Conceptos Clave

- **Working Directory:** Donde trabajamos con nuestros archivos
- **Staging Area:** Donde preparamos los cambios antes de confirmarlos
- **Repository:** Donde se guardan todos los commits
- **HEAD:** Puntero que indica en qué commit estamos actualmente
- **Hash:** Identificador único de cada commit
- **.gitignore:** Archivo para excluir archivos del control de versiones

---

## 📚 Comandos Resumen

| Comando | Descripción |
|---------|-------------|
| `git init` | Inicializar repositorio |
| `git status` | Ver estado actual |
| `git add <archivo>` | Añadir archivo al staging |
| `git commit -m "mensaje"` | Confirmar cambios |
| `git log` | Ver historial de commits |
| `git log --oneline` | Ver historial simplificado |
| `git log --all --oneline` | Ver todos los commits |
| `git checkout <archivo>` | Descartar cambios |
| `git checkout <hash>` | Moverse a un commit |
| `git config -l` | Ver configuración |

---

**Nota:** Esta práctica nos permite entender cómo Git almacena y gestiona los cambios en nuestros proyectos, permitiéndonos viajar en el tiempo entre diferentes versiones del código.
