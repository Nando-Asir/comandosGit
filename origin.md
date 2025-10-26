# [Repositorio Github](README.md)

---

## Instalación de Git

```bash
sudo apt update
```
```bash
sudo apt policy git
```
```bash
sudo apt install git
```

---

## Creamos un repositorio en Github o hacemos Fork de otro usuario

### Si creamos uno en Github
Pinchamos `New Repository` y rellenamos los datos

### Si usamos el repositorio de otro usuario
Entramos en su repositorio y le damos a `Fork`, arriba a la derecha

---

## ⚙️ Configuración de Git

Configurar Git a nivel global en `/home/usuario`:

```bash
git config --global user.name "Tu Nombre"
```
```bas
git config --global user.email "tuemail@example.com"
```
```bash
git config --global init.defaultBranch main
```
La configuración se guarda en el archivo `.gitconfig`

### Ver la configuración
```bash
git config -l
```

---

## Clonar Proyecto

### 1. Clonamos el repositorio del proyecto
```bash
git clone https://github.com/usuario/nombreRepositorio
```
```bash
cd proyecto1/
```

### 2. Abrir VSCode
```bash
code .
```

### 3. Creamos una rama propia para trabajar
```bash
git branch nuevaRama
```

### 4. Cambiamos de rama
```bash
git switch nuevaRama
```

---

## Add y Commit

### 1. Crear el primer archivo
Crear `ejemplo1.txt`
```bash
echo "Este es el ejemplo1" > ejemplo1.txt
```

### 2. Ver el estado del proyecto
```bash
git status
```

### 3. Añadir el fichero al staging
```bash
git add .
```

### 4. Ver nuevamente el estado
```bash
git status
```

### 5. Hacer el primer commit
```bash
git commit -m "Creación de ejemplo1.txt"
```
Intentaremos utilizar un nombre descriptivo del contenido.
Se crea un Hash para identificarlo (ejemplo: `2fe5258`)

---

## Log - Historial de Commits

### Ver los commits
```bash
git log
```

### Crear un segundo archivo
Crear `ejemplo2.txt`
```bash
echo "Este es el ejemplo2" > ejemplo2.txt
```

### Añadir y hacer commit
```bash
git status
```
```bash
git add ejemplo2.txt
```
```bash
git commit -m "Añadimos el ejemplo2.txt"
```

### Ver el log actualizado
```bash
git log
```

Ahora tenemos dos estados en nuestra rama principal, con **nuevaRama** apuntando al último commit.

---

## Merge y Push

### 1. Cambiamos a la rama main
```bash
git switch main
```

### 2. Hacemos merge de la rama secundaria
```bash
git merge nuevaRama
```

### 3. Subimos los cambios a nuestro repositorio de Github
```bash
git push origin main
```
Siendo `origin` el nombre del repositorio de Github y `main` nuestro repositorio en local.

---

## Pull Request

### Le indicamos al usuario que hemos finalizado los cambios y le pedimos que acepte
Lo hacemos pinchando `Pull Request`.

Al usuario le llegará una notificación para que acepte los cambios.
