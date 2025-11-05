# 🧠 Guía Rápida GIT — WEBMAIN Edition 💻

![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
![.gitignore](https://img.shields.io/badge/.gitignore-File-red?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)
![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)

Documentación base para configurar, iniciar y trabajar con repositorios GIT.
Incluye comandos esenciales, tips útiles y algunos atajos pro pa' devs con estilo. 😎

---

## 🔗 Menú Rápido

* [Configuración Básica](#️-configuración-básica)
* [Alias Útiles](#-alias-útiles)
* [Iniciando un Repositorio](#-iniciando-un-repositorio)
* [GIT ADD](#-git-add)
* [GIT COMMIT](#-git-commit)
* [GIT PUSH / PULL](#️-git-push--pull)
* [GIT LOG](#-git-log)
* [GIT DIFF](#-git-diff)
* [GIT RESET / HEAD](#-git-reset--head)
* [GIT BRANCH](#-git-branch)
* [GIT REBASE](#-git-rebase)
* [GIT REMOTE](#-git-remote)
* [GIT TAG](#️-git-tag)
* [Limpieza](#-limpieza)
* [Alias GIT Personalizados](#-alias-git-personalizados--webmain-edition)
* [Tips WEBMAIN](#-tips-webmain)
* [Autor](#-autor)

---

## ⚙️ Configuración Básica

Configurar nombre que aparecerá en los commits:

```bash
git config --global user.name "Claudio (WEBMAIN)"
```

Configurar correo:

```bash
git config --global user.email "claudio.webmain@gmail.com"
```

Activar colores en la consola:

```bash
git config --global color.ui true
```

---

## 🧩 Alias Útiles

Crea alias cortos para tus comandos más usados:

```bash
git config --global alias.st "status -sb"
git config --global alias.cm "commit -m"
git config --global alias.br "branch"
git config --global alias.ch "checkout"
git config --global alias.lg "log --oneline --graph --decorate --all"
```

> 💡 Luego podís escribir por ejemplo `git st` o `git cm "mensaje"` en vez del comando largo.

---

## 🚀 Iniciando un Repositorio

Iniciar GIT en la carpeta del proyecto:

```bash
git init
```

Clonar un repositorio:

```bash
git clone <url>
```

Agregar todos los archivos:

```bash
git add .
```

Hacer el primer commit:

```bash
git commit -m "Primer commit inicial"
```

Subir cambios:

```bash
git push origin main
```

---

## 📦 GIT ADD

Agregar todos los archivos:

```bash
git add .
```

Agregar uno en específico:

```bash
git add <archivo>
```

Agregar por tipo:

```bash
git add *.js
```

Agregar por carpeta:

```bash
git add src/
```

---

## 💬 GIT COMMIT

Commit estándar:

```bash
git commit -m "Mensaje del commit"
```

Agregar y commitear directo:

```bash
git commit -a -m "Actualiza archivos"
```

Modificar el último commit (sin crear uno nuevo):

```bash
git commit --amend -m "Corrige mensaje o agrega archivos olvidados"
```

Borrar el último commit **manteniendo los cambios en staging:**

```bash
git reset --soft HEAD~1
```

Borrar el último commit **eliminando también los cambios:**

```bash
git reset --hard HEAD~1
```

---

## ☁️ GIT PUSH / PULL

Subir al repositorio remoto:

```bash
git push origin <branch>
```

Traer cambios del remoto:

```bash
git pull origin <branch>
```

Subir tags:

```bash
git push --tags
```

---

## 🕓 GIT LOG

Logs detallados:

```bash
git log
```

Vista resumida:

```bash
git log --oneline --graph --decorate --all
```

Ver commits recientes (limitados):

```bash
git log -n 5
```

---

## 🧮 GIT DIFF

Ver diferencias locales:

```bash
git diff
```

Ver diferencias staged:

```bash
git diff --staged
```

---

## 🧱 GIT RESET / HEAD

Sacar un archivo del commit:

```bash
git reset HEAD <archivo>
```

Revertir al commit anterior manteniendo cambios:

```bash
git reset --soft HEAD^
```

Revertir al commit anterior eliminando cambios:

```bash
git reset --hard HEAD^
```

Volver a un commit específico:

```bash
git reset --hard <commit_sha>
```

---

## 🌿 GIT BRANCH

Listar branches:

```bash
git branch
```

Crear branch:

```bash
git branch <nombre>
```

Cambiar de branch:

```bash
git checkout <nombre>
```

Eliminar branch:

```bash
git branch -d <nombre>
```

Forzar eliminación:

```bash
git branch -D <nombre>
```

---

## 🔄 GIT REBASE

Actualizar tu branch con los últimos cambios del main sin merge:

```bash
git fetch origin
git rebase origin/main
```

Resolver conflicto y continuar:

```bash
git rebase --continue
```

Abortar rebase:

```bash
git rebase --abort
```

---

## 🔗 GIT REMOTE

Agregar repositorio remoto:

```bash
git remote add origin <url>
```

Ver remotos configurados:

```bash
git remote -v
```

Cambiar URL remota:

```bash
git remote set-url origin <url>
```

Eliminar remoto:

```bash
git remote remove origin
```
## 🔎 RASTREO DE ARCHIVOS

Ver archivos no rastreados:

```bash
git ls-files --others --exclude-standard
```
Dejar de rastrear archivos en remoto

```bash
git rm --cached <archivo>
```
Nota: Esto elimina el archivo del repositorio pero lo mantiene en tu sistema local.

Estos comandos utilizan git rm --cached que:

Elimina los archivos del índice de Git (deja de rastrearlos)
NO elimina los archivos físicamente de tu directorio de trabajo
Los archivos seguirán existiendo localmente pero Git ya no los rastreará
Uso típico:

Después de agregar archivos al ![.gitignore](https://img.shields.io/badge/.gitignore-File-red?style=flat&logo=git&logoColor=white) y querer que Git deje de rastrear archivos que ya estaban siendo seguidos
Para eliminar archivos sensibles del repositorio remoto sin borrarlos localmente

---

## 🏷️ GIT TAG

Listar tags:

```bash
git tag
```

Crear tag anotado:

```bash
git tag -a v1.0 -m "Versión 1.0 estable"
```

Subir tags:

```bash
git push origin --tags
```

---

## 🧹 Limpieza

Eliminar branches eliminados en remoto:

```bash
git remote prune origin
```

Borrar archivo del repositorio:

```bash
git rm <archivo>
```

Revertir un merge o commit:

```bash
git log
git reset --hard <commit_sha>
```

---

## 🧩 Alias GIT Personalizados — WEBMAIN Edition

Estos son los alias configurados actualmente en tu entorno Git.
Sirven para ejecutar comandos largos con nombres cortos y rápidos ⚡

```bash
# 📄 Alias actuales (desde git-aliases.txt)
git st  →  git status -sb
git cm  →  git commit -m
git br  →  git branch
git ch  →  git checkout
git lg  →  git log --oneline --graph --decorate --all
```

---

## ⚙️ Cómo agregar alias de forma global

Los alias se guardan en el archivo global de configuración de Git (`~/.gitconfig`),
por lo que se aplican en **todos tus proyectos**.

### 🧠 Crear alias manualmente

Podés usar este formato en la terminal:

```bash
git config --global alias.<nombre> "<comando>"
```

Por ejemplo:

```bash
git config --global alias.st "status -sb"
git config --global alias.cm "commit -m"
git config --global alias.br "branch"
git config --global alias.ch "checkout"
git config --global alias.lg "log --oneline --graph --decorate --all"
```

> 💡 El flag `--global` los hace válidos para todos los repositorios.
> Si querís que el alias funcione solo en un proyecto, omití `--global`.

---

### 🧩 Ver tus alias configurados

Listar solo los alias:

```bash
git config --get-regexp alias
```

Ver toda tu configuración:

```bash
git config --list
```

Abrir el archivo global en VS Code:

```bash
code ~/.gitconfig
```

---

### 💾 Exportar tus alias a un archivo

Si querís guardarlos o documentarlos:

```bash
git config --get-regexp alias > git-aliases.txt
```

Y luego podés incluirlos o actualizarlos en tu README.md (como este 😎).

---

### Otros comandos útiles

Borrar carpeta node_modules:
```bash
rm -rf node_modules
```

Borrar archivo package-lock.json:
```bash
rm -f package-lock.json
```
Verificar si quedo limpio:
```bash
ls -l node_modules
```
Si quieres hacerlo en una sola línea (speedrun):
```bash
rm -rf node_modules && rm -f package-lock.json && ls -l node_modules
```

---







### 🔁 Importar alias desde archivo (opcional)

Si querís aplicar todos tus alias guardados en otro equipo:

1. Abrí tu `.gitconfig` con:

   ```bash
   code ~/.gitconfig
   ```
2. Pegá el bloque `[alias]` que tenías respaldado.
3. Guardá el archivo y ¡listo!
   Tus alias ya quedan activos globalmente.

---

## 💡 Consejo WEBMAIN

Si querís probar un alias antes de hacerlo global, podís crear uno temporal sin `--global`.
Si te gusta, lo promovís después con el flag global.
Así mantenís tu `.gitconfig` limpio y ordenado 🔥

---

## 🧠 Tips WEBMAIN

| Acción                                      | Comando                                 |
| ------------------------------------------- | --------------------------------------- |
| Ver el estado rápido                        | `git st`                                |
| Deshacer último commit (sin perder cambios) | `git reset --soft HEAD~1`               |
| Cambiar mensaje del último commit           | `git commit --amend -m "Nuevo mensaje"` |
| Alias rápido para log                       | `git lg`                                |
| Config global editable                      | `git config --global -e`                |
| Ver configuración actual                    | `git config --list`                     |

---

## 👨‍💻 Autor

**Claudio (WEBMAIN)**
*Publicista & Desarrollador Frontend*
🌍 Chile 🇨🇱 | 💡 Sello: “Código limpio, documentación clara, diseño con propósito.”
