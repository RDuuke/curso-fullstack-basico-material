# 03 - Comandos básicos de Git

## Objetivo de la clase

Aprender los comandos básicos de Git que se usarán durante el curso para revisar el estado del repositorio, guardar cambios, consultar historial y trabajar de forma ordenada.

Al finalizar esta clase, la estudiante deberá poder:

* Revisar el estado del repositorio.
* Identificar archivos modificados.
* Agregar archivos al área de preparación.
* Crear commits.
* Ver el historial de cambios.
* Entender el flujo básico de trabajo local con Git.

---

## 1. Antes de empezar

Para esta clase se debe tener listo:

* Git instalado.
* Git configurado con nombre y correo.
* Cuenta de GitHub activa.
* Repositorio del curso clonado.
* Visual Studio Code instalado.
* Repositorio abierto en Visual Studio Code.

Repositorio del curso:

```txt
https://github.com/RDuuke/curso-fullstack-basico-material
```

---

## 2. ¿Qué significa trabajar con Git?

Cuando trabajamos con Git, normalmente hacemos este ciclo:

```txt
Modificar archivos → Revisar cambios → Preparar cambios → Crear commit
```

En comandos, ese flujo básico se ve así:

```bash
git status
git add .
git commit -m "Mensaje del commit"
```

Más adelante también usaremos:

```bash
git push
git pull
```

Pero en esta clase nos enfocaremos primero en los comandos locales.

---

## 3. `git status`

El comando `git status` sirve para revisar el estado actual del repositorio.

```bash
git status
```

Este comando nos ayuda a responder preguntas como:

* ¿Estoy en la rama correcta?
* ¿Hay archivos modificados?
* ¿Hay archivos nuevos?
* ¿Hay cambios pendientes por guardar?
* ¿El repositorio está limpio?

Ejemplo de salida cuando no hay cambios:

```txt
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

Esto significa que no hay cambios pendientes.

---

## 4. Estados básicos de los archivos en Git

Un archivo puede estar en diferentes estados.

| Estado    | Significado                                     |
| --------- | ----------------------------------------------- |
| Untracked | Archivo nuevo que Git todavía no está siguiendo |
| Modified  | Archivo modificado                              |
| Staged    | Archivo preparado para commit                   |
| Committed | Cambio guardado en el historial                 |

Dicho de forma sencilla:

```txt
Untracked = Git ve el archivo, pero aún no lo controla.
Modified = El archivo cambió.
Staged = El archivo está listo para guardarse.
Committed = El cambio ya quedó guardado.
```

---

## 5. Crear un archivo de práctica

Para practicar, crear dentro del repositorio un archivo llamado:

```txt
practica-git.md
```

Contenido sugerido:

```md
# Práctica de Git

Estoy aprendiendo comandos básicos de Git.
```

Después de guardar el archivo, ejecutar:

```bash
git status
```

Git debería mostrar que existe un archivo nuevo.

---

## 6. `git add`

El comando `git add` sirve para preparar archivos antes de crear un commit.

Para agregar un archivo específico:

```bash
git add practica-git.md
```

Para agregar todos los cambios:

```bash
git add .
```

El punto `.` significa “agregar todos los cambios del directorio actual”.

Después de ejecutar `git add`, revisar nuevamente:

```bash
git status
```

Ahora el archivo debería aparecer como preparado para commit.

---

## 7. ¿Qué es el área de preparación?

Antes de crear un commit, Git nos permite seleccionar qué cambios queremos incluir.

Esa zona se llama **área de preparación** o **staging area**.

Flujo:

```txt
Archivo modificado → git add → Archivo preparado → git commit
```

Esto es útil porque no siempre queremos guardar todos los cambios en un mismo commit.

---

## 8. `git commit`

El comando `git commit` guarda los cambios preparados en el historial del repositorio.

Ejemplo:

```bash
git commit -m "Agregar práctica de comandos básicos"
```

La opción `-m` permite escribir el mensaje del commit.

Un commit debe tener un mensaje claro.

Buen ejemplo:

```bash
git commit -m "Agregar práctica de comandos básicos"
```

Mal ejemplo:

```bash
git commit -m "cambios"
```

Otro mal ejemplo:

```bash
git commit -m "asdf"
```

Los commits con mensajes claros ayudan a entender la historia del proyecto. Un commit llamado “cosas” es como dejar una nota en la nevera diciendo “eso”: nadie sabe qué pasó, pero todos sospechan.

---

## 9. Reglas para buenos commits

Un buen commit debería:

* Ser pequeño.
* Tener un propósito claro.
* Incluir cambios relacionados.
* Tener un mensaje entendible.
* Explicar qué se agregó, corrigió o modificó.

Ejemplos recomendados:

```bash
git commit -m "Agregar README inicial"
git commit -m "Crear guía de comandos básicos de Git"
git commit -m "Corregir explicación de git status"
git commit -m "Actualizar enlaces de recursos"
```

---

## 10. `git log`

El comando `git log` permite ver el historial de commits.

```bash
git log
```

Muestra información como:

* Identificador del commit.
* Autor.
* Fecha.
* Mensaje del commit.

Para ver el historial de forma corta:

```bash
git log --oneline
```

Ejemplo:

```txt
a1b2c3d Agregar práctica de comandos básicos
e4f5g6h Agregar README inicial del curso
```

Este comando es muy útil para revisar los cambios recientes.

---

## 11. `git diff`

El comando `git diff` muestra las diferencias entre lo que había antes y lo que se modificó.

```bash
git diff
```

Sirve para revisar cambios antes de agregarlos con `git add`.

Flujo recomendado:

```bash
git status
git diff
git add .
git commit -m "Mensaje claro"
```

Esto ayuda a evitar subir cambios por accidente.

---

## 12. `git restore`

El comando `git restore` permite descartar cambios en un archivo.

Ejemplo:

```bash
git restore practica-git.md
```

Esto devuelve el archivo al último estado guardado en Git.

Importante:

```txt
Usar git restore con cuidado, porque puede eliminar cambios locales que aún no se han guardado en un commit.
```

Si no estás segura de usarlo, primero revisar con:

```bash
git status
git diff
```

---

## 13. `git restore --staged`

Si agregaste un archivo con `git add`, pero quieres quitarlo del área de preparación, puedes usar:

```bash
git restore --staged practica-git.md
```

Esto no borra el archivo ni sus cambios.

Solo lo quita del estado `staged`.

Flujo:

```txt
Staged → git restore --staged → Modified
```

---

## 14. `git branch`

El comando `git branch` muestra las ramas disponibles en el repositorio.

```bash
git branch
```

La rama actual aparecerá marcada con un asterisco `*`.

Ejemplo:

```txt
* main
```

Más adelante usaremos ramas para cada tarea.

---

## 15. `git checkout`

El comando `git checkout` permite cambiar de rama.

Ejemplo:

```bash
git checkout main
```

También se puede usar para crear una nueva rama y cambiarse a ella:

```bash
git checkout -b tarea/comandos-basicos-git
```

Este comando crea una rama nueva llamada `tarea/comandos-basicos-git` y se mueve a ella.

---

## 16. `git switch`

Git también tiene un comando más moderno para cambiar de rama:

```bash
git switch main
```

Para crear una nueva rama:

```bash
git switch -c tarea/comandos-basicos-git
```

Durante el curso podemos usar `checkout` o `switch`, pero se explicará cuál usar en cada caso.

---

## 17. Flujo básico local

Cuando trabajamos localmente, el flujo básico será:

```bash
git status
git add .
git commit -m "Mensaje claro"
git log --oneline
```

Ejemplo completo:

```bash
git status
git add practica-git.md
git commit -m "Agregar práctica de comandos básicos"
git log --oneline
```

---

## 18. Comandos vistos en esta clase

| Comando                        | Descripción                              |
| ------------------------------ | ---------------------------------------- |
| `git status`                   | Muestra el estado del repositorio        |
| `git add archivo`              | Agrega un archivo al área de preparación |
| `git add .`                    | Agrega todos los cambios                 |
| `git commit -m "mensaje"`      | Guarda cambios en el historial           |
| `git log`                      | Muestra historial de commits             |
| `git log --oneline`            | Muestra historial resumido               |
| `git diff`                     | Muestra diferencias no preparadas        |
| `git restore archivo`          | Descarta cambios locales                 |
| `git restore --staged archivo` | Quita un archivo del área de preparación |
| `git branch`                   | Lista ramas                              |
| `git checkout rama`            | Cambia de rama                           |
| `git checkout -b rama`         | Crea y cambia a una rama                 |
| `git switch rama`              | Cambia de rama                           |
| `git switch -c rama`           | Crea y cambia a una rama                 |

---

## 19. Actividad guiada

Realizar los siguientes pasos:

1. Abrir el repositorio en Visual Studio Code.
2. Abrir la terminal.
3. Ejecutar:

```bash
git status
```

4. Crear un archivo llamado:

```txt
practica-git.md
```

5. Escribir dentro del archivo:

```md
# Práctica de Git

Estoy aprendiendo comandos básicos de Git.

## Comandos vistos

- git status
- git add
- git commit
- git log
```

6. Revisar el estado:

```bash
git status
```

7. Agregar el archivo:

```bash
git add practica-git.md
```

8. Crear commit:

```bash
git commit -m "Agregar práctica de comandos básicos"
```

9. Revisar historial:

```bash
git log --oneline
```

---

## 20. Tarea práctica

Crear un archivo llamado:

```txt
mis-comandos-git.md
```

Dentro del archivo, escribir con tus propias palabras qué hace cada comando:

```txt
git status
git add
git commit
git log
git diff
git branch
git checkout
```

También agregar una sección final respondiendo:

```txt
¿Cuál comando te pareció más importante y por qué?
```

---

## 21. Entregable

Enviar por Classroom:

* Captura del archivo `mis-comandos-git.md`.
* Captura de `git status`.
* Captura de `git log --oneline`.
* Explicación corta de qué aprendiste en esta práctica.

Más adelante esta tarea podrá entregarse mediante Pull Request.

---

## 22. Criterios de revisión

La actividad se considera completa si:

* El archivo `mis-comandos-git.md` existe.
* Explica los comandos con palabras propias.
* Se evidencia uso de `git status`.
* Se evidencia uso de `git log --oneline`.
* El commit tiene un mensaje claro.
* La entrega está ordenada.

---

## 23. Errores comunes

### Error: hice cambios pero Git no los muestra

Verifica que estés dentro de la carpeta del repositorio.

Ejecuta:

```bash
pwd
```

o en Windows:

```bash
cd
```

Luego revisa:

```bash
git status
```

---

### Error: hice `git add .` pero no quería agregar todo

Puedes quitar los archivos del área de preparación con:

```bash
git restore --staged .
```

Esto no elimina tus cambios, solo los quita del estado preparado.

---

### Error: escribí mal el mensaje del commit

Por ahora no vamos a modificar commits anteriores.

Lo importante es aprender a escribir mejor los próximos mensajes.

---

### Error: no sé si debo hacer commit

Una buena pregunta es:

```txt
¿Este cambio representa un avance claro que quiero guardar?
```

Si la respuesta es sí, probablemente puedes hacer commit.

---

## 24. Cierre de la clase

Los comandos básicos de Git son la base para trabajar de forma organizada.

Al principio puede parecer mucho, pero en la práctica diaria casi siempre repetimos el mismo ciclo:

```txt
Revisar → Agregar → Guardar
```

En comandos:

```bash
git status
git add .
git commit -m "Mensaje claro"
```

Cuando este flujo se vuelve natural, trabajar con Git deja de ser misterio y empieza a sentirse como guardar partida antes del jefe final.
