# Recursos de Git y GitHub

Esta carpeta contiene el material de apoyo relacionado con **Git** y **GitHub**.

El objetivo de estos recursos es acompañar el aprendizaje paso a paso, desde los conceptos básicos hasta el flujo de trabajo con ramas, commits, push, pull y Pull Requests.

Estos documentos servirán como guía durante las clases, las prácticas y las tareas del curso.

---

## Objetivo de esta sección

Al finalizar esta sección, la estudiante deberá poder:

* Explicar qué es Git.
* Explicar qué es GitHub.
* Diferenciar entre repositorio local y remoto.
* Instalar y configurar Git.
* Usar comandos básicos de Git.
* Crear commits claros.
* Crear y cambiar entre ramas.
* Subir cambios a GitHub.
* Traer cambios desde GitHub.
* Comprender el flujo básico de trabajo del curso.

---

## Recursos disponibles

| Orden | Recurso                                                                   | Descripción                                                                                                                            |
| ----- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| 01    | [¿Qué es Git y qué es GitHub?](./01-que-es-git-y-github.md)               | Explicación inicial sobre Git, GitHub, repositorios, commits, push, pull, ramas y Pull Requests.                                       |
| 02    | [Instalación y configuración de Git](./02-instalacion-y-configuracion.md) | Guía para instalar Git, configurar nombre y correo, validar la instalación, aceptar la invitación al repositorio y clonar el proyecto. |
| 03    | [Comandos básicos de Git](./03-comandos-basicos.md)                       | Introducción práctica a comandos como `git status`, `git add`, `git commit`, `git log`, `git diff`, `git branch` y `git checkout`.     |
| 04    | [Flujo Push y Pull](./04-flujo-push-pull.md)                              | Explicación del flujo para sincronizar cambios entre el computador y GitHub usando `push` y `pull`.                                    |
| 05    | [Ramas y commits](./05-ramas-y-commits.md)                                | Guía para entender ramas, commits, nombres de ramas, mensajes de commit y buenas prácticas de trabajo.                                 |

---

## Orden recomendado de lectura

Se recomienda estudiar los recursos en este orden:

```txt
01 - ¿Qué es Git y qué es GitHub?
02 - Instalación y configuración
03 - Comandos básicos
04 - Flujo Push y Pull
05 - Ramas y commits
```

Cada archivo construye sobre el anterior, por eso es importante no saltarse pasos.

Git no se aprende leyendo una sola vez. Se aprende practicando, equivocándose y volviendo a hacer `git status` como si fuera una oración de protección.

---

## Flujo base del curso

Durante el curso usaremos este flujo para trabajar tareas y prácticas:

```bash
git checkout main
git pull origin main
git checkout -b tarea/nombre-de-la-tarea
```

Después de realizar cambios:

```bash
git status
git add .
git commit -m "Agregar solución de la tarea"
git push origin tarea/nombre-de-la-tarea
```

Luego se creará un Pull Request desde GitHub.

---

## Convención de ramas

Usaremos nombres de ramas claros y descriptivos.

Ejemplos:

```txt
tarea/resumen-git-github
tarea/comandos-basicos
tarea/flujo-push-pull
feature/listado-reservas
fix/corregir-validacion
docs/agregar-guia-git
```

---

## Buenas prácticas

Al trabajar con Git y GitHub, recuerda:

* Revisar siempre el estado con `git status`.
* Actualizar `main` antes de crear una rama.
* No trabajar directamente sobre `main`.
* Crear una rama por tarea.
* Hacer commits pequeños y claros.
* Escribir mensajes de commit descriptivos.
* Subir la rama con `git push`.
* Crear Pull Request para entregar cambios.
* Leer los mensajes de error con calma.

---

## Comandos principales

| Comando                       | Uso                                   |
| ----------------------------- | ------------------------------------- |
| `git status`                  | Ver el estado actual del repositorio  |
| `git add .`                   | Preparar todos los cambios            |
| `git commit -m "mensaje"`     | Guardar cambios en el historial       |
| `git log --oneline`           | Ver historial resumido                |
| `git pull origin main`        | Traer cambios desde GitHub            |
| `git push origin nombre-rama` | Subir cambios a GitHub                |
| `git branch`                  | Ver ramas                             |
| `git checkout -b nombre-rama` | Crear y cambiar a una rama            |
| `git checkout main`           | Cambiar a la rama principal           |
| `git diff`                    | Ver diferencias antes de hacer commit |

---

## Repositorio del curso

Repositorio principal de material de apoyo:

```txt
https://github.com/RDuuke/curso-fullstack-basico-material
```

---

## Nota final

Estos recursos serán la base para trabajar con Git y GitHub durante el curso.

No es necesario memorizar todos los comandos desde el inicio. Lo importante es entender el flujo y practicarlo muchas veces hasta que se vuelva natural.

La meta es que Git deje de sentirse como una caja negra y empiece a sentirse como una herramienta de trabajo diaria.
