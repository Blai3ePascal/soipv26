# Curso BASHico v1.0 – Bash Scripting Simulator (Single-HTML)

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![Modo](https://img.shields.io/badge/Modo-Entrenamiento%20Bash%20%7C%20Scripting-critical)
![Rol](https://img.shields.io/badge/Rol-Docente%20%7C%20Estudiante-informational)
![Stack](https://img.shields.io/badge/Stack-HTML%2FCSS%2FJavaScript%2FTailwind%2FLucide-blueviolet)
![Niveles](https://img.shields.io/badge/Niveles-50-success)
![Entrega](https://img.shields.io/badge/Entrega-Single%20HTML%20File-orange)
![Plataforma](https://img.shields.io/badge/Plataforma-GitHub%20Pages%20%7C%20Moodle-0aa2ff)

> **Objetivo:** que el alumnado aprenda **Bash scripting** de forma incremental mediante un simulador tipo “editor + consola”, con **misiones guiadas**, **teoría integrada (man page)**, **pistas/soluciones**, validación automática y progreso guardado en el navegador.

---

## Índice

1. [Descripción del simulador (ES)](#1-descripción-del-simulador-es)  
   1.1 [Qué incluye y qué no incluye](#11-qué-incluye-y-qué-no-incluye)  
   1.2 [Qué se aprende](#12-qué-se-aprende)  
2. [Cómo usarlo (ES)](#2-cómo-usarlo-es)  
   2.1 [Flujo de trabajo del alumno](#21-flujo-de-trabajo-del-alumno)  
   2.2 [Pistas y soluciones (scaffolding)](#22-pistas-y-soluciones-scaffolding)  
3. [Mapa de contenidos por niveles (ES)](#3-mapa-de-contenidos-por-niveles-es)  
4. [Ejemplos de soluciones (ES)](#4-ejemplos-de-soluciones-es)  
5. [Arquitectura e implementación (ES)](#5-arquitectura-e-implementación-es)  
   5.1 [SPA monolítica “todo en uno”](#51-spa-monolítica-todo-en-uno)  
   5.2 [Motor de niveles: objetivos + check](#52-motor-de-niveles-objetivos--check)  
   5.3 [Consola simulada y ejecución](#53-consola-simulada-y-ejecución)  
   5.4 [Persistencia del progreso](#54-persistencia-del-progreso)  
   5.5 [Temas visuales y accesibilidad](#55-temas-visuales-y-accesibilidad)  
6. [Uso docente sugerido (ES)](#6-uso-docente-sugerido-es)  
7. [Exercise overview (EN)](#7-exercise-overview-en)  
8. [How it works (EN)](#8-how-it-works-en)  
9. [Learning goals (EN)](#9-learning-goals-en)  
10. [License](#10-license)

---

## 1. Descripción del simulador (ES)

**Curso BASHico v1.0** es un simulador formativo para practicar **Bash scripting** sin instalar nada. El alumno trabaja dentro de un entorno tipo:

- Panel izquierdo con **misión** (objetivo del nivel) y **man page** (teoría breve).
- Editor central estilo **nano script.sh** con numeración de líneas.
- Consola inferior con ejecución tipo `./script.sh`, estado (`IDLE/RUNNING/SUCCESS/ERROR`) y salida del “script”.

### ¿Por qué “Single-HTML”?

El simulador está diseñado para distribuirse como **un único archivo HTML**:

- Ideal para **GitHub Pages** (publicación instantánea).
- Ideal para **Moodle**, donde es habitual evitar múltiples ficheros sueltos (JS/CSS/assets) por rutas rotas o limitaciones de empaquetado.

---

### 1.1. Qué incluye y qué no incluye

**Incluye:**
- 50 niveles con progresión incremental.
- Teoría contextual por nivel (“MAN PAGE”).
- Pistas y solución (modo ayuda).
- Verificación automática por nivel (checks con expresiones regulares o validaciones simples).
- Progreso guardado en el navegador (localStorage).
- Temas visuales (retro/cream/gray) y estética terminal.

**No incluye:**
- Ejecución real de Bash en el sistema operativo del alumno.
- Acceso a un filesystem real, procesos reales o permisos reales.

> El diseño busca **seguridad + portabilidad**: el alumnado aprende sintaxis y patrones mentales sin depender de un entorno Linux instalado.

---

### 1.2. Qué se aprende

El curso está pensado para cubrir desde cero hasta una base sólida de scripting:

- Salida estándar: `echo`
- Estructura mínima de script: `#!/bin/bash`
- Variables y expansión: `VAR=...` y `$VAR`
- Comentarios: `# ...`
- Comillas simples vs dobles
- Entrada de usuario: `read`
- Aritmética: `expr` y `$((...))`
- Variables de entorno: `$HOME`, `$USER`
- Condicionales: `if / elif / else / fi`
- Comparaciones numéricas y de strings
- Comprobación de archivos: `-f`, `-d`, `-e`, negación `!`
- Operadores lógicos: `&&` y `||`
- Bucles: `for` (lista/rango/C-style), `while`, `until`
- Control de bucle: `break`, `continue`
- Globbing: `*.txt`
- Lectura de archivos: `while read ... done < file`
- Menús simples: `select`
- Argumentos: `$0`, `$1`, `$#`, `$@`
- Funciones, argumentos de función, `local`
- Códigos de salida: `$?`, `return`
- Sustitución de comandos: `VAR=$(cmd)`
- Pipes y redirecciones: `|`, `>`, `>>`
- Procesamiento de texto: `grep`, `cut`, `sed`, `awk`
- `case` y arrays
- Ejercicio de cierre (graduación) combinando estructuras

---

## 2. Cómo usarlo (ES)

### 2.1. Flujo de trabajo del alumno

1. Selecciona un nivel desde **SELECCIONAR NIVEL**.
2. Lee la **misión** (objetivo).
3. Consulta **MAN PAGE** si necesitas teoría.
4. Escribe o completa el script en el editor.
5. Ejecuta con el botón:


./EJECUTAR\_SCRIPT.SH


6. Observa la salida y el estado:
- `SUCCESS` si cumple el objetivo.
- `ERROR` si no cumple.
7. Si es `SUCCESS`, pulsa **SIGUIENTE NIVEL >>**.

---

### 2.2. Pistas y soluciones (scaffolding)

El panel de misión incluye dos ayudas:

- **SOLICITAR PISTA (HINT)**  
  Muestra una guía breve para desbloquear el nivel sin regalarlo completo.

- **ACCEDER A SOLUCIÓN (CHEAT)**  
  Muestra una posible solución (útil en docencia como apoyo, o para recuperar ritmo).

> En aula, se recomienda “Hint primero, solución después”, para mantener aprendizaje activo.

---

## 3. Mapa de contenidos por niveles (ES)

> Resumen por bloques. El simulador incluye 50 niveles numerados.

### Bloque A — Fundamentos (1–10)
- `echo`, shebang
- variables + `$`
- comentarios
- comillas dobles/simples
- `read`
- aritmética (`expr`, `$(( ))`)
- variables de entorno (`$HOME`)

### Bloque B — Condicionales y pruebas (11–20)
- `if/fi`, `-eq`, `=`
- `else`, `elif`
- tests `-f`, `-d`, negación `!`
- `&&` y `||`

### Bloque C — Bucles (21–30)
- `for` (lista, rango `{1..5}`, C-style)
- `while`, `until`
- `break`, `continue`
- globbing `*.txt`
- lectura de archivo línea a línea
- `select`

### Bloque D — Argumentos y funciones (31–40)
- `$1`, `$#`, `$@`, `$0`
- funciones, argumentos en funciones
- `local`
- `$?` exit codes
- `return`
- sustitución de comandos `$(...)`

### Bloque E — Tuberías y “text tools” (41–49)
- pipes `|`
- redirecciones `>`, `>>`
- `grep`, `cut`, `sed`, `awk`
- `case`
- arrays

### Bloque F — Graduación (50)
- reto final combinando `for`, `if`, `echo`

---

## 4. Ejemplos de soluciones (ES)

A continuación se muestran ejemplos representativos (no necesariamente idénticos a un nivel exacto, pero consistentes con los objetivos del curso).

### 4.1. Script mínimo correcto
```bash
#!/bin/bash
echo "Sistema listo"
```

### 4.2. Variables y expansión

```bash
#!/bin/bash
AGENTE=007
echo "ID: $AGENTE"
```

### 4.3. Read + control básico

```bash
#!/bin/bash
echo "Introduce password:"
read PASSWORD
echo "Recibido: $PASSWORD"
```

### 4.4. If numérico

```bash
#!/bin/bash
EDAD=15
if [ $EDAD -gt 18 ]; then
  echo "Adulto"
elif [ $EDAD -gt 12 ]; then
  echo "Adolescente"
else
  echo "Niño"
fi
```

### 4.5. For por rango

```bash
#!/bin/bash
for N in {1..5}; do
  echo $N
done
```

### 4.6. Argumentos del script

```bash
#!/bin/bash
echo "Script: $0"
echo "Primer argumento: $1"
echo "Total argumentos: $#"
```

### 4.7. Pipes + grep

```bash
#!/bin/bash
ls -l | grep ".sh"
```

### 4.8. Redirecciones

```bash
#!/bin/bash
echo "Inicio" > log.txt
echo "Paso 2" >> log.txt
```

### 4.9. Procesamiento con cut

```bash
#!/bin/bash
echo "root:x:0:0" | cut -d ":" -f 1
```

### 4.10. Sed y awk

```bash
#!/bin/bash
echo "Hola Mundo" | sed 's/Mundo/BASH/'
echo "A B C" | awk '{print $2}'
```

---

## 5\. Arquitectura e implementación (ES)

### 5.1. SPA monolítica “todo en uno”

El simulador es una **Single Page Application** sin backend:

-   HTML estructura (paneles, editor, consola, modales).
    
-   CSS (estética terminal + CRT overlay + temas).
    
-   JS para niveles, validación, progreso y UI.
    

Dependencias por CDN:

-   **TailwindCSS** (maquetación rápida y consistente)
    
-   **Lucide** (iconos)
    

---

### 5.2. Motor de niveles: objetivos + check

El curso define un array de niveles. Cada nivel contiene (conceptualmente):

-   `id`: número de nivel
    
-   `title`: título del objetivo
    
-   `desc`: descripción (misión)
    
-   `man`: teoría del comando o concepto
    
-   `init`: plantilla inicial del script
    
-   `sol`: solución sugerida (cheat)
    
-   `hint`: pista (hint)
    
-   `check(code)`: función que valida el script
    
-   `out`: salida esperada mostrada en consola cuando es correcto
    

**Claves didácticas del diseño:**

-   El nivel no evalúa “código perfecto”, evalúa **si cumples el objetivo**.
    
-   Las verificaciones suelen ser:
    
    -   Expresiones regulares (por ejemplo, detectar `echo "Hola Mundo"`).
        
    -   Condiciones simples (por ejemplo, presencia de `fi`).
        

Esto permite progresión rápida, feedback inmediato y coste de mantenimiento bajo.

---

### 5.3. Consola simulada y ejecución

Al pulsar **./EJECUTAR\_SCRIPT.SH**:

1.  Se imprime `> ./script.sh`.
    
2.  Cambia el estado a `RUNNING` (con animación).
    
3.  Tras un breve delay, se evalúa `check(code)`:
    
    -   Si es correcto:
        
        -   se imprime `out`
            
        -   se imprime `[EXIT CODE 0] SUCCESS`
            
        -   aparece modal **¡MISIÓN CUMPLIDA!**
            
    -   Si es incorrecto:
        
        -   se imprime un error genérico
            
        -   se imprime `[EXIT CODE 1] FAILURE`
            
        -   se mantiene el nivel
            

> Importante: el simulador no ejecuta Bash real. Simula salida y exit codes con objetivos didácticos.

---

### 5.4. Persistencia del progreso

El nivel actual se guarda en el navegador mediante **localStorage**:

-   Se almacena el índice del nivel.
    
-   Al reabrir el simulador, carga automáticamente el último nivel.
    

Incluye botón **\[ RESET SYSTEM \]** que:

-   borra el progreso
    
-   vuelve al nivel inicial
    
-   reabre el modal de introducción
    

---

### 5.5. Temas visuales y accesibilidad

El simulador incluye un selector rápido de temas:

-   **Retro Hacker** (verde/negro + CRT overlay)
    
-   **Cream** (alto contraste suave tipo “Solarized claro”)
    
-   **Gray** (modo documentación / neutro)
    

Esto permite adaptar el simulador a:

-   aulas con proyectores,
    
-   sensibilidad visual,
    
-   preferencias personales del alumnado.
    

---

## 6\. Uso docente sugerido (ES)

### Sesión 1 (50–60 min) — Fundamentos y control básico

-   Niveles 1–10: echo, shebang, variables, comillas, read, aritmética, env vars
    
-   Cierre: mini-reto “script mínimo correcto”
    

**Evaluación rápida:**

-   ¿saben explicar `VAR=...` vs `echo $VAR`?
    

### Sesión 2 (50–70 min) — Condicionales

-   Niveles 11–20: if/else/elif, tests, `&&` y `||`
    
-   Actividad: script de acceso “clave correcta / denegado”
    

**Evaluación rápida:**

-   ¿diferencian `-eq` de `=`?
    

### Sesión 3 (60–90 min) — Bucles y automatización

-   Niveles 21–30: for/while/until, globbing, lectura de archivos, select
    
-   Actividad: procesar lista de entradas (pseudo log) y responder
    

**Evaluación rápida:**

-   ¿entienden `break/continue`?
    

### Sesión 4 (60–90 min) — Herramientas UNIX y flujo de texto

-   Niveles 41–49: pipes, redirecciones, grep/cut/sed/awk
    
-   Actividad: “pipeline” de extracción y sustitución
    

**Evaluación rápida:**

-   ¿saben leer “input → output” con `|`?
    

### Cierre

-   Nivel 50: combinación de estructuras en un script final.
    
-   Entrega sugerida: captura del “SUCCESS” + script final + breve explicación.
    

---

# 7\. Exercise overview (EN)

**Curso BASHico v1.0** is a browser-based Bash scripting simulator designed to teach core CLI scripting concepts through guided missions.

It features:

-   50 progressively structured levels
    
-   Integrated theory (“man page”) per level
    
-   Hints and solutions for scaffolding
    
-   Automatic checks and immediate feedback
    
-   Local progress saving (browser storage)
    
-   Single-file HTML distribution (ideal for GitHub Pages and Moodle)
    

---

# 8\. How it works (EN)

Each level contains:

-   A mission objective and short explanation
    
-   A starter script template
    
-   A validation function (`check(code)`)
    
-   A simulated console output on success
    

When the student runs the script:

-   The simulator validates the code (pattern checks)
    
-   Displays a success/failure exit code
    
-   Unlocks the next mission on success
    

No real Bash execution occurs, which keeps the environment safe and portable.

---

# 9\. Learning goals (EN)

By completing the course, students will be able to:

-   Write basic Bash scripts with correct structure (`#!/bin/bash`)
    
-   Use variables and expansions properly
    
-   Read user input and perform simple arithmetic
    
-   Build conditionals and file tests
    
-   Work with loops and script arguments
    
-   Create functions and understand exit codes
    
-   Use pipes and redirections for automation
    
-   Apply standard text tools (grep/cut/sed/awk)
    
-   Combine fundamentals into a final mini-project
    

---

# 10\. License

Released under the **MIT License**.

```text
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy...
```
