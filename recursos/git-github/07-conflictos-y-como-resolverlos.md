# 07. Conflictos en Git y cómo resolverlos

## Introducción

Cuando trabajamos solos en un proyecto es poco común encontrar conflictos. Sin embargo, en un equipo de desarrollo varias personas pueden modificar el mismo archivo al mismo tiempo.

Git intenta combinar automáticamente esos cambios, pero cuando no puede decidir cuál versión conservar, genera un **conflicto** y solicita la intervención del desarrollador.

La buena noticia es que los conflictos son normales y aprender a resolverlos es una habilidad fundamental para cualquier programador.

---

## Objetivos de aprendizaje

Al finalizar este tema podrás:

* Entender qué es un conflicto en Git.
* Identificar cuándo ocurre un conflicto.
* Resolver un conflicto manualmente.
* Evitar muchos conflictos siguiendo buenas prácticas.

---

## ¿Qué es un conflicto?

Un conflicto ocurre cuando Git encuentra cambios incompatibles entre dos versiones de un mismo archivo y **no puede fusionarlos automáticamente**.

Por ejemplo:

* Dos personas modifican la misma línea de código.
* Una persona elimina un archivo mientras otra lo edita.
* Se intenta hacer un `merge` o un `pull` con cambios que chocan entre sí.

En estos casos Git detiene la operación y espera que el desarrollador tome una decisión.

---

## Un ejemplo sencillo

Imagina que existe el siguiente archivo:

```txt
Bienvenidos al Curso Fullstack Básico
```

Tú cambias esa línea por:

```txt
Bienvenidos al mejor Curso Fullstack Básico
```

Mientras tanto, otro compañero la cambia por:

```txt
Bienvenidos al Curso de Desarrollo Web
```

Cuando intentan unir ambos cambios, Git no sabe cuál debe conservar y genera un conflicto.

---

## ¿Cuándo suelen aparecer conflictos?

Los conflictos son comunes cuando ejecutas operaciones como:

```bash
git merge
```

o

```bash
git pull
```

También pueden aparecer durante un `git rebase`, aunque ese tema lo veremos más adelante.

---

## ¿Cómo se ve un conflicto?

Git marca el archivo con indicadores especiales:

```txt
<<<<<<< HEAD
Bienvenidos al mejor Curso Fullstack Básico
=======
Bienvenidos al Curso de Desarrollo Web
>>>>>>> feature/nuevo-texto
```

Estas marcas indican:

* `<<<<<<< HEAD`: tu versión actual.
* `=======`: separador entre ambas versiones.
* `>>>>>>>`: versión proveniente de la otra rama.

Tu trabajo consiste en decidir cuál conservar o cómo combinarlas.

---

## Cómo resolver un conflicto paso a paso

### 1. Revisa qué archivos tienen conflictos

```bash
git status
```

Git mostrará los archivos que necesitan atención.

### 2. Abre el archivo afectado

Busca las marcas `<<<<<<<`, `=======` y `>>>>>>>`.

### 3. Edita el contenido

Elimina las marcas y deja únicamente el texto o código que deseas conservar.

Por ejemplo:

```txt
Bienvenidos al mejor Curso de Desarrollo Web
```

### 4. Guarda el archivo

Una vez corregido, indícale a Git que el conflicto fue resuelto:

```bash
git add nombre-del-archivo
```

### 5. Finaliza el proceso

Si estabas realizando un merge, crea el commit correspondiente:

```bash
git commit
```

---

## Ejercicio práctico

1. Crea una nueva rama.

```bash
git checkout -b feature/prueba-conflicto
```

2. Modifica una línea de un archivo y realiza un commit.

3. Regresa a `main`.

```bash
git checkout main
```

4. Modifica la misma línea con un contenido diferente y realiza otro commit.

5. Ejecuta:

```bash
git merge feature/prueba-conflicto
```

6. Observa el conflicto generado.

7. Resuélvelo manualmente y finaliza el merge.

---

## Buenas prácticas

* Haz `git pull` antes de empezar a trabajar.
* Realiza commits pequeños y frecuentes.
* Trabaja en ramas independientes para cada funcionalidad.
* Comunícate con tu equipo cuando varios desarrolladores modifiquen los mismos archivos.
* Revisa cuidadosamente el resultado antes de confirmar la resolución del conflicto.

---

## Errores comunes

* Eliminar las marcas del conflicto sin revisar el contenido.
* Elegir una versión y perder cambios importantes de la otra.
* Confirmar (`commit`) sin probar que el proyecto sigue funcionando.
* Trabajar muchos días sin sincronizar con la rama principal.

---

## Resumen

Un conflicto en Git no significa que algo esté roto; simplemente indica que Git necesita ayuda para decidir cómo combinar dos cambios incompatibles.

Resolver conflictos es parte del trabajo diario de los equipos de desarrollo y, con práctica, se convierte en una tarea sencilla y rutinaria.

---

## Actividad para el estudiante

1. Simula un conflicto siguiendo el ejercicio práctico.
2. Resuélvelo manualmente.
3. Verifica que el proyecto funcione correctamente.
4. Comparte con el docente una captura del `git status` antes y después de resolver el conflicto.
