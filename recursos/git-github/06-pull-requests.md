# 06 - Pull Requests

## Objetivo de la clase

Comprender qué es un Pull Request, para qué sirve y cómo crearlo en GitHub para entregar el trabajo de forma ordenada.

Al finalizar esta clase, la estudiante deberá poder:

* Explicar qué es un Pull Request y para qué sirve.
* Crear un Pull Request en GitHub paso a paso.
* Identificar las partes de un Pull Request.
* Responder a los comentarios de revisión y subir correcciones.
* Integrar (hacer *merge*) el trabajo y limpiar la rama.

---

## 1. ¿Qué es un Pull Request?

Hasta ahora aprendiste a crear ramas, hacer commits y subir tus cambios a GitHub con `git push`. Pero subir una rama **no integra** tu trabajo a la rama principal (`main`). Falta un paso importante: el **Pull Request**.

Un Pull Request (o **PR**) es una **solicitud para integrar los cambios de una rama en otra** (normalmente de tu rama de tarea hacia `main`).

Cuando creas un PR le estás diciendo al equipo:

```txt
Terminé mi trabajo en esta rama.
Por favor revísenlo y, si está bien, intégrenlo a main.
```

El PR muestra de forma clara:

* Qué archivos cambiaron.
* Qué se agregó, modificó o eliminó (línea por línea).
* Una descripción escrita por ti explicando el cambio.

Esto permite que el docente o un compañero revise antes de que el cambio llegue a `main`. En este curso, **todas las tareas se entregan mediante un Pull Request**.

---

## 2. ¿Dónde encaja el Pull Request en el flujo?

El PR es el paso que conecta tu rama con la rama principal:

```txt
Crear rama  →  Hacer commits  →  git push origin tarea/...  →  Pull Request  →  Revisión  →  Merge
```

Recuerda: nunca se empuja directamente a `main`. Siempre se trabaja en una rama y se integra mediante un Pull Request.

---

## 3. Cómo crear un Pull Request paso a paso

### 1. Sube tu rama a GitHub

Primero asegúrate de haber subido tu rama de tarea:

```bash
git push origin tarea/nombre-de-la-tarea
```

### 2. Abre el repositorio en GitHub

Entra al repositorio del curso en GitHub. Después de hacer `push`, GitHub suele mostrar un aviso con un botón:

```txt
Compare & pull request
```

Haz clic en ese botón. Si no aparece, ve a la pestaña **Pull requests** y haz clic en **New pull request**.

### 3. Revisa la base y la rama a comparar

GitHub te mostrará algo como:

```txt
base: main  ←  compare: tarea/nombre-de-la-tarea
```

Esto significa: "quiero llevar los cambios de `tarea/nombre-de-la-tarea` hacia `main`". Verifica que la dirección sea la correcta.

### 4. Escribe un título y una descripción claros

* **Título:** corto y descriptivo. Ejemplo: `Agregar resumen de ramas y commits`.
* **Descripción:** explica qué hiciste y por qué. Ejemplo:

```txt
Agregué el archivo resumen-ramas-commits.md con las respuestas
de la práctica sobre ramas y commits.
```

### 5. Crea el Pull Request

Haz clic en **Create pull request**. Listo: tu trabajo queda publicado para revisión.

---

## 4. Partes de un Pull Request

| Parte             | Para qué sirve                                            |
| ----------------- | --------------------------------------------------------- |
| **Título**        | Resume el cambio en una frase                             |
| **Descripción**   | Explica qué se hizo y por qué                             |
| **base ← compare** | Indica desde qué rama y hacia qué rama van los cambios   |
| **Commits**       | Lista de los commits incluidos en el PR                   |
| **Files changed** | Muestra los cambios línea por línea                       |
| **Reviewers**     | Personas que revisarán el trabajo (en el curso, el docente) |
| **Conversation**  | Espacio para comentarios y respuestas                     |

---

## 5. Cómo responder a la revisión

Es normal que la persona que revisa deje comentarios o pida cambios. Esto **no es algo malo**: es parte del aprendizaje y del trabajo en equipo.

Para aplicar las correcciones **no necesitas crear un PR nuevo**. Solo:

1. Haz los cambios en tu computador, en la **misma rama**.
2. Guarda con un commit:

```bash
git add .
git commit -m "Aplicar correcciones de la revisión"
```

3. Sube los cambios a la misma rama:

```bash
git push origin tarea/nombre-de-la-tarea
```

El Pull Request se **actualiza automáticamente** con tus nuevos commits.

---

## 6. Merge y limpieza de la rama

Cuando la revisión es aprobada, los cambios se integran a `main` con el botón **Merge pull request** en GitHub.

Después del merge conviene actualizar tu copia local y limpiar la rama ya integrada:

```bash
git checkout main
git pull origin main
git branch -d tarea/nombre-de-la-tarea
```

Así tu `main` queda con los cambios integrados y eliminas la rama que ya cumplió su función.

---

## Buenas prácticas

* Sube tu rama con `git push` antes de intentar crear el PR.
* Verifica que la base sea `main` y la rama a comparar sea tu rama de tarea.
* Escribe títulos y descripciones claros: ayudan a quien revisa.
* Atiende los comentarios de revisión con calma y sin tomarlos como algo personal.
* Aplica las correcciones en la misma rama; no abras un PR nuevo.
* Después del merge, actualiza `main` y elimina la rama integrada.

---

## Errores comunes

* Crear el PR con la dirección invertida (`compare: main`).
* Olvidar hacer `git push` antes de abrir el PR (la rama no aparece en GitHub).
* Dejar título o descripción vacíos.
* Crear un PR nuevo para cada corrección en lugar de subir a la misma rama.
* Empujar directamente a `main` y saltarse el Pull Request.

---

## Resumen

Un Pull Request es la forma de **proponer y revisar** cambios antes de integrarlos a `main`. Es el puente entre tu rama de trabajo y la rama principal del proyecto.

En este curso entregarás cada tarea mediante un Pull Request: subes tu rama, abres el PR, recibes revisión, aplicas correcciones en la misma rama y, cuando todo está bien, se hace el merge.

---

## Actividad para el estudiante

1. Crea una rama de tarea y realiza al menos un commit.
2. Sube la rama con `git push origin tarea/...`.
3. Abre un Pull Request hacia `main` con un título y una descripción claros.
4. Comparte con el docente el enlace del Pull Request creado.
