# Diario de Aprendizaje - 1. Git

Registro de lo trabajado en clase con Git: configuracion inicial, flujo basico, ramas, deshacer cambios, repositorio remoto y etiquetas. Cada bloque incluye una breve explicacion y su ejemplo de codigo.

## 1. Configuracion inicial y creacion del repositorio

### git config --global user.name y user.email

Define la identidad que Git asocia a cada commit. Solo se configura una vez por equipo.

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu_correo@ejemplo.com"
```

### git init

Inicializa un repositorio Git nuevo en la carpeta actual.

```bash
git init
```

### git remote add y git remote -v

Vincula la carpeta local con el repositorio remoto y permite verificar que la conexion quedo registrada.

```bash
git remote add origin https://github.com/usuario/repositorio.git
git remote -v
```

### git branch -M main

Renombra la rama actual a `main`. Se usa al inicio para unificar el nombre de la rama principal.

```bash
git branch -M main
```

## 2. Flujo basico: guardar cambios

### git add

Anade los cambios al area de preparacion (staging) antes de confirmarlos.

```bash
git add archivo.txt
git add .
```

### git commit

Guarda los cambios preparados en el historial del repositorio con un mensaje descriptivo.

```bash
git commit -m "Descripcion del cambio"
```

### git commit --amend

Corrige el ultimo commit: permite cambiar el mensaje o agregar archivos olvidados sin crear un commit nuevo.

```bash
git commit --amend -m "Mensaje corregido"
```

### git push -u origin main

Sube los commits locales al repositorio remoto. La opcion `-u` establece la rama remota como referencia para futuros `push` y `pull`.

```bash
git push -u origin main
```

## 3. Consultar el historial y los cambios

### git log

Muestra el historial de commits del repositorio.

```bash
git log
git log --oneline
```

### git diff

Muestra las diferencias entre archivos modificados y lo confirmado en el ultimo commit.

```bash
git diff
```

## 4. Ramas y desplazamiento

### git checkout y git switch

Ambos permiten cambiar de rama. `checkout` es el comando clasico y tambien sirve para restaurar archivos. `switch` es el comando moderno, especifico para moverse entre ramas.

```bash
git checkout main
git switch main
git switch -c nueva-rama
```

## 5. Deshacer cambios

Cada comando actua en un nivel distinto. Es importante no confundirlos.

### git restore

Restaura archivos del area de trabajo o los saca del area de preparacion. Es la forma segura de descartar cambios sin tocar el historial.

```bash
git restore archivo.txt
git restore --staged archivo.txt
```

### git reset

Mueve el puntero de la rama a otro commit. Segun la opcion, mantiene o elimina los cambios.

```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```

### git revert

Crea un commit nuevo que deshace los cambios de un commit anterior. No borra el historial, por eso es seguro en ramas compartidas.

```bash
git revert <hash-del-commit>
```

### git clean

Elimina archivos no rastreados por Git (archivos nuevos que nunca se anadieron con `add`).

```bash
git clean -n
git clean -f
```

## 6. Etiquetas

### git tag

Marca un punto concreto del historial, normalmente una version.

```bash
git tag v1.0``
git tag
git push origin v1.0
```

## 7. Ramas

Crear ramas es algo necesario para tener una buena gestion de aplicacion y equipo.

```bash
git branch "<Nombre_Rama>"

```

- Cambiar rama:

```bash
git checkout "<Nombre_Rama>"
```
