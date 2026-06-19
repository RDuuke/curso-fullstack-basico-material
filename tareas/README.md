# Tareas

Esta carpeta contiene las **entregas de práctica** realizadas durante el curso.

Cada archivo corresponde a una tarea trabajada por la estudiante:

| Archivo | Tema |
| ------- | ---- |
| [practica-git.md](./practica-git.md) | Comandos básicos de Git |
| [flujo-push-pull.md](./flujo-push-pull.md) | Flujo de push y pull |
| [practica-ramas-commits.md](./practica-ramas-commits.md) | Ramas y commits |

---

## Instrucciones de las tareas

Las instrucciones formales (objetivo, actividades, entregable y criterios de revisión) se encuentran en los recursos del curso. El taller integrador del módulo de Git está en:

* [Taller práctico de Git y GitHub](../recursos/git-github/10-taller-practico-git-github.md)

---

## Cómo se entregan las tareas

Cada tarea se entrega mediante un **Pull Request**, siguiendo el flujo de trabajo del curso:

```bash
git checkout main
git pull origin main
git checkout -b tarea/nombre-de-la-tarea
# ... realizar los cambios ...
git add .
git commit -m "Mensaje claro del cambio"
git push origin tarea/nombre-de-la-tarea
```

Luego se crea el Pull Request desde GitHub. Si tienes dudas, repasa el recurso [Pull Requests](../recursos/git-github/06-pull-requests.md).
