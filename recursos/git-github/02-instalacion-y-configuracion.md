# 02 - Instalación y configuración de Git

## Objetivo de la clase

Preparar el entorno de trabajo para usar Git y GitHub durante el curso.

Al finalizar esta clase, la estudiante deberá tener:

* Git instalado en su computador.
* Una cuenta de GitHub activa.
* Git configurado con nombre y correo.
* Acceso al repositorio del curso.
* Visual Studio Code preparado para trabajar.
* Conocimiento básico para validar que todo quedó instalado correctamente.

---

## 1. ¿Por qué necesitamos instalar Git?

Git es la herramienta que nos permitirá controlar los cambios del proyecto.

Durante el curso usaremos Git para:

* Guardar avances del código.
* Crear ramas.
* Hacer commits.
* Subir cambios a GitHub.
* Traer cambios desde GitHub.
* Crear Pull Requests.

Antes de empezar a programar, necesitamos asegurarnos de que Git esté instalado y configurado correctamente.

---

## 2. Descargar Git

Para instalar Git, se debe ingresar al sitio oficial:

```txt
https://git-scm.com/
```

Desde allí se descarga el instalador según el sistema operativo:

* Windows.
* macOS.
* Linux.

---

## 3. Instalación en Windows

Si estás usando Windows:

1. Ingresa a `https://git-scm.com/`.
2. Descarga Git para Windows.
3. Ejecuta el instalador.
4. Puedes dejar la mayoría de opciones por defecto.
5. Asegúrate de instalar también **Git Bash**.
6. Finaliza la instalación.

Git Bash será una terminal que nos permitirá ejecutar comandos de Git.

---

## 4. Validar que Git quedó instalado

Después de instalar Git, abre una terminal.

Puede ser:

* Git Bash.
* Terminal de Windows.
* PowerShell.
* Terminal integrada de Visual Studio Code.

Ejecuta el siguiente comando:

```bash
git --version
```

Si Git está instalado correctamente, deberías ver una respuesta similar a esta:

```bash
git version 2.45.0
```

El número puede cambiar según la versión instalada.

Si aparece un mensaje de error, significa que Git no quedó instalado correctamente o la terminal no lo reconoce.

---

## 5. Configurar nombre de usuario en Git

Git necesita saber quién realiza los cambios.

Para configurar el nombre, usamos:

```bash
git config --global user.name "Tu Nombre"
```

Ejemplo:

```bash
git config --global user.name "Lili"
```

Este nombre aparecerá asociado a los commits realizados desde el computador.

---

## 6. Configurar correo en Git

También debemos configurar el correo.

Lo ideal es usar el mismo correo asociado a la cuenta de GitHub.

Comando:

```bash
git config --global user.email "tu-correo@example.com"
```

Ejemplo:

```bash
git config --global user.email "lili@example.com"
```

Este correo ayuda a relacionar los commits locales con la cuenta de GitHub.

---

## 7. Verificar la configuración de Git

Para revisar la configuración actual, ejecuta:

```bash
git config --global --list
```

Deberías ver algo parecido a esto:

```bash
user.name=Lili
user.email=lili@example.com
```

Si aparece el nombre y el correo, Git ya está configurado.

---

## 8. Crear o validar cuenta de GitHub

GitHub será la plataforma donde estará alojado el repositorio del curso.

Para usarlo, se necesita una cuenta activa.

Ingresar a:

```txt
https://github.com/
```

Si ya tienes cuenta, solo debes iniciar sesión.

Si no tienes cuenta, debes crear una nueva.

---

## 9. Repositorio del curso

El repositorio de material de apoyo del curso será:

```txt
https://github.com/RDuuke/curso-fullstack-basico-material
```

En este repositorio se publicarán:

* Material de clase.
* Guías.
* Ejercicios.
* Tareas.
* Recursos.
* Ejemplos.
* Indicaciones de entregas.

También será usado para practicar ramas, commits y Pull Requests.

---

## 10. Aceptar invitación al repositorio

La invitación para acceder al repositorio ya fue enviada.

Para aceptarla:

1. Inicia sesión en GitHub.
2. Revisa las notificaciones.
3. Busca la invitación al repositorio `curso-fullstack-basico-material`.
4. Acepta la invitación.
5. Ingresa al repositorio.

Si no aparece la invitación, revisar también el correo asociado a GitHub.

---

## 11. Instalar Visual Studio Code

Visual Studio Code será el editor que usaremos para escribir código.

Se puede descargar desde:

```txt
https://code.visualstudio.com/
```

Después de instalarlo, se usará para abrir carpetas de proyectos y editar archivos.

---

## 12. Abrir la terminal en Visual Studio Code

Para abrir la terminal dentro de Visual Studio Code:

1. Abrir Visual Studio Code.
2. Ir al menú superior.
3. Seleccionar `Terminal`.
4. Luego seleccionar `New Terminal` o `Nueva terminal`.

También se puede usar el atajo:

```txt
Ctrl + ñ
```

o en algunos teclados:

```txt
Ctrl + `
```

Desde esta terminal podremos ejecutar comandos de Git.

---

## 13. Crear carpeta local para el curso

Antes de clonar el repositorio, se recomienda crear una carpeta para guardar los archivos del curso.

Ejemplo:

```txt
Documentos/
└── curso-fullstack-basico/
```

Desde la terminal, se puede crear una carpeta así:

```bash
mkdir curso-fullstack-basico
```

Entrar a la carpeta:

```bash
cd curso-fullstack-basico
```

---

## 14. Clonar el repositorio del curso

Clonar significa descargar una copia del repositorio desde GitHub al computador.

Comando:

```bash
git clone https://github.com/RDuuke/curso-fullstack-basico-material.git
```

Luego entrar a la carpeta del repositorio:

```bash
cd curso-fullstack-basico-material
```

---

## 15. Abrir el repositorio en Visual Studio Code

Después de entrar a la carpeta del repositorio, se puede abrir en Visual Studio Code con:

```bash
code .
```

El punto `.` significa “abrir la carpeta actual”.

Si el comando `code .` no funciona, se puede abrir Visual Studio Code manualmente y seleccionar:

```txt
File → Open Folder
```

o en español:

```txt
Archivo → Abrir carpeta
```

Luego se selecciona la carpeta del repositorio.

---

## 16. Verificar el estado del repositorio

Dentro de la carpeta del repositorio, ejecutar:

```bash
git status
```

Este comando muestra el estado actual del repositorio.

Si todo está correcto, deberías ver algo como:

```bash
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

Esto significa que el repositorio está actualizado y no hay cambios pendientes.

---

## 17. Comandos vistos en esta clase

| Comando                                   | Descripción                                  |
| ----------------------------------------- | -------------------------------------------- |
| `git --version`                           | Muestra la versión instalada de Git          |
| `git config --global user.name "Nombre"`  | Configura el nombre del usuario              |
| `git config --global user.email "correo"` | Configura el correo del usuario              |
| `git config --global --list`              | Muestra la configuración global              |
| `mkdir nombre-carpeta`                    | Crea una carpeta                             |
| `cd nombre-carpeta`                       | Entra a una carpeta                          |
| `git clone URL`                           | Descarga un repositorio                      |
| `git status`                              | Muestra el estado del repositorio            |
| `code .`                                  | Abre la carpeta actual en Visual Studio Code |

---

## 18. Checklist de la clase

Marca cada punto cuando esté completo:

```txt
[ ] Git instalado
[ ] Versión de Git validada
[ ] Nombre configurado en Git
[ ] Correo configurado en Git
[ ] Cuenta de GitHub activa
[ ] Invitación al repositorio aceptada
[ ] Visual Studio Code instalado
[ ] Carpeta local del curso creada
[ ] Repositorio clonado
[ ] Repositorio abierto en Visual Studio Code
[ ] Comando git status ejecutado correctamente
```

---

## 19. Actividad práctica

Realizar los siguientes pasos:

1. Validar que Git esté instalado.
2. Configurar nombre y correo en Git.
3. Iniciar sesión en GitHub.
4. Aceptar la invitación al repositorio.
5. Clonar el repositorio del curso.
6. Abrir el repositorio en Visual Studio Code.
7. Ejecutar `git status`.

---

## 20. Entregable

Enviar por Classroom:

* Captura del comando:

```bash
git --version
```

* Captura del comando:

```bash
git config --global --list
```

* Captura del repositorio abierto en GitHub.
* Captura del repositorio abierto en Visual Studio Code.
* Captura del comando:

```bash
git status
```

---

## 21. Criterios de revisión

La actividad se considera completa si:

* Git está instalado correctamente.
* Git tiene nombre y correo configurados.
* La cuenta de GitHub está activa.
* La invitación al repositorio fue aceptada.
* El repositorio fue clonado correctamente.
* El repositorio se abrió en Visual Studio Code.
* El comando `git status` se ejecutó sin errores.

---

## 22. Errores comunes

### Error: `git` no se reconoce como comando

Puede ocurrir si Git no está instalado o si la terminal no lo reconoce.

Solución:

* Verificar que Git esté instalado.
* Cerrar y abrir nuevamente la terminal.
* Reiniciar Visual Studio Code.
* Reinstalar Git si es necesario.

---

### Error: no aparece la invitación de GitHub

Puede ocurrir si se está usando otra cuenta de GitHub.

Solución:

* Confirmar el usuario correcto.
* Revisar notificaciones de GitHub.
* Revisar el correo asociado a GitHub.
* Solicitar nuevamente la invitación si es necesario.

---

### Error: `code .` no funciona

Puede ocurrir si Visual Studio Code no está agregado al PATH.

Solución:

* Abrir Visual Studio Code manualmente.
* Ir a `Archivo → Abrir carpeta`.
* Seleccionar la carpeta del repositorio.

---

## 23. Cierre de la clase

En esta clase preparamos el entorno de trabajo.

Esto es importante porque antes de construir cualquier proyecto necesitamos tener listas las herramientas principales.

A partir de la próxima clase empezaremos a usar Git con más práctica: cambios, commits, push, pull y revisión del historial.

Configurar bien el entorno puede parecer un paso pequeño, pero evita muchos dolores de cabeza después. En programación, media hora preparando bien el ambiente puede ahorrar tres horas peleando con la terminal como si fuera villana de novela.
