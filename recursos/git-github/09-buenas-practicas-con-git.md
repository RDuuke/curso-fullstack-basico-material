# 09. Buenas prácticas con Git

## 📖 Introducción

Git es una herramienta muy poderosa, pero utilizarla correctamente marca una gran diferencia en la calidad de un proyecto.

Adoptar buenas prácticas desde el inicio facilita el trabajo en equipo, reduce errores y permite entender fácilmente la historia de un proyecto, incluso meses o años después.

En este capítulo aprenderás algunos hábitos que utilizan equipos profesionales de desarrollo y que también aplicaremos durante este curso.

---

## 🎯 Objetivos de aprendizaje

Al finalizar este tema podrás:

* Escribir commits claros y descriptivos.
* Organizar mejor tu trabajo utilizando ramas.
* Evitar errores comunes al trabajar con Git.
* Mantener un historial de cambios limpio y fácil de entender.

---

# 📝 Escribe buenos mensajes de commit

Cada commit representa un cambio en el proyecto, por lo que su mensaje debe explicar claramente qué se hizo.

## ✅ Buenos ejemplos

```text
Agrega formulario de registro
Corrige validación del correo electrónico
Actualiza estilos de la página principal
Crea endpoint para listar usuarios
```

## ❌ Malos ejemplos

```text
Cambios
Arreglo
Prueba
asdf
Actualización
```

Recuerda: un buen mensaje permite que cualquier persona entienda rápidamente el propósito del cambio.

---

# 🌿 Trabaja siempre con ramas

Evita realizar cambios directamente sobre `main`.

En lugar de eso, crea una rama para cada funcionalidad o actividad.

Por ejemplo:

```bash
git checkout -b feature/pagina-contacto
```

Al finalizar, podrás integrar esa rama mediante un Pull Request.

---

# 💾 Haz commits pequeños y frecuentes

No esperes a terminar todo el proyecto para hacer un único commit.

Es preferible guardar avances pequeños y organizados.

Por ejemplo:

* Commit 1: Crear estructura HTML.
* Commit 2: Agregar estilos CSS.
* Commit 3: Implementar lógica en JavaScript.
* Commit 4: Corregir errores encontrados.

Esto facilita volver atrás si ocurre algún problema.

---

# 🔄 Mantén tu repositorio actualizado

Antes de comenzar una tarea, descarga los cambios más recientes:

```bash
git checkout main
git pull origin main
```

Así reduces la posibilidad de encontrar conflictos al integrar tu trabajo.

---

# 👀 Revisa tus cambios antes de confirmar

Antes de realizar un commit puedes verificar el estado del repositorio:

```bash
git status
```

Y si deseas revisar exactamente qué cambió:

```bash
git diff
```

Dedicar unos segundos a esta revisión puede evitar errores innecesarios.

---

# 🚫 No subas archivos innecesarios

Existen archivos que normalmente no deberían almacenarse en Git, por ejemplo:

* Dependencias descargadas.
* Archivos temporales.
* Archivos compilados.
* Configuraciones personales.
* Contraseñas o credenciales.

Para excluirlos se utiliza el archivo `.gitignore`.

Un ejemplo sencillo:

```text
node_modules/
dist/
.env
.vscode/
```

---

# 🤝 Piensa en tu equipo

Cuando trabajas con Git no solo escribes código para ti.

También debes facilitar que otras personas puedan:

* Leer tus cambios.
* Revisar tus commits.
* Entender tu historial.
* Colaborar contigo sin dificultades.

Un repositorio organizado beneficia a todo el equipo.

---

## 💡 Buenas prácticas recomendadas

* Usa nombres descriptivos para las ramas.
* Escribe mensajes de commit claros.
* Haz commits pequeños y frecuentes.
* Sincroniza el repositorio antes de empezar.
* Revisa tus cambios antes de enviarlos.
* Utiliza `.gitignore` correctamente.
* Evita subir archivos sensibles o innecesarios.

---

## ⚠️ Errores comunes

* Trabajar directamente sobre `main`.
* Hacer un solo commit con cientos de cambios.
* Subir archivos que no hacen parte del proyecto.
* Utilizar mensajes de commit poco informativos.
* No revisar el estado del repositorio antes de hacer un commit.

---

## 📌 Resumen

Las buenas prácticas con Git ayudan a mantener proyectos organizados, facilitan el trabajo colaborativo y reducen errores durante el desarrollo.

Pequeños hábitos, como escribir buenos mensajes de commit o trabajar en ramas independientes, hacen una gran diferencia cuando el proyecto crece.

---

## 📝 Actividad para el estudiante

Imagina que desarrollaste una aplicación para gestionar tareas.

Escribe cinco mensajes de commit que representen cambios reales del proyecto. Por ejemplo:

* Crear pantalla de inicio.
* Implementar autenticación.
* Agregar validación del formulario.
* Corregir error en el listado.
* Actualizar documentación.

Luego, analiza si esos mensajes son claros y descriptivos para otra persona que no conozca el proyecto.
