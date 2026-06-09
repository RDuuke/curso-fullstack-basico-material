# 01 - ¿Qué es Git y qué es GitHub?

## Objetivo de la clase

Comprender qué son Git y GitHub, para qué sirven y por qué son herramientas importantes en el desarrollo de software.

Al finalizar esta clase, la estudiante deberá poder explicar con sus propias palabras:

* Qué es Git.
* Qué es GitHub.
* Qué diferencia hay entre Git y GitHub.
* Para qué sirve guardar versiones del código.
* Por qué los equipos de desarrollo usan repositorios.

---

## 1. ¿Qué problema resuelve Git?

Cuando estamos programando, normalmente hacemos muchos cambios en nuestros archivos.

Por ejemplo:

* Creamos archivos nuevos.
* Modificamos código.
* Corregimos errores.
* Probamos ideas.
* Eliminamos partes que ya no sirven.
* Agregamos nuevas funcionalidades.

El problema aparece cuando necesitamos responder preguntas como:

* ¿Qué cambié?
* ¿Cuándo lo cambié?
* ¿Por qué lo cambié?
* ¿Quién hizo el cambio?
* ¿Cómo puedo volver a una versión anterior?
* ¿Cómo puedo trabajar sin dañar lo que ya funciona?

Git ayuda a resolver ese problema.

---

## 2. ¿Qué es Git?

Git es una herramienta de **control de versiones**.

Eso significa que nos permite guardar el historial de cambios de un proyecto.

Con Git podemos saber qué archivos cambiaron, cuándo cambiaron y guardar diferentes versiones del código.

Una forma sencilla de entenderlo:

> Git es como una máquina del tiempo para nuestro código.

Cada vez que hacemos un cambio importante, podemos guardar una “foto” del estado del proyecto. Esa foto se llama **commit**.

---

## 3. Ejemplo sencillo

Imagina que estás escribiendo un documento.

Primero tienes esto:

```txt
Versión 1:
Hola, este es mi proyecto.
```

Luego agregas más información:

```txt
Versión 2:
Hola, este es mi proyecto.
Estoy aprendiendo Git.
```

Después haces otro cambio:

```txt
Versión 3:
Hola, este es mi proyecto.
Estoy aprendiendo Git y GitHub.
```

Sin Git, puede ser difícil saber qué cambió entre una versión y otra.

Con Git, podemos guardar cada versión importante y volver a consultarla cuando sea necesario.

---

## 4. ¿Qué es un repositorio?

Un repositorio es el lugar donde se guarda un proyecto controlado con Git.

Puede contener:

* Archivos de código.
* Carpetas.
* Documentación.
* Historial de cambios.
* Ramas.
* Commits.

En este curso usaremos un repositorio para guardar el material, las tareas y parte del avance del aprendizaje.

---

## 5. ¿Qué es GitHub?

GitHub es una plataforma en internet donde podemos guardar repositorios Git.

Git vive en nuestro computador.

GitHub vive en la nube.

Con GitHub podemos:

* Subir nuestro código.
* Guardar una copia remota del proyecto.
* Compartir el proyecto con otras personas.
* Trabajar en equipo.
* Crear ramas.
* Crear Pull Requests.
* Revisar cambios.
* Documentar tareas.
* Ver el historial del proyecto.

---

## 6. Diferencia entre Git y GitHub

Aunque suelen mencionarse juntos, no son lo mismo.

| Concepto | Descripción                                           |
| -------- | ----------------------------------------------------- |
| Git      | Herramienta que controla versiones del código         |
| GitHub   | Plataforma en línea donde se guardan repositorios Git |

Una forma sencilla de verlo:

```txt
Git = herramienta
GitHub = plataforma donde se sube el proyecto
```

Ejemplo:

```txt
Git es como el cuaderno donde escribes el historial.
GitHub es como la biblioteca donde guardas y compartes ese cuaderno.
```

---

## 7. ¿Qué es un commit?

Un commit es un registro de cambios.

Cada commit representa una versión del proyecto en un momento específico.

Un commit debería responder:

* Qué se cambió.
* Por qué se cambió.
* En qué momento se hizo el cambio.

Ejemplo de mensaje de commit:

```bash
git commit -m "Agregar README inicial del curso"
```

Ese mensaje indica que se agregó el archivo README inicial.

---

## 8. ¿Qué es push?

`push` significa subir los cambios desde nuestro computador hacia GitHub.

Ejemplo:

```bash
git push origin main
```

Esto envía los commits locales hacia el repositorio remoto.

Dicho de forma sencilla:

```txt
push = subir cambios a GitHub
```

---

## 9. ¿Qué es pull?

`pull` significa traer los cambios desde GitHub hacia nuestro computador.

Ejemplo:

```bash
git pull origin main
```

Esto actualiza nuestro proyecto local con los cambios que están en GitHub.

Dicho de forma sencilla:

```txt
pull = traer cambios desde GitHub
```

---

## 10. ¿Qué es una rama?

Una rama es una línea de trabajo separada dentro del proyecto.

Sirve para trabajar en una funcionalidad o tarea sin afectar directamente la versión principal.

Ejemplo:

```bash
git checkout -b tarea/mi-primera-entrega
```

Esto crea una nueva rama para trabajar una tarea.

Dicho de forma sencilla:

```txt
rama = espacio separado para trabajar sin dañar lo principal
```

---

## 11. ¿Qué es un Pull Request?

Un Pull Request, también conocido como PR, es una solicitud para unir cambios de una rama a otra.

Normalmente se usa para pedir que los cambios realizados en una rama sean revisados antes de unirlos a la rama principal.

En este curso usaremos Pull Requests para entregar tareas.

El flujo será:

```txt
Crear rama → Hacer cambios → Commit → Push → Crear Pull Request
```

---

## 12. ¿Por qué usaremos Git y GitHub en el curso?

Usaremos Git y GitHub porque son herramientas muy usadas en el mundo real del desarrollo de software.

Nos ayudarán a practicar:

* Organización del trabajo.
* Historial de cambios.
* Entrega de tareas.
* Trabajo por ramas.
* Revisión mediante Pull Requests.
* Documentación del avance.

No se trata solo de aprender comandos. Se trata de aprender una forma ordenada de trabajar.

---

## 13. Resumen rápido

| Concepto     | Significado                                      |
| ------------ | ------------------------------------------------ |
| Git          | Herramienta para controlar versiones             |
| GitHub       | Plataforma para guardar repositorios en internet |
| Repositorio  | Carpeta/proyecto controlado con Git              |
| Commit       | Registro de cambios                              |
| Push         | Subir cambios a GitHub                           |
| Pull         | Traer cambios desde GitHub                       |
| Rama         | Espacio separado de trabajo                      |
| Pull Request | Solicitud para revisar y unir cambios            |

---

## 14. Actividad de reflexión

Responder con tus propias palabras:

1. ¿Qué es Git?
2. ¿Qué es GitHub?
3. ¿Cuál es la diferencia entre Git y GitHub?
4. ¿Para qué sirve un commit?
5. ¿Qué significa hacer push?
6. ¿Qué significa hacer pull?
7. ¿Por qué es útil trabajar con ramas?
8. ¿Qué es un Pull Request?

---

## 15. Cierre de la clase

Git y GitHub nos ayudan a trabajar de forma más ordenada.

Al inicio puede parecer que son muchos comandos, pero poco a poco se vuelven parte natural del proceso de desarrollo.

La idea no es memorizar todo desde el primer día. La idea es practicar hasta que el flujo tenga sentido.
