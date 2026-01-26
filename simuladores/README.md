# OS Simulators – Interactive Systems Labs (Simuladores de Sistemas Operativos)

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![Modo](https://img.shields.io/badge/Modo-Simulador%20Interactivo-critical)
![Enfoque](https://img.shields.io/badge/Enfoque-Aprendizaje%20por%20Simulación-success)
![Rol](https://img.shields.io/badge/Rol-Docente%20%7C%20Alumno-informational)
![Stack](https://img.shields.io/badge/Stack-HTML%2FCSS%2FJavaScript-blueviolet)
![Entrega](https://img.shields.io/badge/Entrega-Single%20HTML%20File-orange)
![Plataforma](https://img.shields.io/badge/Plataforma-GitHub%20Pages%20%7C%20Moodle-0aa2ff)

> **Objetivo:** proporcionar una colección de **simuladores didácticos de Sistemas Operativos** para el **Grado en Ingeniería del Software**, diseñados para aprender mediante **experimentación controlada**, visualización de estado interno y mecánicas de “reto guiado”.
>
> Estos simuladores están construidos como **aplicaciones web autocontenidas (SPA)** que **funcionan en el navegador** y pueden publicarse como un único archivo **HTML** (ideal para **GitHub Pages** y para entornos como **Moodle**, donde conviene evitar dependencias en ficheros sueltos).

---

## Índice

1. [Descripción general y filosofía (ES)](#1-descripción-general-y-filosofía-es)  
   1.1 [Qué es este repositorio](#11-qué-es-este-repositorio)  
   1.2 [Principios de diseño didáctico](#12-principios-de-diseño-didáctico)  
2. [Arquitectura técnica (ES)](#2-arquitectura-técnica-es)  
   2.1 [Estructura “todo en uno” (Single-HTML)](#21-estructura-todo-en-uno-single-html)  
   2.2 [Motor de simulación y evaluación](#22-motor-de-simulación-y-evaluación)  
   2.3 [UI/UX: temas, paneles y modales](#23-uiux-temas-paneles-y-modales)  
3. [Cómo ejecutar y desplegar (ES)](#3-cómo-ejecutar-y-desplegar-es)  
   3.1 [Ejecución local](#31-ejecución-local)  
   3.2 [Despliegue en GitHub Pages](#32-despliegue-en-github-pages)  
   3.3 [Integración en Moodle](#33-integración-en-moodle)  
4. [Uso en el aula (ES)](#4-uso-en-el-aula-es)  
   4.1 [Dinámicas recomendadas](#41-dinámicas-recomendadas)  
   4.2 [Evaluación y evidencias de aprendizaje](#42-evaluación-y-evidencias-de-aprendizaje)  
5. [Objetivos didácticos (ES)](#5-objetivos-didácticos-es)  
6. [Buenas prácticas de mantenimiento (ES)](#6-buenas-prácticas-de-mantenimiento-es)  
7. [Exercise overview (EN)](#7-exercise-overview-en)  
8. [Technical architecture (EN)](#8-technical-architecture-en)  
9. [Run & deploy (EN)](#9-run--deploy-en)  
10. [How to use in class (EN)](#10-how-to-use-in-class-en)  
11. [Learning goals (EN)](#11-learning-goals-en)  
12. [License](#12-license)  
13. [Glosario / Glossary](#13-glosario--glossary)  

---

# 1. Descripción general y filosofía (ES)

## 1.1. Qué es este repositorio

Este repositorio reúne **simuladores interactivos** orientados a Sistemas Operativos y fundamentos de sistemas, diseñados para:

- Convertir conceptos “invisibles” (estado interno del SO) en **comportamientos observables**.
- Practicar **decisiones técnicas** en un entorno seguro (sin romper una VM ni depender del hardware del aula).
- Desarrollar hábito profesional: **leer salidas**, razonar “causa → efecto” y validar hipótesis.

Los simuladores no buscan sustituir laboratorios con sistemas reales: su objetivo es **acelerar la comprensión** y permitir que el alumnado llegue a la práctica “real” con un mapa mental más sólido.

## 1.2. Principios de diseño didáctico

**Principios base comunes:**

1. **Aprendizaje por interacción**  
   El alumnado no “lee un tema”: ejecuta acciones, observa efectos y ajusta su estrategia.

2. **Estado interno visible**  
   La interfaz muestra indicadores y paneles que reflejan el estado del “sistema simulado” (progreso, logs, consola, memoria conceptual, etc.).

3. **Reto guiado con feedback inmediato**  
   Cada interacción genera retroalimentación clara: éxito, fallo, pista, o corrección sugerida.

4. **Narrativa ligera (opcional)**  
   Algunos simuladores usan una capa narrativa para aumentar atención y retención, pero siempre subordinada al contenido técnico.

5. **Diseño docente-friendly**  
   - Fácil de desplegar (un único HTML).
   - Fácil de resetear.
   - Fácil de usar en aula y evaluable (rúbricas / capturas / entregas).

---

# 2. Arquitectura técnica (ES)

## 2.1. Estructura “todo en uno” (Single-HTML)

Los simuladores se distribuyen como un **archivo HTML único** con:

- **HTML**: estructura y paneles (dashboard, consola, HUD, etc.).  
- **CSS**: estilos integrados (`<style>`) o utilidades (p. ej. Tailwind vía CDN).  
- **JavaScript**: lógica completa (estado, motor de simulación, evaluación y UI).  

**Razón clave (docencia):** en plataformas como **Moodle**, es común que sea más operativo entregar **un único fichero** en lugar de múltiples assets sueltos (CSS/JS/imagenes), evitando rutas rotas y problemas de empaquetado.

> Recomendación: si un simulador depende de recursos externos (CDNs, fuentes), mantener una variante “offline” con todo embebido cuando el entorno del centro restrinja tráfico externo.

## 2.2. Motor de simulación y evaluación

Cada simulador implementa (de forma explícita o implícita) un patrón similar:

- **Estado** (state): variables del “sistema” y del progreso del alumno.  
- **Eventos**: acciones del usuario (inputs, botones, selección de opciones).  
- **Transiciones**: reglas que deciden el siguiente estado.  
- **Evaluación**: validación de criterios mínimos (correctitud, orden de acciones, consistencia).  
- **Feedback**: mensajes orientados a aprendizaje (no solo “correcto/incorrecto”).

En general, el progreso puede funcionar como:

- **Secuencia de fases** (paso a paso).
- **Niveles o retos** con condiciones de victoria.
- **Misiones** con objetivos medibles.
- **Modo libre** (sandbox) con feedback contextual.

### Persistencia (opcional)
Algunos simuladores guardan progreso localmente mediante **localStorage** para permitir continuidad entre sesiones sin necesidad de backend.

- Ventaja: continuidad en clase/laboratorio.
- Requisito: informar de que es **persistencia local** (navegador del alumno).

## 2.3. UI/UX: temas, paneles y modales

Elementos UI frecuentes:

- **Paneles tipo dashboard** (distribución por rejilla).
- **Consolas** con salida formateada (estilo terminal).
- **Modales** de explicación, glosario, pistas o veredicto.
- **Temas visuales** (ej. modo terminal / modo claro / escala de grises), típicamente con:
  - Variables CSS (`:root`), o
  - `data-theme="..."` para alternar paletas.

**Objetivo pedagógico del diseño visual:** reducir fricción, sostener atención y mantener consistencia entre simuladores para que la interfaz sea “familiar” aunque cambie el contenido.

---

# 3. Cómo ejecutar y desplegar (ES)

## 3.1. Ejecución local

No se requiere instalación.

1. Descarga el archivo `.html`.
2. Ábrelo con doble clic en un navegador moderno (Chrome/Edge/Firefox).
3. Si el simulador utiliza recursos externos (CDNs), asegúrate de tener conexión.

> Consejo docente: para clase, lleva el HTML ya descargado y probado en los equipos del aula o en una máquina patrón.

## 3.2. Despliegue en GitHub Pages

Opción recomendada para acceso público:

1. Crea un repositorio en GitHub.
2. Sube el simulador como `index.html` (o crea una carpeta por simulador).
3. Ve a **Settings → Pages**.
4. Selecciona rama y carpeta (`/root` o `/docs`).
5. GitHub Pages publicará una URL estable para el simulador.

**Ventajas:**
- Acceso por enlace (sin instalaciones).
- Permite compartir enunciados, rúbricas y materiales anexos en el repositorio.

## 3.3. Integración en Moodle

La integración se plantea con un objetivo claro: **que el alumnado ejecute el simulador sin dependencias**.

### Opción A — Subir el HTML como recurso
1. Activa edición en tu curso.
2. Añade un recurso **Archivo**.
3. Sube el `.html`.
4. Configura la visualización:
   - “Abrir” en una nueva ventana o “Incrustar” (según configuración del centro).

### Opción B — Enlace externo (GitHub Pages)
1. Publica el simulador en GitHub Pages.
2. En Moodle, añade un recurso **URL**.
3. Pega el enlace.

**Notas prácticas:**
- Si Moodle restringe scripts en páginas internas, usar “Archivo” o “URL”.
- Si hay bloqueo de CDNs, usar la variante offline (todo embebido en el HTML).

---

# 4. Uso en el aula (ES)

## 4.1. Dinámicas recomendadas

**Propuesta de sesión tipo (50–90 min):**

1. **Introducción conceptual (5–10 min)**  
   Qué se va a simular y qué preguntas debe ser capaz de responder el alumno al final.

2. **Demostración guiada (10–15 min)**  
   El docente resuelve un “micro-reto” mostrando:
   - Cómo leer la interfaz.
   - Qué paneles importan.
   - Cómo interpretar el feedback.

3. **Trabajo por parejas o tríos (15–35 min)**  
   El alumnado resuelve retos similares con autonomía.

4. **Puesta en común (10–20 min)**  
   Comparación de estrategias y errores típicos.

5. **Cierre y transferencia (5–10 min)**  
   Conectar el simulador con práctica real (VM, shell real, logs reales, herramientas reales).

## 4.2. Evaluación y evidencias de aprendizaje

Métodos simples y escalables:

- **Capturas** de estados finales (veredicto, logs, resultados).
- **Mini-informe** (5–10 líneas) con:
  - Hipótesis inicial
  - Acción aplicada
  - Resultado observado
  - Lección aprendida
- **Checklist/rúbrica**:
  - Comprende concepto
  - Interpreta salida
  - Justifica decisiones
  - Corrige errores

---

# 5. Objetivos didácticos (ES)

Estos simuladores entrenan competencias nucleares de Sistemas Operativos:

1. Comprender conceptos base (procesos, memoria, filesystem, shell, arranque, etc.).
2. Razonar sobre **estado** y **transiciones** (“si hago X, el sistema cambia a Y”).
3. Leer salidas técnicas y traducirlas a explicaciones correctas.
4. Practicar diagnóstico (síntoma → hipótesis → prueba → corrección).
5. Consolidar hábitos de ingeniería:
   - precisión,
   - consistencia,
   - trazabilidad de decisiones.

---

# 6. Buenas prácticas de mantenimiento (ES)

Recomendaciones para evolucionar el catálogo de simuladores:

- Mantener un **estilo de UI consistente** (paneles, tipografías, colores, modales).
- Diseñar “retos” con:
  - objetivo explícito,
  - condiciones verificables,
  - feedback inmediato y pedagógico.
- Documentar en el propio HTML:
  - sección de configuración (niveles/datos),
  - sección de motor (evaluación),
  - sección de UI (render).
- Evitar dependencias innecesarias: cuanto menos “ecosistema”, más fácil de desplegar.

---

# 7. Exercise overview (EN)

This repository provides a collection of **interactive Operating Systems simulators** designed for **Software Engineering undergraduates**.

**Key idea:** students learn faster when they can *interact* with a system model, observe its internal state, and receive immediate feedback.

All simulators follow a browser-first approach:

- **No backend**
- **Runs entirely in the browser**
- **Single-file HTML delivery** (ideal for GitHub Pages and LMS environments such as Moodle)

---

# 8. Technical architecture (EN)

## 8.1. Single-file distribution (All-in-one HTML)

Each simulator is delivered as a **self-contained HTML file** that includes:

- Structural UI (HTML)
- Embedded styles (`<style>`) and/or utility CSS via CDN
- Simulation logic (JavaScript)

This packaging strategy is especially helpful for teaching deployments where multiple files (assets, paths, bundling) can introduce friction.

## 8.2. Simulation + evaluation engine

Most simulators implement a shared learning loop:

1. User performs an action (input / command / choice).
2. The simulator updates the internal state.
3. The engine validates success conditions.
4. The UI provides clear feedback (success, failure, hints).

Optional features commonly included:

- Progress systems (phases / levels)
- Scoring or achievements
- Instructor-friendly reset paths
- Local persistence (e.g., `localStorage`) to resume sessions

## 8.3. UI patterns

Typical UI components:

- Dashboard layouts (grid panels)
- Terminal-like output consoles
- Contextual modals (glossary / hints / explanation)
- Theme switchers (terminal/clear/grayscale), usually via CSS variables or `data-theme`

---

# 9. Run & deploy (EN)

## 9.1. Run locally

1. Download the `.html` file.
2. Open it in a modern browser.
3. If the simulator uses external CDNs, ensure Internet access is available.

## 9.2. Deploy on GitHub Pages

1. Upload the simulator as `index.html` in a GitHub repository.
2. Go to **Settings → Pages**.
3. Select branch and folder.
4. GitHub will provide a public URL for easy student access.

## 9.3. Moodle integration

Two practical approaches:

- **Upload HTML as a File resource** (works well when scripts are allowed in file display).
- **Use an external URL** pointing to GitHub Pages.

If your Moodle environment blocks external CDNs, use a fully offline variant (everything embedded into the single HTML file).

---

# 10. How to use in class (EN)

Suggested teaching flow:

1. Short concept introduction (what are we simulating and why?)
2. Instructor-led walkthrough (one micro challenge)
3. Student work (pairs/triads)
4. Group debrief (compare strategies and mistakes)
5. Transfer to real tooling (VM, terminal, logs, etc.)

---

# 11. Learning goals (EN)

Students will learn to:

- Understand core OS concepts through interactive models
- Reason in terms of state, constraints, and transitions
- Interpret technical output and explain it accurately
- Apply a diagnostic workflow (symptom → hypothesis → test → fix)
- Build consistent engineering habits (precision, traceability, verification)

---

# 12. License

This project is released under the **MIT License**.

```text
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files...
