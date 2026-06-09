# 04 - Flujo Push y Pull en GitHub

## Objetivo de la clase

Comprender cómo se sincronizan los cambios entre el computador y GitHub usando los comandos `push` y `pull`.

Al finalizar esta clase, la estudiante deberá poder:

* Entender qué es un repositorio local.
* Entender qué es un repositorio remoto.
* Diferenciar entre `push` y `pull`.
* Subir cambios desde el computador hacia GitHub.
* Traer cambios desde GitHub hacia el computador.
* Aplicar un flujo básico antes de empezar una tarea.
* Reconocer errores comunes al sincronizar cambios.

---

## 1. Repositorio local y repositorio remoto

Cuando trabajamos con Git y GitHub, normalmente tenemos dos versiones del repositorio:

| Tipo de repositorio | Dónde está       | Para qué sirve                             |
| ------------------- | ---------------- | ------------------------------------------ |
| Repositorio local   | En el computador | Es donde trabajamos y modificamos archivos |
| Repositorio remoto  | En GitHub        | Es donde se guarda una copia en internet   |

Dicho de forma sencilla:

```txt
Local = mi computador
Remoto = GitHub
```

Durante el curso trabajaremos en el repositorio local y luego enviaremos los cambios al repositorio remoto.

---

## 2. ¿Qué significa sincronizar?

Sincronizar significa mantener actualizado el repositorio local y el repositorio remoto.

Puede pasar que:

* Tú tengas cambios en tu computador que todavía no están en GitHub.
* GitHub tenga cambios que todavía no están en tu computador.
* Otra persona haya subido cambios al repositorio.
* El material del curso haya sido actualizado en GitHub.

Por eso necesitamos usar `push` y `pull`.

---

## 3. ¿Qué es `push`?

`push` significa subir cambios desde el computador hacia GitHub.

Se usa cuando ya hicimos commits locales y queremos enviarlos al repositorio remoto.

Flujo:

```txt
Computador → GitHub
```

Comando básico:

```bash
git push origin main
```

Significado:

| Parte      | Significado                        |
| ---------- | ---------------------------------- |
| `git push` | Subir cambios                      |
| `origin`   | Nombre del repositorio remoto      |
| `main`     | Rama a la que se suben los cambios |

Dicho de forma sencilla:

```txt
push = subir mis commits a GitHub
```

---

## 4. ¿Qué es `pull`?

`pull` significa traer cambios desde GitHub hacia el computador.

Se usa cuando queremos actualizar nuestro repositorio local con los cambios que están en el remoto.

Flujo:

```txt
GitHub → Computador
```

Comando básico:

```bash
git pull origin main
```

Significado:

| Parte      | Significado                        |
| ---------- | ---------------------------------- |
| `git pull` | Traer cambios                      |
| `origin`   | Nombre del repositorio remoto      |
| `main`     | Rama desde la que se traen cambios |

Dicho de forma sencilla:

```txt
pull = traer cambios desde GitHub
```

---

## 5. Diferencia entre `push` y `pull`

| Comando    | Dirección      | Uso                        |
| ---------- | -------------- | -------------------------- |
| `git push` | Local → Remoto | Subir cambios a GitHub     |
| `git pull` | Remoto → Local | Traer cambios desde GitHub |

Resumen:

```txt
push = yo envío cambios
pull = yo recibo cambios
```

Ejemplo cotidiano:

```txt
Push es como enviar una tarea.
Pull es como descargar la versión actualizada del material.
```

---

## 6. ¿Cuándo usar `pull`?

Se recomienda usar `pull` antes de empezar a trabajar.

Por ejemplo:

```bash
git checkout main
git pull origin main
```

Esto asegura que tu rama `main` esté actualizada antes de crear una nueva rama o hacer cambios.

Usaremos `pull` cuando:

* Iniciamos una clase.
* Vamos a comenzar una nueva tarea.
* El docente actualizó material.
* Queremos tener la última versión del repositorio.
* Antes de crear una rama nueva.

---

## 7. ¿Cuándo usar `push`?

Se usa `push` después de hacer commits.

Flujo típico:

```bash
git status
git add .
git commit -m "Agregar solución de tarea"
git push origin nombre-de-la-rama
```

Usaremos `push` cuando:

* Terminamos una tarea.
* Queremos subir nuestros commits a GitHub.
* Necesitamos crear un Pull Request.
* Queremos guardar una copia remota de nuestro trabajo.

---

## 8. Flujo recomendado antes de iniciar una tarea

Antes de empezar una nueva tarea, usaremos este flujo:

```bash
git checkout main
git pull origin main
git checkout -b tarea/nombre-de-la-tarea
```

Explicación:

1. Nos ubicamos en `main`.
2. Traemos la última versión desde GitHub.
3. Creamos una rama nueva para la tarea.

Ejemplo:

```bash
git checkout main
git pull origin main
git checkout -b tarea/flujo-push-pull
```

---

## 9. Flujo recomendado al terminar una tarea

Después de hacer cambios, usaremos este flujo:

```bash
git status
git add .
git commit -m "Agregar práctica de flujo push y pull"
git push origin tarea/flujo-push-pull
```

Explicación:

1. Revisamos qué cambió.
2. Agregamos los cambios.
3. Creamos un commit.
4. Subimos la rama a GitHub.

Luego se podrá crear un Pull Request.

---

## 10. ¿Qué es `origin`?

`origin` es el nombre que Git le da normalmente al repositorio remoto principal.

Cuando clonamos un repositorio desde GitHub, Git configura automáticamente ese remoto con el nombre `origin`.

Para ver los remotos configurados:

```bash
git remote -v
```

Ejemplo de salida:

```txt
origin  https://github.com/RDuuke/curso-fullstack-basico-material.git (fetch)
origin  https://github.com/RDuuke/curso-fullstack-basico-material.git (push)
```

Esto significa que el repositorio local está conectado al repositorio remoto de GitHub.

---

## 11. ¿Qué significa `main`?

`main` es el nombre de la rama principal del repositorio.

En muchos proyectos, `main` contiene la versión base o principal del trabajo.

Durante el curso evitaremos trabajar directamente sobre `main`, excepto cuando el docente lo indique.

La idea será:

```txt
main = rama principal
tarea/... = rama para trabajar una tarea
```

---

## 12. Primer push de una rama nueva

Cuando creamos una rama nueva, es posible que GitHub todavía no conozca esa rama.

Ejemplo:

```bash
git checkout -b tarea/flujo-push-pull
```

Después de hacer commit, subimos la rama con:

```bash
git push origin tarea/flujo-push-pull
```

También puede aparecer una sugerencia como:

```bash
git push --set-upstream origin tarea/flujo-push-pull
```

O en forma corta:

```bash
git push -u origin tarea/flujo-push-pull
```

La opción `-u` conecta la rama local con la rama remota.

Después de eso, en futuros pushes se podrá usar simplemente:

```bash
git push
```

---

## 13. ¿Qué pasa si hago cambios y no hago push?

Si haces cambios, creas commits, pero no haces `push`, esos commits solo existen en tu computador.

GitHub no los verá todavía.

Esto significa que:

* No aparecerán en el repositorio remoto.
* No se podrá crear Pull Request con esos cambios.
* Otra persona no podrá verlos.
* Si pierdes el computador, esos commits podrían perderse.

Por eso, después de completar una tarea, es importante hacer `push`.

---

## 14. ¿Qué pasa si no hago pull?

Si no haces `pull`, puedes estar trabajando con una versión vieja del repositorio.

Esto puede causar problemas como:

* No tener el material actualizado.
* Trabajar sobre una versión desactualizada.
* Tener conflictos al subir cambios.
* No ver archivos nuevos agregados por otra persona.

Por eso, antes de comenzar a trabajar, se recomienda hacer:

```bash
git checkout main
git pull origin main
```

---

## 15. Flujo visual completo

```txt
1. Actualizar main
   GitHub → Computador

   git checkout main
   git pull origin main

2. Crear rama de trabajo
   Computador

   git checkout -b tarea/nombre-tarea

3. Hacer cambios
   Computador

4. Guardar cambios
   Computador

   git add .
   git commit -m "Mensaje claro"

5. Subir cambios
   Computador → GitHub

   git push origin tarea/nombre-tarea

6. Crear Pull Request
   GitHub
```

---

## 16. Actividad guiada

Realizar los siguientes pasos:

1. Abrir el repositorio del curso en Visual Studio Code.
2. Abrir la terminal.
3. Ir a la rama principal:

```bash
git checkout main
```

4. Traer la última versión del repositorio:

```bash
git pull origin main
```

5. Crear una rama nueva:

```bash
git checkout -b tarea/flujo-push-pull
```

6. Crear un archivo llamado:

```txt
flujo-push-pull.md
```

7. Agregar el siguiente contenido:

```md
# Práctica de Push y Pull

Estoy practicando cómo sincronizar cambios entre mi computador y GitHub.

## Comandos usados

- git checkout main
- git pull origin main
- git checkout -b tarea/flujo-push-pull
- git add .
- git commit
- git push
```

8. Revisar el estado:

```bash
git status
```

9. Agregar los cambios:

```bash
git add .
```

10. Crear commit:

```bash
git commit -m "Agregar práctica de flujo push y pull"
```

11. Subir la rama:

```bash
git push origin tarea/flujo-push-pull
```

---

## 17. Tarea práctica

Crear un archivo llamado:

```txt
resumen-push-pull.md
```

Dentro del archivo, responder con tus propias palabras:

1. ¿Qué significa hacer `push`?
2. ¿Qué significa hacer `pull`?
3. ¿Cuál es la diferencia entre repositorio local y remoto?
4. ¿Por qué es importante hacer `pull` antes de empezar una tarea?
5. ¿Por qué es importante hacer `push` después de hacer commits?
6. ¿Qué significa `origin`?
7. ¿Qué significa `main`?
8. ¿Qué comando usarías para subir una rama llamada `tarea/mi-practica`?

---

## 18. Entregable

Enviar por Classroom:

* Captura del archivo `resumen-push-pull.md`.
* Captura del comando `git status`.
* Captura del comando `git log --oneline`.
* Captura del `push` realizado.
* Enlace a la rama subida en GitHub, si aplica.

Más adelante esta práctica también podrá entregarse mediante Pull Request.

---

## 19. Criterios de revisión

La actividad se considera completa si:

* Se entiende la diferencia entre `push` y `pull`.
* Se creó una rama de trabajo.
* Se realizó al menos un commit.
* Se subió la rama a GitHub.
* El archivo de resumen responde las preguntas con palabras propias.
* Los comandos fueron ejecutados correctamente.
* La entrega está ordenada.

---

## 20. Errores comunes

### Error: `fatal: not a git repository`

Significa que no estás dentro de una carpeta controlada por Git.

Solución:

1. Verifica que estés dentro de la carpeta del repositorio.
2. Ejecuta:

```bash
pwd
```

o en Windows:

```bash
cd
```

3. Entra a la carpeta correcta con:

```bash
cd curso-fullstack-basico-material
```

---

### Error: `failed to push some refs`

Puede pasar cuando el repositorio remoto tiene cambios que tu computador aún no tiene.

Solución general:

```bash
git pull origin main
```

Luego revisar si hay conflictos.

Si estás trabajando en una rama de tarea, consulta antes de hacer cambios fuertes.

---

### Error: no tengo permisos para hacer push

Puede pasar si la invitación al repositorio no fue aceptada o si estás usando otra cuenta de GitHub.

Solución:

* Revisar que la invitación fue aceptada.
* Verificar la cuenta de GitHub.
* Confirmar que tienes permisos como colaboradora.
* Revisar si el repositorio remoto apunta al lugar correcto con:

```bash
git remote -v
```

---

### Error: estoy intentando hacer push a `main`

Durante el curso evitaremos subir cambios directamente a `main`.

Antes de hacer cambios, se debe crear una rama:

```bash
git checkout -b tarea/nombre-de-la-tarea
```

---

## 21. Recomendación de trabajo

Antes de empezar cualquier tarea:

```bash
git checkout main
git pull origin main
git checkout -b tarea/nombre-de-la-tarea
```

Al terminar:

```bash
git status
git add .
git commit -m "Mensaje claro"
git push origin tarea/nombre-de-la-tarea
```

Este flujo será una de las bases más importantes del curso.

---

## 22. Resumen rápido

| Acción                     | Comando                                 |
| -------------------------- | --------------------------------------- |
| Traer cambios desde GitHub | `git pull origin main`                  |
| Subir cambios a GitHub     | `git push origin nombre-rama`           |
| Ver repositorio remoto     | `git remote -v`                         |
| Ver estado actual          | `git status`                            |
| Crear rama                 | `git checkout -b nombre-rama`           |
| Guardar cambios            | `git add .` + `git commit -m "mensaje"` |

---

## 23. Cierre de la clase

`push` y `pull` son comandos fundamentales para trabajar con GitHub.

Con `pull` traemos cambios.

Con `push` enviamos cambios.

El orden recomendado es:

```txt
Primero actualizo → Luego trabajo → Después subo
```

En comandos:

```bash
git pull
git add .
git commit
git push
```

Dominar este flujo evita muchos problemas y ayuda a trabajar de forma organizada. No elimina todos los errores, pero al menos hace que los errores tengan mejor presentación.
