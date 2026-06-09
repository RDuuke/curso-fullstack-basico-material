# 05 - Ramas y commits en Git

## Objetivo de la clase

Comprender qué son las ramas y los commits en Git, por qué se usan y cómo ayudan a trabajar de forma ordenada en un proyecto.

Al finalizar esta clase, la estudiante deberá poder:

* Explicar qué es una rama.
* Crear una rama nueva.
* Cambiar entre ramas.
* Entender para qué sirve un commit.
* Crear commits con mensajes claros.
* Aplicar una convención básica para nombrar ramas.
* Aplicar buenas prácticas al guardar cambios.

---

## 1. ¿Qué es una rama?

Una rama es una línea de trabajo separada dentro de un repositorio.

Permite trabajar en cambios nuevos sin afectar directamente la rama principal del proyecto.

En este curso, la rama principal será:

```txt
main
```

Y para cada tarea crearemos una rama diferente.

Ejemplo:

```txt
tarea/resumen-git
```

Dicho de forma sencilla:

```txt
Una rama es un espacio seguro para trabajar cambios sin dañar lo principal.
```

---

## 2. ¿Por qué usamos ramas?

Usamos ramas porque nos permiten:

* Trabajar una tarea de forma aislada.
* Probar cambios sin afectar `main`.
* Organizar mejor el trabajo.
* Crear Pull Requests.
* Revisar cambios antes de unirlos.
* Evitar modificar directamente la versión principal.

Ejemplo:

```txt
main
 └── tarea/comandos-basicos-git
```

La rama `main` se mantiene limpia, mientras que la rama de tarea contiene los cambios nuevos.

---

## 3. ¿Qué es `main`?

`main` es la rama principal del repositorio.

Normalmente contiene la versión base o estable del proyecto.

Durante el curso evitaremos trabajar directamente en `main`.

La idea será:

```txt
main = versión principal
tarea/... = espacio de trabajo para una tarea
feature/... = espacio de trabajo para una funcionalidad
fix/... = espacio para una corrección
docs/... = espacio para documentación
```

---

## 4. Ver ramas existentes

Para ver las ramas del repositorio, usamos:

```bash
git branch
```

La rama actual aparece marcada con un asterisco `*`.

Ejemplo:

```txt
* main
```

Esto significa que actualmente estamos trabajando en la rama `main`.

---

## 5. Crear una rama nueva

Para crear una rama nueva y cambiarse a ella, usamos:

```bash
git checkout -b nombre-de-la-rama
```

Ejemplo:

```bash
git checkout -b tarea/ramas-y-commits
```

Este comando hace dos cosas:

1. Crea la rama `tarea/ramas-y-commits`.
2. Cambia automáticamente a esa rama.

También se puede usar el comando moderno:

```bash
git switch -c tarea/ramas-y-commits
```

Ambos funcionan. Durante el curso podemos usar cualquiera, pero mantendremos un flujo claro.

---

## 6. Cambiar de rama

Para cambiar a una rama existente:

```bash
git checkout main
```

O usando `switch`:

```bash
git switch main
```

Ejemplo:

```bash
git checkout tarea/ramas-y-commits
```

Antes de cambiar de rama, es recomendable revisar el estado del repositorio:

```bash
git status
```

Si tienes cambios sin guardar, Git puede impedir el cambio o podrías confundirte.

---

## 7. Convención para nombres de ramas

Los nombres de ramas deben ser claros y descriptivos.

En este curso usaremos esta convención:

```txt
tipo/nombre-descriptivo
```

Tipos comunes:

| Tipo        | Uso                                            |
| ----------- | ---------------------------------------------- |
| `tarea/`    | Para tareas del curso                          |
| `feature/`  | Para funcionalidades nuevas                    |
| `fix/`      | Para correcciones                              |
| `docs/`     | Para documentación                             |
| `refactor/` | Para mejorar código sin cambiar comportamiento |

Ejemplos:

```txt
tarea/ramas-y-commits
tarea/resumen-push-pull
feature/listado-reservas
fix/corregir-validacion-cliente
docs/agregar-guia-git
refactor/organizar-servicio-reservas
```

---

## 8. Buenas prácticas para ramas

Una buena rama debería:

* Tener un nombre claro.
* Representar una sola tarea o funcionalidad.
* Crearse desde `main` actualizado.
* No mezclar muchos cambios diferentes.
* Terminar en un Pull Request.

Mal ejemplo:

```txt
tarea/cosas
```

Buen ejemplo:

```txt
tarea/resumen-comandos-git
```

Otro mal ejemplo:

```txt
feature/arreglos-varios-y-cambios-y-pruebas
```

Buen ejemplo:

```txt
feature/crear-formulario-reservas
```

---

## 9. Flujo recomendado para crear ramas

Antes de crear una rama nueva:

```bash
git checkout main
git pull origin main
```

Luego crear la rama:

```bash
git checkout -b tarea/nombre-de-la-tarea
```

Ejemplo completo:

```bash
git checkout main
git pull origin main
git checkout -b tarea/ramas-y-commits
```

Esto garantiza que la nueva rama nace desde la versión más actualizada de `main`.

---

## 10. ¿Qué es un commit?

Un commit es un registro de cambios dentro del historial de Git.

Cada commit guarda una versión del proyecto en un momento específico.

Dicho de forma sencilla:

```txt
Un commit es una foto del proyecto en un momento importante.
```

Cada commit tiene:

* Identificador único.
* Autor.
* Fecha.
* Mensaje.
* Archivos modificados.

---

## 11. ¿Para qué sirven los commits?

Los commits sirven para:

* Guardar avances.
* Consultar el historial.
* Entender qué cambió.
* Volver a revisar versiones anteriores.
* Dividir el trabajo en pasos pequeños.
* Facilitar revisiones en Pull Requests.

Un proyecto con buenos commits es más fácil de entender.

Un proyecto con commits tipo `cambios`, `final`, `final-final`, `ahora-si-final`... bueno, ese proyecto ya empezó terapia.

---

## 12. Crear un commit

Para crear un commit, primero revisamos los cambios:

```bash
git status
```

Luego agregamos los archivos:

```bash
git add .
```

Después creamos el commit:

```bash
git commit -m "Agregar resumen de ramas y commits"
```

Flujo:

```bash
git status
git add .
git commit -m "Mensaje claro"
```

---

## 13. Cómo escribir buenos mensajes de commit

Un mensaje de commit debe explicar qué se hizo.

Formato recomendado:

```txt
Verbo + descripción corta
```

Ejemplos:

```bash
git commit -m "Agregar resumen de comandos Git"
git commit -m "Crear guía de instalación de Git"
git commit -m "Corregir explicación de ramas"
git commit -m "Actualizar estructura de recursos"
```

Verbos recomendados:

* Agregar
* Crear
* Corregir
* Actualizar
* Eliminar
* Mejorar
* Refactorizar
* Documentar

---

## 14. Ejemplos de buenos y malos commits

| Mal mensaje | Mejor mensaje                           |
| ----------- | --------------------------------------- |
| `cambios`   | `Agregar explicación de git status`     |
| `final`     | `Completar guía de comandos básicos`    |
| `cosas`     | `Actualizar ejemplos de ramas`          |
| `prueba`    | `Agregar práctica de flujo push y pull` |
| `arreglo`   | `Corregir error en comando git pull`    |

Un buen mensaje no tiene que ser largo. Tiene que ser claro.

---

## 15. Commits pequeños

Es mejor hacer commits pequeños y relacionados.

Ejemplo de malos commits:

```txt
Un solo commit que agrega README, cambia estilos, corrige backend, borra archivos y modifica tareas.
```

Ejemplo de buenos commits:

```txt
Agregar README inicial
Crear guía de comandos básicos
Corregir explicación de git push
Actualizar checklist de instalación
```

Cada commit debe representar una idea clara.

---

## 16. Ver historial de commits

Para ver el historial:

```bash
git log
```

Para verlo de forma resumida:

```bash
git log --oneline
```

Ejemplo:

```txt
a1b2c3d Agregar resumen de ramas y commits
e4f5g6h Agregar guía de flujo push y pull
d7e8f9a Agregar guía de comandos básicos
```

---

## 17. Ver cambios antes de hacer commit

Antes de hacer commit, es recomendable revisar qué cambió:

```bash
git status
git diff
```

`git status` muestra qué archivos cambiaron.

`git diff` muestra el contenido exacto que cambió.

Flujo recomendado:

```bash
git status
git diff
git add .
git commit -m "Mensaje claro"
```

---

## 18. Subir una rama a GitHub

Después de crear commits en una rama, debemos subirla a GitHub.

Ejemplo:

```bash
git push origin tarea/ramas-y-commits
```

Si es la primera vez que subes esa rama, también puedes usar:

```bash
git push -u origin tarea/ramas-y-commits
```

Luego de subir la rama, se podrá crear un Pull Request.

---

## 19. Flujo completo de ramas y commits

```bash
git checkout main
git pull origin main
git checkout -b tarea/ramas-y-commits

# Realizar cambios en archivos

git status
git diff
git add .
git commit -m "Agregar práctica de ramas y commits"
git push origin tarea/ramas-y-commits
```

---

## 20. Actividad guiada

Realizar los siguientes pasos:

1. Abrir el repositorio en Visual Studio Code.
2. Abrir la terminal.
3. Ir a `main`:

```bash
git checkout main
```

4. Actualizar `main`:

```bash
git pull origin main
```

5. Crear una rama nueva:

```bash
git checkout -b tarea/ramas-y-commits
```

6. Crear un archivo llamado:

```txt
practica-ramas-commits.md
```

7. Agregar el siguiente contenido:

````md
# Práctica de ramas y commits

Estoy aprendiendo a trabajar con ramas y commits en Git.

## Mi rama de trabajo

La rama que estoy usando es:

```txt
tarea/ramas-y-commits
````

## Lo que aprendí

* Una rama permite trabajar cambios sin afectar `main`.
* Un commit guarda una versión del proyecto.
* Los mensajes de commit deben ser claros.

````

8. Revisar estado:

```bash
git status
````

9. Revisar diferencias:

```bash
git diff
```

10. Agregar cambios:

```bash
git add .
```

11. Crear commit:

```bash
git commit -m "Agregar práctica de ramas y commits"
```

12. Subir rama:

```bash
git push origin tarea/ramas-y-commits
```

---

## 21. Tarea práctica

Crear un archivo llamado:

```txt
resumen-ramas-commits.md
```

Responder con tus propias palabras:

1. ¿Qué es una rama?
2. ¿Para qué sirve una rama?
3. ¿Por qué no deberíamos trabajar directamente sobre `main`?
4. ¿Qué es un commit?
5. ¿Qué características debe tener un buen commit?
6. Escribe 3 ejemplos de buenos nombres de ramas.
7. Escribe 3 ejemplos de buenos mensajes de commit.
8. ¿Cuál es el flujo recomendado para iniciar una tarea?
9. ¿Cuál es el flujo recomendado para guardar y subir cambios?

---

## 22. Entregable

Enviar por Classroom:

* Captura del archivo `resumen-ramas-commits.md`.
* Captura de la rama creada.
* Captura del comando `git status`.
* Captura del comando `git log --oneline`.
* Captura del `push` realizado.
* Enlace de la rama en GitHub, si aplica.

Más adelante esta entrega podrá realizarse mediante Pull Request.

---

## 23. Criterios de revisión

La actividad se considera completa si:

* La rama fue creada correctamente.
* El nombre de la rama es claro.
* Se creó al menos un commit.
* El mensaje del commit es claro.
* Se subió la rama a GitHub.
* El archivo responde las preguntas con palabras propias.
* La entrega está ordenada.

---

## 24. Errores comunes

### Error: hice cambios en `main`

Si todavía no hiciste commit, puedes crear una rama y llevar esos cambios allí:

```bash
git checkout -b tarea/nombre-de-la-tarea
```

Luego haces commit en esa rama.

Si ya hiciste commit en `main`, consulta antes de continuar.

---

### Error: no sé en qué rama estoy

Ejecuta:

```bash
git branch
```

La rama actual aparece con `*`.

También puedes usar:

```bash
git status
```

---

### Error: quiero borrar una rama local

Si una rama ya no se necesita:

```bash
git branch -d nombre-rama
```

Si Git no permite borrarla porque tiene cambios no fusionados:

```bash
git branch -D nombre-rama
```

Usar `-D` con cuidado.

---

### Error: escribí mal el nombre de la rama

Una opción sencilla es crear una nueva rama con el nombre correcto y continuar allí.

Más adelante aprenderemos a renombrar ramas, pero por ahora priorizaremos claridad y práctica.

---

## 25. Resumen rápido

| Concepto               | Significado                |
| ---------------------- | -------------------------- |
| Rama                   | Línea de trabajo separada  |
| `main`                 | Rama principal             |
| Commit                 | Registro de cambios        |
| `git branch`           | Ver ramas                  |
| `git checkout -b`      | Crear y cambiar a una rama |
| `git checkout`         | Cambiar de rama            |
| `git add .`            | Preparar cambios           |
| `git commit -m`        | Guardar cambios            |
| `git push origin rama` | Subir rama a GitHub        |

---

## 26. Cierre de la clase

Las ramas nos permiten trabajar sin afectar directamente la versión principal del proyecto.

Los commits nos permiten guardar avances claros en el historial.

Durante el curso, cada tarea importante deberá seguir este flujo:

```txt
Actualizar main → Crear rama → Hacer cambios → Commit → Push → Pull Request
```

Este flujo parece largo al principio, pero después se vuelve natural. Es como aprender a manejar: primero piensas en todo, luego haces los cambios casi automático… excepto cuando Git te habla en rojo, ahí todos volvemos a leer despacio.
