# 10 - Taller práctico de Git y GitHub

## Objetivo de la clase

Practicar de principio a fin el flujo de trabajo completo del curso, integrando todo lo aprendido en los temas anteriores: ramas, commits, push, Pull Request y resolución de conflictos.

Este taller funciona también como una **tarea entregable**. Más abajo encontrarás el objetivo, las actividades, el entregable y los criterios de revisión.

Al finalizar este taller, la estudiante deberá poder:

* Ejecutar el flujo de trabajo completo sin ayuda.
* Crear una rama, hacer commits claros y subirlos a GitHub.
* Crear un Pull Request y atender la revisión.
* Provocar y resolver un conflicto manualmente.
* Integrar el trabajo a `main` y limpiar la rama.

---

## Antes de empezar

Asegúrate de tener listo lo siguiente:

* Git instalado y configurado (ver tema 02).
* El repositorio del curso clonado en tu computador.
* Haber leído los temas 01 al 09.

Comprueba tu configuración:

```bash
git config --global user.name
git config --global user.email
```

---

## Paso 1. Actualiza la rama principal

Antes de crear cualquier rama, parte siempre de un `main` actualizado:

```bash
git checkout main
git pull origin main
```

---

## Paso 2. Crea tu rama de trabajo

Crea una rama con un nombre claro y descriptivo:

```bash
git checkout -b tarea/taller-git-github
```

Verifica en qué rama estás:

```bash
git branch
```

La rama actual aparece marcada con un asterisco (`*`).

---

## Paso 3. Realiza un cambio

Dentro de la carpeta del repositorio, crea un archivo llamado `taller.md` y escribe lo que aprendiste en este módulo. Por ejemplo:

```txt
# Mi taller de Git

En este módulo aprendí a usar ramas, commits, push, pull,
Pull Requests y a resolver conflictos.
```

---

## Paso 4. Revisa el estado y guarda con un commit

Revisa qué cambió:

```bash
git status
```

Prepara y guarda el cambio con un mensaje claro:

```bash
git add taller.md
git commit -m "Agregar taller con resumen del módulo de Git"
```

Haz al menos **dos commits** durante el taller (por ejemplo, agrega una segunda sección al archivo y vuelve a hacer `add` y `commit`).

---

## Paso 5. Sube tu rama a GitHub

```bash
git push origin tarea/taller-git-github
```

Recuerda: se sube la **rama de tarea**, nunca directamente `main`.

---

## Paso 6. Crea un Pull Request

1. Abre el repositorio en GitHub.
2. Haz clic en **Compare & pull request** (o ve a la pestaña **Pull requests** → **New pull request**).
3. Verifica que la dirección sea `base: main  ←  compare: tarea/taller-git-github`.
4. Escribe un título y una descripción claros.
5. Haz clic en **Create pull request**.

Si tienes dudas, repasa el tema 06 (Pull Requests).

---

## Paso 7. Provoca y resuelve un conflicto

Los conflictos son parte normal del trabajo en equipo. En este paso vas a provocar uno a propósito para practicar cómo resolverlo (ver tema 07).

1. Asegúrate de estar en tu rama de tarea y modifica la **primera línea** de `taller.md`. Por ejemplo, déjala así:

```txt
# Mi taller de Git (versión rama)
```

Guarda el cambio con un commit:

```bash
git add taller.md
git commit -m "Cambiar el título del taller en la rama"
```

2. Cámbiate a `main` y modifica **la misma primera línea** con un texto diferente:

```bash
git checkout main
```

```txt
# Mi taller de Git (versión main)
```

```bash
git add taller.md
git commit -m "Cambiar el título del taller en main"
```

3. Intenta integrar tu rama en `main`. Como ambas versiones cambiaron la misma línea, Git generará un conflicto:

```bash
git merge tarea/taller-git-github
```

4. Revisa los archivos en conflicto:

```bash
git status
```

5. Abre `taller.md`. Verás las marcas del conflicto:

```txt
<<<<<<< HEAD
# Mi taller de Git (versión main)
=======
# Mi taller de Git (versión rama)
>>>>>>> tarea/taller-git-github
```

6. Edita el archivo: elimina las marcas (`<<<<<<<`, `=======`, `>>>>>>>`) y deja únicamente el texto que quieres conservar. Por ejemplo:

```txt
# Mi taller de Git
```

7. Marca el conflicto como resuelto y finaliza el merge:

```bash
git add taller.md
git commit
```

8. Verifica que todo quedó en orden:

```bash
git status
git log --oneline
```

Si te trabas, repasa el tema 07 (Conflictos y cómo resolverlos).

---

## Paso 8. Atiende la revisión

Si el docente deja comentarios pidiendo cambios, aplícalos en la **misma rama**:

```bash
git add .
git commit -m "Aplicar correcciones de la revisión"
git push origin tarea/taller-git-github
```

El Pull Request se actualiza automáticamente.

---

## Paso 9. Integra y limpia

Cuando el Pull Request sea aprobado y se haga el merge, actualiza tu copia local y elimina la rama:

```bash
git checkout main
git pull origin main
git branch -d tarea/taller-git-github
```

---

## Lista de verificación

Marca cada punto cuando lo completes:

* [ ] Actualicé `main` antes de crear la rama.
* [ ] Creé una rama con un nombre claro (`tarea/...`).
* [ ] Hice al menos dos commits con mensajes descriptivos.
* [ ] Subí mi rama con `git push`.
* [ ] Creé un Pull Request hacia `main`.
* [ ] Provoqué y resolví un conflicto manualmente.
* [ ] Atendí los comentarios de la revisión (si los hubo).
* [ ] La rama se integró a `main` mediante el merge.

---

## Entregable

* Un Pull Request hacia `main` desde tu rama `tarea/taller-git-github`.
* El archivo `taller.md` con tu resumen del módulo.
* Al menos dos commits con mensajes claros.
* Un conflicto provocado y resuelto (captura del `git status` antes y después).

---

## Criterios de revisión

| Criterio                                              | Cumple |
| ----------------------------------------------------- | ------ |
| Trabajó en una rama (no directamente sobre `main`)    |        |
| Los mensajes de commit son claros y descriptivos      |        |
| La rama fue subida correctamente a GitHub             |        |
| El Pull Request tiene título y descripción claros     |        |
| La dirección del PR es correcta (`base: main`)        |        |
| Provocó y resolvió un conflicto correctamente         |        |
| Atendió los comentarios de la revisión                |        |

---

## Nota final

Este taller reúne todo el módulo de Git y GitHub. Si lograste completarlo de principio a fin, ya dominas el flujo de trabajo que usaremos durante el resto del curso. Lo importante no es memorizar los comandos, sino entender el flujo y repetirlo hasta que se vuelva natural.
