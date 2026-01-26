# CSimulator Pro – C & Pointers Mastery (El Taller del Compilador)

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![Modo](https://img.shields.io/badge/Modo-Simulador%20de%20Compilación%20GCC-critical)
![Rol](https://img.shields.io/badge/Rol-Docente%20%7C%20Estudiante-informational)
![Stack](https://img.shields.io/badge/Stack-HTML%2FCSS%2FJavaScript%2FTailwind%2FLucide-blueviolet)
![Rutas](https://img.shields.io/badge/Rutas-General%20%2B%20Punteros-success)
![Tema](https://img.shields.io/badge/Temas-Dark%20%7C%20Cream%20%7C%20Gray-important)

> **Objetivo:** que el alumnado aprenda **programación en C** paso a paso con un entorno tipo **IDE**, validación inmediata y progresión por niveles; y que entienda (de verdad) el corazón de C: **punteros, direcciones, memoria, argumentos** y **I/O** (syscalls + stdio) sin necesidad de instalar nada.

---

## Índice

1. [Descripción del simulador (ES)](#1-descripción-del-simulador-es)  
   1.1 [Qué entrena exactamente](#11-qué-entrena-exactamente)  
   1.2 [Las dos rutas: General y Punteros](#12-las-dos-rutas-general-y-punteros)  
2. [Cómo usarlo (ES)](#2-cómo-usarlo-es)  
3. [Objetivos didácticos (ES)](#3-objetivos-didácticos-es)  
4. [Ejemplos de soluciones (ES)](#4-ejemplos-de-soluciones-es)  
5. [Cómo funciona por dentro (ES)](#5-cómo-funciona-por-dentro-es)  
   5.1 [Arquitectura técnica](#51-arquitectura-técnica)  
   5.2 [Motor de validación: “compilar” sin compilar](#52-motor-de-validación-compilar-sin-compilar)  
   5.3 [Visualizador de RAM (modo punteros)](#53-visualizador-de-ram-modo-punteros)  
   5.4 [Progreso, reinicio y temas](#54-progreso-reinicio-y-temas)  
6. [Uso docente sugerido (ES)](#6-uso-docente-sugerido-es)  
7. [Exercise overview (EN)](#7-exercise-overview-en)  
8. [How to use in class (EN)](#8-how-to-use-in-class-en)  
9. [Learning goals (EN)](#9-learning-goals-en)  
10. [Implementation notes (EN)](#10-implementation-notes-en)  
11. [Licencia](#11-licencia)  
12. [Glosario rápido](#12-glosario-rápido)  

---

## 1. Descripción del simulador (ES)

**CSimulator Pro** es un simulador educativo “todo en uno” (un único **HTML**) que recrea una experiencia tipo **Visual Studio Code + GCC** para aprender C.

- Se ejecuta **100% en el navegador** (sin backend).
- Está pensado para **GitHub Pages** o **Moodle**, donde es útil que todo viva dentro de **un único archivo**.
- Cada nivel viene con:
  - una **instrucción concreta**,
  - un **código inicial**,
  - una **pista**,
  - una **solución** (opcional),
  - y una validación automática que determina si has completado el reto.

---

### 1.1. Qué entrena exactamente

El simulador está diseñado para reforzar competencias reales de C:

- Sintaxis esencial: `main`, `return`, `printf`, comentarios.
- Variables y tipos: `int`, `char`, `float`, `const`.
- Operaciones y lógica: `+`, `*`, `if/else`, `==`, `%`.
- Control de flujo: `while`, `for`, `i++`.
- Cadenas y punteros: arrays de `char`, `char*`, desreferencia `*`.
- Argumentos: `argc`, `argv[]`.
- Construcción realista de CLI: `getopt`, `optarg`, `optind`.
- Ficheros nivel Kernel: `open`, `read`, `write`, `close`, `lseek`.
- Ficheros nivel stdio: `fopen`, `fread`, `fwrite`, `fclose`, `fseek`.

---

### 1.2. Las dos rutas: General y Punteros

CSimulator Pro se organiza como un “doble curso”:

#### Ruta A — Curso General
Ideal para empezar desde cero y llegar a un dominio funcional:
- Fundamentos → control de flujo → tipos → strings → CLI → ficheros (syscalls y stdio).

Incluye una graduación final cuando completas el itinerario.

#### Ruta B — Curso de Punteros y Memoria (RAM Lab)
Enfocado a lo más importante de C:
- direcciones (`&`), punteros (`int *p`),
- desreferencia (`*p`),
- punteros a arrays,
- estructuras con `->`,
- heap con `malloc` (y la idea de vida útil de la memoria).

En esta ruta, la salida clásica se sustituye por un **visualizador de RAM**.

---

## 2. Cómo usarlo (ES)

1. Abre el simulador en el navegador.
2. Elige una ruta:
   - **General**
   - **Punteros**
3. Lee la consigna y escribe tu solución en el editor.
4. Pulsa el botón de **compilar/ejecutar**.
5. Si el nivel es correcto:
   - recibirás feedback de éxito,
   - y podrás avanzar al siguiente nivel.
6. Si fallas:
   - verás un error explicativo,
   - y una pista útil para corregirlo.

### Funciones de apoyo
- **Ayuda**: muestra explicación y pista del nivel.
- **Solución (si está habilitada)**: muestra un ejemplo de resolución.
- **Salto de nivel**: el docente puede saltar a un ejercicio concreto.
- **Reinicio total**: borra el progreso de ambos cursos.

---

## 3. Objetivos didácticos (ES)

Al finalizar el uso del simulador, el alumnado debería ser capaz de:

1. Escribir programas sencillos en C siguiendo buenas prácticas básicas.
2. Entender la diferencia entre:
   - **asignar** (`=`) y **comparar** (`==`).
3. Dominar bucles y condicionales para resolver lógica de control.
4. Imprimir y formatear salida con `printf` (`%d`, `%c`, `%f`, `%s`, `%p`).
5. Comprender qué es una dirección de memoria y por qué importan los punteros.
6. Entender el modelo mental:
   - **Stack** (automático) vs **Heap** (manual).
7. Leer argumentos por línea de comandos (`argc/argv`) como lo hace un comando real.
8. Reconocer el valor de `getopt` para construir herramientas CLI profesionales.
9. Diferenciar I/O de bajo nivel (**syscalls**) vs alto nivel (**stdio**).
10. Conectar C con Sistemas Operativos: file descriptors, lectura/escritura y posicionamiento.

---

## 4. Ejemplos de soluciones (ES)

> En el simulador hay muchas micro-soluciones. Aquí tienes ejemplos “tipo” para entender el estilo.

### 4.1. Hello World con salto de línea
```c
#include <stdio.h>

int main() {
    printf("Hola\n");
    return 0;
}
```

### 4.2. Variables + printf con placeholder

```c
#include <stdio.h>

int main() {
    int puntos = 50;
    printf("Puntos: %d\n", puntos);
    return 0;
}
```

### 4.3. If / else

```c
#include <stdio.h>

int main() {
    int puntos = 5;

    if (puntos > 10) {
        printf("Ganaste\n");
    } else {
        printf("Perdiste\n");
    }

    return 0;
}
```

### 4.4. Bucle for

```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 3; i++) {
        printf("%d", i);
    }
    return 0;
}
```

### 4.5. Punteros: dirección y desreferencia

```c
#include <stdio.h>

int main() {
    int numero = 50;
    int *p = &numero;

    printf("Direccion: %p\n", &numero);
    printf("Valor via puntero: %d\n", *p);

    *p = 100;
    printf("Numero ahora: %d\n", numero);

    return 0;
}
```

### 4.6. CLI realista: argc / argv

```c
#include <stdio.h>

int main(int argc, char *argv[]) {
    printf("argc = %d\n", argc);
    printf("argv[1] = %s\n", argv[1]);
    return 0;
}
```

### 4.7. Syscalls (Kernel I/O): open/write/close

```c
#include <fcntl.h>
#include <unistd.h>
#include <stdio.h>

int main() {
    int fd = open("datos.txt", O_CREAT | O_WRONLY, 0644);
    write(fd, "Hola", 4);
    close(fd);
    return 0;
}
```

### 4.8. StdIO: fopen/fwrite/fclose

```c
#include <stdio.h>

int main() {
    FILE *f = fopen("notas.txt", "w");
    fwrite("ABC", 1, 3, f);
    fclose(f);
    return 0;
}
```

---

## 5\. Cómo funciona por dentro (ES)

### 5.1. Arquitectura técnica

-   Es una **SPA** sin backend.
    
-   UI renderizada dinámicamente.
    
-   Editor central con numeración de líneas y un panel derecho:
    
    -   **Consola de salida** (curso general)
        
    -   **Visualizador de RAM** (curso punteros)
        
-   Estética inspirada en IDE moderno, con barra de estado (archivo activo, líneas, “GCC simulado”).
    

---

### 5.2. Motor de validación: “compilar” sin compilar

Este simulador **no ejecuta C real** (por seguridad y portabilidad).  
En su lugar, cada nivel define una función de **validación** que inspecciona el texto del código:

-   Si detecta la estructura esperada (por ejemplo, un `printf("Hola\n");`) → nivel correcto.
    
-   Si falta algo → devuelve un error explicativo y el reto sigue activo.
    

Esto da una experiencia muy parecida a:

-   escribir código,
    
-   compilar,
    
-   obtener output o error,
    
-   corregir,
    
-   avanzar.
    

---

### 5.3. Visualizador de RAM (modo punteros)

En la ruta de punteros, el simulador añade una capa diferencial:

-   Cada nivel puede definir un estado inicial de memoria (`memoryInit`).
    
-   Al resolver un reto, puede devolver `memoryUpdate` para cambiar valores y direcciones.
    
-   El alumnado ve explícitamente:
    
    -   direcciones (ej. `0x7FF0`, `0x8000`)
        
    -   qué variable vive ahí
        
    -   qué valor guarda
        
    -   y cuándo un puntero apunta a otra dirección
        

**Resultado:** los punteros dejan de ser magia y pasan a ser *mapa*.

---

### 5.4. Progreso, reinicio y temas

-   El simulador guarda progreso separado por ruta (**General** y **Punteros**).
    
-   Incluye un modal de **reinicio total** para empezar desde cero.
    
-   Ofrece temas visuales para adaptar legibilidad:
    
    -   oscuro (default)
        
    -   claro tipo “cream”
        
    -   gris “documentación”
        

---

## 6\. Uso docente sugerido (ES)

### Sesión 1 (45–60 min): Fundamentos y control

-   Niveles: `main`, `printf`, variables, if/else, bucles.
    
-   Objetivo: que el alumnado no “memorice”, sino que explique por qué funciona.
    

### Sesión 2 (45–60 min): Strings, CLI y herramientas

-   `char[]`, `%s`, `argc/argv`, mini-retos de argumentos.
    
-   Cierre con introducción a `getopt`: por qué los programas reales lo usan.
    

### Sesión 3 (60–90 min): I/O + Sistemas Operativos

-   Syscalls + stdio.
    
-   Diferencia conceptual:
    
    -   `open/read/write/close` = kernel, file descriptor
        
    -   `fopen/fread/fwrite/fclose` = biblioteca, buffers
        

### Laboratorio extra: Punteros + RAM Lab

-   Modo punteros como actividad “de choque”
    
-   Evaluación rápida:
    
    -   ¿Qué guarda `p`?
        
    -   ¿Qué hace `*p`?
        
    -   ¿Qué hace `&x`?
        
    -   ¿Qué cambia al hacer `p++`?
        

---

## 7\. Exercise overview (EN)

**CSimulator Pro** is a browser-only learning simulator for the C language.  
It delivers a guided experience that looks and feels like a lightweight IDE, with immediate feedback and progressive levels.

It includes two learning paths:

-   **General C course:** fundamentals → control flow → data types → strings → CLI arguments → file I/O (syscalls + stdio)
    
-   **Pointers & Memory Lab:** addresses, pointers, dereferencing, arrays, structs, heap allocation (`malloc`) and a RAM visualizer.
    

Everything runs inside a **single HTML file**, perfect for GitHub Pages or LMS environments.

---

## 8\. How to use in class (EN)

1.  Pick a path (General or Pointers).
    
2.  Read the instructions for the current level.
    
3.  Write code in the editor.
    
4.  Press “compile/run”.
    
5.  Use help/hints if needed.
    
6.  Advance level by level.
    

Recommended setup:

-   Use the **General course** first.
    
-   Then switch to the **Pointers Lab** as a conceptual deep dive.
    

---

## 9\. Learning goals (EN)

After completing the simulator, students should be able to:

-   Build simple programs in C with correct syntax and formatting.
    
-   Understand assignments vs comparisons (`=` vs `==`).
    
-   Use loops and conditionals properly.
    
-   Print formatted output (`%d`, `%c`, `%f`, `%s`, `%p`).
    
-   Explain pointers as “variables storing addresses”.
    
-   Differentiate stack vs heap at a conceptual level.
    
-   Read command-line arguments (`argc/argv`) like real CLI tools.
    
-   Understand the role of `getopt` in professional utilities.
    
-   Distinguish low-level syscalls vs stdio buffered I/O.
    

---

## 10\. Implementation notes (EN)

-   **No real compilation happens.** Each level validates the code text against expected patterns.
    
-   The simulator emulates a typical GCC run (`gcc main.c -o main && ./main`) for realism.
    
-   The Pointers Lab uses a memory table that updates on success to visualize addresses and pointer targets.
    
-   Progress is tracked independently for each course and can be fully reset.
    

---

## 11\. Licencia

Este proyecto se publica bajo licencia **MIT**.

```text
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files...
```

---

## 12\. Glosario rápido

-   **Placeholder**: marcador de formato en `printf` (`%d`, `%s`, etc.).
    
-   **Puntero**: variable que guarda una dirección de memoria.
    
-   **Desreferencia**: usar `*p` para acceder al contenido apuntado.
    
-   **Stack**: memoria automática (variables locales).
    
-   **Heap**: memoria manual (malloc/free).
    
-   **File Descriptor (FD)**: entero que identifica un archivo abierto en syscalls.
    
-   **StdIO**: librería de C basada en `FILE*` con buffers.
    
-   **getopt**: utilidad estándar para flags de programas CLI.
    

---

**Creado por Pascal.** Pensado para aprender C como se aprende de verdad: escribiendo, fallando, corrigiendo y entendiendo.
