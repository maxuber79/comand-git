# 🧠 Guía Rápida GIT — WEBMAIN Edition 💻

Documentación base para configurar, iniciar y trabajar con repositorios GIT.
Incluye comandos esenciales, tips útiles y algunos atajos pro pa’ devs con estilo. 😎

---

## 🔗 Menú Rápido

* [Configuración Básica](#%EF%B8%8F-configuraci%C3%B3n-b%C3%A1sica)
* [Alias Útiles](#-alias-%C3%BAtiles)
* [Iniciando un Repositorio](#-iniciando-un-repositorio)
* [GIT ADD](#-git-add)
* [GIT COMMIT](#-git-commit)
* [GIT PUSH / PULL](#%EF%B8%8F-git-push--pull)
* [GIT LOG](#-git-log)
* [GIT DIFF](#-git-diff)
* [GIT RESET / HEAD](#-git-reset--head)
* [GIT BRANCH](#-git-branch)
* [GIT REBASE](#-git-rebase)
* [GIT REMOTE](#-git-remote)
* [GIT TAG](#%EF%B8%8F-git-tag)
* [Limpieza](#-limpieza)
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

## 🧯 Alias Útiles

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
