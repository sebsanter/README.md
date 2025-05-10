# REPOSITORIO DE GIT – Prácticas y Comandos Básicos
## Conceptos Importantes
### Repositorio
Se puede ver como una carpeta donde se guarda lo que se necesite , en este caso apuntes
### Commits
Checkpoint
### Rama
Es un entorno que no afecta el el main(rama principal) a menos que se lo permitamos 
### Merge
Combina ramas y las añade al main pero hay riesgo de conflictos especialemente por no ser iguales cosa que pasa casi siempre 

## 📘 Clase 1: Inicialización de un repositorio

- `git init`: Inicializa un nuevo repositorio Git en el directorio actual.

---

## 📘 Clase 2: Estados, commits y navegación

- `git status`: Verifica el estado actual del repositorio.
- `git add <archivo>`: Añade archivos al área de staging.
- `git commit`: Realiza un commit.
- `git commit -m "mensaje"`: Commit con mensaje en línea.(crea un commit con un nombre elegido desde la terminal)
- `git restore --staged <archivo>`: Revierte el archivo del área de staging.
- `git add .`: Añade todos los archivos al staging.
- `git log`: Muestra el historial de commits.
- `git log --help`: Ayuda del comando log.
- `git log --oneline`: Historial reducido en una sola línea por commit.
- `git commit --amend -m "nuevo mensaje"`: Modifica el mensaje del último commit.(cambia el nombre del commit)
- `git checkout <rama|SHA>`: Cambia de rama o revisa un commit antiguo.
- `git switch <rama>`: Alternativa moderna a `checkout` para cambiar de rama.(cambia a
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
- `git clone <url>`: Clona un repositorio remoto.(esto se usa para hacer ediciones en el clonado y luego subirlas recien a github)
- `git push origin <rama>`: Empuja cambios a la rama remota.(sube la rama local a github)
- `git remote prune origin`: Limpia referencias remotas obsoletas.
- `git remote -v`: Muestra los remotos conectados.
- `git pull`: Trae y fusiona cambios del remoto.
- `git fetch`: Trae cambios del remoto sin fusionarlos.
- `git push -u`: Establece upstream para la rama.
- `git push -f`: Fuerza un push.
- `git push --all`: Empuja todas las ramas.
- `git push <rama1> <rama2>`: Empuja múltiples ramas.
- `git push -u origin <rama>`: Establece rama y empuja.
- ¿Qué es un Pull Request?: Solicitud para fusionar cambios a otra rama (GitHub).

---
## 📘 Clase 5: Flujos de trabajo con ramas

- **Gitflow**:
  - `main`(versiones), `develop`(codigo a probar y valiar), `feature`(caracteristicas nuevas), `release`(solo para emergencia), `hotfix`(parches
- **Otros flujos**:
  - GitHub Flow ( la mayoria de ramas salen del main y para mergearlas se usa la pull request)
  - Trunk Based Development(de acuerdo a lo investigado por mi es basicamente lo mismo que lo de arriba pero los commits son temporales y ya )
  - Ship Show Ask(Se fusiona en la rama principal sin revisión.-Abre una petición de cambios para que sean revisados por CI pero se fusiona inmediatamente-Abre una PR para discutir los cambios antes de fusionarlos).

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
    ejecutar una acción o script cada vez que ocurre un evento determinado de Git
  - Hooks del lado del cliente y del servidor.
    DEL CLIENTE
    se ejecutan solo en el repositorio local. Sirven para automatizar tareas o validaciones antes o después de ciertas acciones.

pre-commit: Se ejecuta antes de un commit. Útil para validar código o evitar commits con demasiados archivos.

prepare-commit-msg: Modifica o complementa el mensaje del commit antes de escribirlo.

commit-msg: Verifica el mensaje del commit una vez escrito (ideal para validar su formato).

post-commit: Corre después del commit. Útil para notificaciones (como enviar un mensaje a Slack).

pre-push: Se ejecuta antes de un push. Ideal para correr tests o verificaciones automáticas.

post-checkout y post-merge: Se usan para limpiar archivos temporales o ramas que ya no se usan después de cambiar de rama o hacer un merge.
  - Creación de hooks personalizados.
    DEL SERVIDOR
    Estos hooks se ejecutan en el repositorio remoto y permiten controlar lo que se acepta o se ejecuta al interactuar con él.

pre-receive: Se ejecuta antes de aceptar cambios. Sirve para validar commits y permisos del usuario que hace push.

update: Controla si se permite actualizar referencias (como ramas) de forma más específica. Útil para reglas avanzadas.

post-receive: Se ejecuta después de recibir los cambios. Se puede usar para enviar notificaciones por correo o actualizar interfaces gráficas con las nuevas ramas o commits.



- **Alias**:
es literalmente un "apodo por asi decirlo" para un comando , esto es para no estar escribiendo comandos largos sino simplificarlos como deseemos
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

