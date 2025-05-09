# REPOSITORIO DE GIT – Prácticas y Comandos Básicos
## 📘 Clase 1: Inicialización de un repositorio

- `git init`: Inicializa un nuevo repositorio Git en el directorio actual.

---

## 📘 Clase 2: Estados, commits y navegación

- `git status`: Verifica el estado actual del repositorio.
- `git add <archivo>`: Añade archivos al área de staging.
- `git commit`: Realiza un commit.
- `git commit -m "mensaje"`: Commit con mensaje en línea.
- `git restore --staged <archivo>`: Revierte el archivo del área de staging.
- `git add .`: Añade todos los archivos al staging.
- `git log`: Muestra el historial de commits.
- `git log --help`: Ayuda del comando log.
- `git log --oneline`: Historial reducido en una sola línea por commit.
- `git commit --amend -m "nuevo mensaje"`: Modifica el mensaje del último commit.
- `git checkout <rama|SHA>`: Cambia de rama o revisa un commit antiguo.
- `git switch <rama>`: Alternativa moderna a `checkout` para cambiar de rama.
- `git branch`: Lista ramas.
- `git switch -c <nueva-rama>`: Crea y cambia a una nueva rama.
