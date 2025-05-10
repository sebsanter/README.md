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
---

## 📘 Clase 3: Fusión de ramas y revisión de cambios

- `git merge --edit`: Permite editar mensaje de merge.
- `git merge --no-commit`: Realiza el merge sin hacer commit automático.
- `git branch -d <rama>`: Elimina una rama (si fue mergeada).
- `git branch -D <rama>`: Elimina una rama forzadamente.
- `git branch -a`: Lista todas las ramas locales y remotas.
- `git merge --no-ff`: Merge con commit explícito.
- `git reset --hard`: Resetea el repositorio a un estado anterior, eliminando cambios.
- `git diff`: Muestra diferencias entre archivos.

---
## 📘 Clase 4: GitHub y trabajo remoto

- `git remote add origin <url>`: Vincula el repositorio local con GitHub.
- `git config list`: Muestra la configuración actual.
- `git clone <url>`: Clona un repositorio remoto.
- `git push origin <rama>`: Empuja cambios a la rama remota.
- `git remote prune origin`: Limpia referencias remotas obsoletas.
- `git remote -v`: Muestra los remotos conectados.
- `git pull`: Trae y fusiona cambios del remoto.
- `git fetch`: Trae cambios del remoto sin fusionarlos.
- `git push -u`: Establece upstream para la rama.
- `git push -f`: Fuerza un push.
- `git push --all`: Empuja todas las ramas.
- `git push <rama1> <rama2>`: Empuja múltiples ramas.
- `git push -u origin <rama>`: Establece rama y empuja.
- ¿Qué es un Pull Request?: Solicitud para fusionar cambios a otra rama (usualmente en GitHub).

---
## 📘 Clase 5: Flujos de trabajo con ramas

- **Gitflow**:
  - `main`, `develop`, `feature`, `release`, `hotfix`
- **Otros flujos**:
  - GitHub Flow
  - Trunk Based Development
  - Ship Show Ask

---

## 📘 Clase 6: Buenas prácticas en Git

- Hacer commits con frecuencia lógica (al completar partes funcionales).
- Escribir mensajes de commit claros y concisos.
- Prefijos útiles para commits: `feat:`, `fix:`, `docs:`, `refactor:`, `style:`, etc.
- Nombrar ramas de forma descriptiva y coherente.
---

## 📘 Clase 7: Reescritura de historial y navegación avanzada

- `git reset --soft <SHA>`: Resetea manteniendo los cambios en staging.
- `git reset --hard <SHA>`: Resetea completamente al commit dado.
- `git reset --soft|hard HEAD~<N>`: Resetea a N commits atrás.
- `git checkout HEAD~<N>`: Navega a N commits atrás.
- `git checkout <SHA>`: Revisa un commit por su hash.

---

## 📘 Clase 8: Hooks, alias y herramientas avanzadas

- **Hooks**:
  - ¿Qué es un hook?
  - Hooks del lado del cliente y del servidor.
  - Creación de hooks personalizados.

- **Alias**:
  - `git config --global alias.co "checkout"`
  - `git config --global alias.st "status"`

- **Stash**:
  - `git stash`: Guarda cambios temporales.
  - `git stash -u`: Incluye archivos no trackeados.
  - `git stash pop`: Aplica y elimina el stash.

- **Cherry-pick**:
  - `git cherry-pick <SHA>`: Aplica un commit específico.

- **Bisect**:
  - `git bisect start`: Inicia búsqueda binaria de bugs.
  - `git bisect good`: Marca un commit como funcional.
  - `git bisect bad`: Marca un commit como con errores.
  - `git bisect reset`: Finaliza el proceso.

- Otros:
  - `git commit --amend -m "<nuevo mensaje>"`: Cambia el último mensaje.
  - `git checkout <SHA> <archivo>`: Recupera un archivo desde un commit específico.

---

## 📝 Apuntes Extra

- 💡 **Usar `git switch` en lugar de `checkout`** para cambiar de rama mejora la legibilidad.
- 🚨 **Evita usar `--force` (`-f`) en `push` a menos que sepas lo que estás haciendo**.
- 🧹 **`git stash` es ideal para guardar cambios temporales antes de hacer un pull o cambiar de rama**.
- 🔍 **`git bisect` es muy útil para encontrar el commit exacto que introdujo un bug**.
- 📄 **Siempre escribe mensajes de commit en infinitivo (e.g. `Agrega formulario`, `Corrige errores`)**.
- 🧭 **Crear ramas con prefijos como `feature/`, `fix/`, `hotfix/` mejora la organización**.
- 📌 **Si cometiste un error en tu último commit (mensaje o contenido), `git commit --amend` puede salvarte**.
