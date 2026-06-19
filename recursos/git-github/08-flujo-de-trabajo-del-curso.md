# 08. Flujo de trabajo del curso

## Introducción

En el mundo profesional no es recomendable desarrollar directamente sobre la rama principal (`main`). En su lugar, cada nueva funcionalidad o corrección se realiza en una rama independiente y, una vez terminada, se integra al proyecto mediante un **Pull Request (PR)**.

Durante este curso seguiremos un flujo de trabajo similar al utilizado por equipos de desarrollo reales. Esto nos permitirá mantener el código organizado, facilitar las revisiones y reducir errores.

---

## Objetivos de aprendizaje

Al finalizar este tema podrás:

* Comprender el flujo de trabajo que utilizaremos durante el curso.
* Crear una rama para desarrollar una tarea.
* Subir tus cambios al repositorio remoto.
* Crear un Pull Request para solicitar la integración de tu trabajo.
* Mantener un historial de cambios limpio y organizado.

---

# Flujo general de trabajo

Cada vez que debas realizar una actividad o desarrollar una nueva funcionalidad, seguirás estos pasos:

```text
Actualizar main
        │
        ▼
Crear una nueva rama
        │
        ▼
Realizar cambios
        │
        ▼
Crear uno o varios commits
        │
        ▼
Subir la rama a GitHub
        │
        ▼
Crear Pull Request
        │
        ▼
Revisión
        │
        ▼
Merge a main
```

Este flujo ayuda a evitar conflictos y permite revisar el trabajo antes de incorporarlo al proyecto principal.

---

# Paso 1: Actualizar la rama principal

Antes de comenzar cualquier tarea, asegúrate de tener la última versión del proyecto.

```bash
git checkout main
git pull origin main
```

Así evitarás trabajar sobre una versión desactualizada.

---

# Paso 2: Crear una nueva rama

Cada actividad debe desarrollarse en una rama propia.

Por ejemplo:

```bash
git checkout -b feature/taller-html
```

Algunas convenciones útiles para nombrar ramas son:

* `feature/login`
* `feature/api-clientes`
* `feature/taller-01`
* `fix/error-formulario`
* `docs/actualizar-readme`

Utiliza nombres descriptivos y fáciles de entender.

---

# Paso 3: Desarrollar la funcionalidad

Realiza todos los cambios necesarios en tu proyecto.

Puedes crear archivos, modificar código, eliminar contenido o agregar documentación.

Durante este proceso es recomendable guardar cambios frecuentemente mediante commits.

---

# Paso 4: Crear un commit

Una vez tengas un avance importante:

```bash
git add .
git commit -m "Agrega solución al taller HTML"
```

El mensaje debe describir claramente qué cambió.

---

# Paso 5: Subir la rama a GitHub

Para compartir tu trabajo con el repositorio remoto:

```bash
git push origin feature/taller-html
```

Ahora la rama estará disponible en GitHub.

---

# Paso 6: Crear un Pull Request

Desde GitHub podrás crear un Pull Request para solicitar que tus cambios sean revisados antes de integrarse a `main`.

En un equipo profesional, otros desarrolladores pueden:

* Revisar tu código.
* Hacer comentarios.
* Solicitar ajustes.
* Aprobar la integración.

En este curso, el Pull Request también servirá como mecanismo para entregar algunas actividades.

---

# Paso 7: Corregir observaciones

Si el docente o un compañero encuentra algo por mejorar, simplemente realiza nuevos cambios en la misma rama.

Después ejecuta nuevamente:

```bash
git add .
git commit -m "Corrige observaciones del PR"
git push
```

El Pull Request se actualizará automáticamente con los nuevos cambios.

---

# Paso 8: Integrar los cambios

Una vez aprobado el Pull Request, los cambios podrán fusionarse con la rama principal (`main`).

Esto significa que la nueva funcionalidad pasa a formar parte oficial del proyecto.

---

## Buenas prácticas

* Trabaja siempre en una rama distinta de `main`.
* Haz commits pequeños y frecuentes.
* Usa mensajes descriptivos en los commits.
* Mantén tu rama actualizada.
* Revisa tus cambios antes de enviarlos.
* No esperes hasta el final para subir todo tu trabajo.

---

## Errores comunes

* Trabajar directamente sobre `main`.
* Hacer un único commit con cientos de cambios.
* Crear ramas con nombres poco descriptivos como `prueba` o `rama1`.
* Olvidar subir la rama antes de crear el Pull Request.
* No revisar los comentarios realizados durante una revisión de código.

---

## Resumen

El flujo de trabajo que utilizaremos durante el curso será:

1. Actualizar `main`.
2. Crear una nueva rama.
3. Desarrollar la actividad.
4. Crear uno o varios commits.
5. Subir la rama a GitHub.
6. Crear un Pull Request.
7. Aplicar correcciones si son necesarias.
8. Integrar los cambios al proyecto.

Seguir este proceso te ayudará a trabajar de forma organizada y te preparará para colaborar en proyectos reales.

---

## Actividad para el estudiante

Realiza el siguiente ejercicio:

1. Actualiza tu rama `main`.
2. Crea una rama llamada `feature/practica-flujo`.
3. Crea un archivo llamado `mi-nota.md`.
4. Escribe una breve presentación personal.
5. Realiza un commit con un mensaje descriptivo.
6. Sube la rama al repositorio remoto.
7. Crea un Pull Request en GitHub.
8. Comparte el enlace del Pull Request con el docente para su revisión.
