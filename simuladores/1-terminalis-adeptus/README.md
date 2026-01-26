# Terminalis Adeptus – Protocolo Génesis (El Ritual de la Terminal)

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![Modo](https://img.shields.io/badge/Modo-Simulador%20UNIX%20%7C%20Terminal-critical)
![Rol](https://img.shields.io/badge/Rol-Magos%20del%20Sistema%20%7C%20Aprendiz%20Sysadmin-informational)
![Stack](https://img.shields.io/badge/Stack-HTML%2FCSS%2FJavaScript%2FTailwind-blueviolet)
![Ritos](https://img.shields.io/badge/Ritos-39%20Protocolos-success)

> **Objetivo:** entrenar comandos esenciales de **UNIX/Linux** en un entorno **seguro**, inmersivo y “gamificado”, con progresión por **ritos**, retroalimentación inmediata y una narrativa (“lore”) tipo *tecno-ritual*.

---

## Índice (ES)

1. [Qué es Terminalis Adeptus](#1-qué-es-terminalis-adeptus)
2. [Cómo jugar](#2-cómo-jugar)
3. [Objetivos de aprendizaje](#3-objetivos-de-aprendizaje)
4. [Ritos (niveles) y progresión](#4-ritos-niveles-y-progresión)
5. [Comandos disponibles](#5-comandos-disponibles)
6. [Economía: Créditos, Herejía y Estrés](#6-economía-créditos-herejía-y-estrés)
7. [Ejemplos de soluciones](#7-ejemplos-de-soluciones)
8. [Cómo está implementado](#8-cómo-está-implementado)
9. [Uso docente](#9-uso-docente)
10. [Licencia](#10-licencia)

---

## 1. Qué es Terminalis Adeptus

**Terminalis Adeptus – Protocolo Génesis** es un simulador de terminal diseñado para *Sistemas Operativos* y formación inicial en CLI.

- Funciona **100% en el navegador**: no necesita backend.
- Está construido como **un único archivo HTML** (ideal para **GitHub Pages** o para **Moodle**, donde a menudo conviene evitar múltiples ficheros sueltos).
- Modela un sistema de archivos y un conjunto de comandos “tipo UNIX” de forma **simulada** (sin ejecutar nada real en tu equipo).
- Convierte el aprendizaje en una secuencia de **39 ritos**: cada uno propone un objetivo concreto, una explicación y un trigger de éxito.

### Lore (ambientación)

En este entrenamiento, la terminal no es una interfaz: es un **cogitador sagrado**.  
Cada comando es un **rito** y cada error alimenta la **herejía** del sistema. Tu misión es dominar el protocolo antes de que la corrupción supere los límites tolerables.

> “No hay certeza en la carne. Solo hay certeza en el acero.”

---

## 2. Cómo jugar

1. Abre el simulador en el navegador.
2. Lee la narrativa del **Protocolo (Rito)** actual.
3. Ejecuta en la terminal el comando que cumple el **objetivo**.
4. Si aciertas, aparece un panel de éxito y desbloqueas el siguiente rito.
5. Si fallas, pierdes créditos y aumenta la herejía (corrupción).

### Controles principales

- **Input de terminal**: escribe comandos y pulsa `Enter`.
- **Panel de ayuda**: cada rito incluye explicación y pista técnica.
- **CÓDIGO del rito**: cada nivel tiene un identificador para navegación docente.
- **TEMA**: cambia el estilo visual (inmersión / accesibilidad).
- **EFECTOS ESTRÉS**: activa/desactiva glitch y efectos de presión.

---

## 3. Objetivos de aprendizaje

Al completar el Protocolo Génesis, el alumnado debería poder:

- Navegar por el sistema de archivos (rutas absolutas/relativas).
- Listar, leer y crear archivos y directorios.
- Mover, copiar y eliminar recursos de forma segura.
- Interpretar permisos y propiedad de archivos.
- Usar utilidades de búsqueda de texto (**grep** / patrones).
- Identificar procesos y aplicar acciones básicas (**ps** / **kill**).
- Comprender comandos de soporte (manuales, ayuda, utilidades).
- Empezar a construir “automatizaciones” simples mediante scripts y redirecciones.

---

## 4. Ritos (niveles) y progresión

El simulador se estructura como una campaña de **39 protocolos**.

- Cada rito tiene:
  - **Narrativa** (contexto)
  - **Objetivo** (comando esperado)
  - **Explicación** (micro-lección)
  - **Solución sugerida** (para el modo docente o asistencia)
- Al completar el último rito, se muestra un final de “maestría” y la puntuación total.

---

## 5. Comandos disponibles

Terminalis Adeptus implementa un subconjunto práctico de comandos UNIX, de manera simulada (no toca tu sistema real).

Ejemplos de comandos incluidos en el simulador:

- Navegación y exploración: `pwd`, `ls`, `cd`, `cat`
- Gestión de recursos: `touch`, `mkdir`, `rm`, `cp`, `mv`
- Texto: `echo`, `grep`
- Procesos: `ps`, `kill`
- Permisos y propiedad: `chmod`, `chown`
- Red/paquetes: `wget`, `apt`, `sudo`
- Ayuda: `help`, `man`, `apropos`
- Archivado: `tar`
- Utilidades: `clear`

> Nota: algunos comandos muestran resultados plausibles pero **simulados** (por diseño didáctico).

---

## 6. Economía: Créditos, Herejía y Estrés

El simulador añade una capa de juego para reforzar hábitos útiles:

### Créditos (puntuación)
- Sirven para medir el rendimiento y habilitar acciones auxiliares.
- Algunas utilidades del “cogitador” requieren créditos (ver tienda).

### Nivel de Herejía (corrupción)
- Sube con el tiempo y con errores.
- Baja al completar ritos con éxito.
- Si llega al máximo, el sistema puede entrar en eventos de “backlash” (penalizaciones).

### Estrés (efectos visuales)
- Puede activarse o desactivarse.
- En modo ON, intensifica feedback visual cuando la herejía es alta.

### Tienda / asistencia
- **Requisición de solución**: permite ver el comando sugerido para el rito actual (modo apoyo).
- **Rito de purificación**: reduce la herejía mediante gasto de créditos.

---

## 7. Ejemplos de soluciones

> Estos ejemplos son representativos. En algunos ritos se admite más de una solución equivalente.

### 7.1. Exploración y rutas

```bash
pwd
ls
ls -la
cd archives
cd ..
cd /home/adeptus/temple_entrance
```

### 7.2. Lectura de evidencias

```bash
cat servo_skull_log.txt
cat heresy_detected.log
```

### 7.3. Crear estructura de contención (cuarentena)

```bash
mkdir cuarentena
mv heresy_detected.log cuarentena/
ls cuarentena
```

### 7.4. Copias controladas y archivo

```bash
cp altar_data.txt archives/
tar -czf backup_archives.tar.gz archives
```

### 7.5. Búsqueda de patrones (forense básico)

```bash
grep ERROR servo_skull_log.txt
grep "Herejía" servo_skull_log.txt
```

### 7.6. Procesos y contención

```bash
ps
ps aux
kill 666
```

### 7.7. Permisos y ejecución (script)

```bash
touch script.sh
echo '#!/bin/bash' > script.sh
echo 'echo "Hola Mundo"' >> script.sh
chmod +x script.sh
./script.sh
```

---

## 8\. Cómo está implementado

> Esta sección está pensada para quien quiera **mantener** o **extender** el simulador.

### 8.1. Arquitectura técnica

-   **SPA monolítica**: todo el simulador vive en un único HTML.
    
-   UI con clases tipo **utility-first** (Tailwind por CDN) y estilos propios.
    
-   Un motor interno que:
    
    1.  **Parsea** el input del usuario.
        
    2.  **Simula** el resultado del comando (output/errores).
        
    3.  Evalúa si el comando cumple el **trigger** del rito actual.
        
    4.  Actualiza puntuación, herejía y progreso.
        

### 8.2. Sistema de archivos simulado

Se define un árbol con nodos de tipo:

-   `dir` con `content` (hijos)
    
-   `file` con `content`, `size`, `owner`, `perms`
    

Esto permite que comandos como `ls`, `cd`, `cat`, `cp`, `mv`, `rm` y `touch` funcionen con coherencia.

### 8.3. Motor de comandos

La función principal del simulador implementa:

-   Resolución de rutas absolutas y relativas (`..`, `.`)
    
-   Lectura y escritura simulada
    
-   Errores tipo Bash (`No existe el archivo o el directorio`, etc.)
    
-   Resultados plausibles para:
    
    -   `wget` (descarga simulada)
        
    -   `apt` (instalación simulada)
        
    -   `tar` (creación de archivo tar simulado)
        

### 8.4. Motor de ritos

Cada rito incluye:

-   `code` (identificador para salto docente)
    
-   `objective` (lo que se pide)
    
-   `solutionCmd` (solución para asistencia)
    
-   `trigger(cmd)` (condición de éxito)
    

Este enfoque permite crear nuevos ritos muy rápido:

-   Añades un objeto al array `levels`
    
-   Defines el texto y el trigger
    
-   Listo: ya tienes un nivel nuevo
    

### 8.5. Persistencia (guardado)

El simulador guarda el estado en el navegador:

-   nivel actual
    
-   créditos
    
-   tema visual
    
-   efectos de estrés
    

Esto permite retomar la práctica sin perder progreso.

---

## 9\. Uso docente

Sugerencias prácticas para clase:

1.  **Demostración guiada (10 min)**
    
    -   Primeros ritos: `pwd`, `ls`, `cd`, `cat`
        
2.  **Trabajo por parejas (20–30 min)**
    
    -   Objetivo: llegar a ritos de cuarentena, grep y permisos
        
3.  **Debrief**
    
    -   ¿Qué comando te dio más problemas y por qué?
        
    -   ¿Qué errores fueron “conceptuales” vs “sintácticos”?
        
4.  **Evaluación ligera**
    
    -   Puntuación final (créditos)
        
    -   Nivel alcanzado
        
    -   Corrección de soluciones y alternativas válidas
        

### Consejos de accesibilidad

-   Si el alumnado se satura con el feedback visual, desactivar **EFECTOS ESTRÉS**.
    
-   Si se atascan, usar “solución” como *scaffold* (no como sustituto del aprendizaje).
    

---

## 10\. Licencia

Este proyecto se publica bajo licencia **MIT**.

```text
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files...
```

---

**Créditos:** Creado por Pascal. Gloria al Omnissiah.
