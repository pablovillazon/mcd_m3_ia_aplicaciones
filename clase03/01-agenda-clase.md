# Clase 3 — Taller de Aplicaciones de Inteligencia Artificial

**Programa:** Maestría en Ciencia de Datos, Inteligencia Artificial y Negocios

**Módulo:** IA y Aplicaciones

**Duración:** 3 horas

**Modalidad:** Taller teórico-práctico

---

## Propósito de la clase

Diseñar e implementar un **MVP de una aplicación de Inteligencia Artificial** que utilice documentos y conocimiento propio de una organización, negocio, área profesional o proyecto personal.

La solución deberá responder a un **problema concreto** y justificar las principales decisiones relacionadas con el uso de IA:

* por qué utilizar IA;
* por qué utilizar RAG;
* qué modelo utilizar;
* qué fuentes de conocimiento incorporar;
* qué componentes necesita la solución;
* qué riesgos existen;
* qué decisiones requieren intervención humana.

> **El objetivo no es solamente construir una aplicación que responda preguntas, sino diseñar una solución de IA justificable, verificable y útil.**

---

# Pregunta guía

> **¿Cómo podemos transformar el conocimiento de una organización en una aplicación de IA que genere valor?**

---

# Resultado esperado

Al finalizar la clase cada participante o grupo deberá disponer de un:

## MVP de aplicación de IA

La solución deberá:

1. resolver un problema claramente definido;
2. utilizar documentos o conocimiento especializado;
3. incorporar un modelo de lenguaje;
4. utilizar recuperación de información (RAG);
5. responder utilizando el conocimiento proporcionado;
6. permitir verificar las fuentes utilizadas;
7. haber sido evaluada mediante preguntas de prueba;
8. identificar riesgos y mecanismos de control.

---

# Agenda

## 19:00 – 19:10 | Apertura — Del RAG conceptual al MVP

**Duración:** 10 minutos

### Recordatorio de la clase anterior

En la Clase 2 trabajamos con:

```text
Texto
  ↓
Extracción
  ↓
Clasificación
  ↓
Análisis
  ↓
Asistente profesional
  ↓
RAG
```

Ahora construiremos una aplicación que implemente estos conceptos.

### Pregunta inicial

Piense en su propia organización, profesión o proyecto:

> **¿Qué conocimiento utilizan diariamente las personas para realizar su trabajo?**

Ejemplos:

* contratos;
* procedimientos;
* normativa;
* políticas;
* informes;
* manuales;
* libros;
* documentación técnica;
* preguntas frecuentes;
* documentación financiera.

---

## 19:10 – 19:30 | Bloque 1 — Arquitectura de una aplicación RAG

**Duración:** 20 minutos

### Conceptos

Revisión práctica de los componentes:

```text
Documentos
    ↓
Procesamiento
    ↓
Fragmentación
    ↓
Embeddings
    ↓
Base vectorial
    ↓
Recuperación
    ↓
Contexto
    ↓
LLM
    ↓
Respuesta
```

### Analizaremos

* ¿Qué es un chunk?
* ¿Qué es un embedding?
* ¿Para qué sirve una base vectorial?
* ¿Qué hace el Retriever?
* ¿Qué hace el LLM?
* ¿Qué información llega realmente al modelo?

### Idea central

> **El LLM genera la respuesta; el sistema RAG proporciona el conocimiento necesario para generarla.**

---

## 19:30 – 19:45 | Bloque 2 — Selección y justificación de IA

**Duración:** 15 minutos

Antes de construir el MVP responderemos:

### ¿Por qué IA?

¿El problema realmente necesita IA?

### ¿Por qué RAG?

¿La aplicación necesita conocimiento especializado o actualizado?

### ¿Qué LLM?

Consideraremos:

* calidad;
* privacidad;
* costo;
* latencia;
* idioma;
* ventana de contexto;
* disponibilidad;
* ejecución local o cloud.

### ¿Qué modelo de embeddings?

Comprenderemos que una aplicación RAG puede utilizar **más de un modelo de IA**.

```text
Embedding Model
      ↓
Representación / búsqueda

LLM
      ↓
Generación / razonamiento
```

---

## 19:45 – 20:10 | Laboratorio guiado — Primer RAG con AnythingLLM

**Duración:** 25 minutos

Construiremos conjuntamente una aplicación sencilla.

### Secuencia

1. Abrir/configurar AnythingLLM.
2. Seleccionar proveedor y modelo.
3. Crear un Workspace.
4. Incorporar documentos.
5. Procesar los documentos.
6. Configurar las instrucciones del asistente.
7. Realizar preguntas.
8. Revisar las fuentes recuperadas.
9. Probar una pregunta cuya respuesta exista.
10. Probar una pregunta cuya respuesta **no exista**.

### Pregunta de análisis

> **¿Qué hace el sistema cuando no encuentra evidencia suficiente?**

---

## 20:10 – 20:25 | Diseño del MVP

**Duración:** 15 minutos

Cada participante o grupo definirá su solución.

### Paso 1 — Problema

```text
Actualmente _______________________________
```

### Paso 2 — Usuario

```text
La solución será utilizada por ____________
```

### Paso 3 — Conocimiento

```text
La información disponible consiste en _____
```

### Paso 4 — Capacidad de IA

```text
Queremos que la aplicación pueda __________
```

### Paso 5 — Valor

```text
La solución permitiría ____________________
```

### Paso 6 — Riesgo

```text
Si la IA se equivoca podría _______________
```

---

## 20:25 – 20:35 | Pausa

**Duración:** 10 minutos

Antes de continuar cada grupo debería tener definido:

* problema;
* usuario;
* documentos;
* tarea;
* valor esperado.

---

# 20:35 – 21:20 | Taller principal — Construcción del MVP

**Duración:** 45 minutos

Cada grupo construirá su aplicación.

### Etapa 1 — Crear el espacio de conocimiento

Incorporar los documentos seleccionados.

### Etapa 2 — Configurar IA

Seleccionar:

* LLM;
* modelo/proveedor;
* configuración local o cloud;
* embeddings disponibles.

### Etapa 3 — Definir comportamiento

Configurar instrucciones para que el asistente:

* utilice los documentos;
* responda con evidencia;
* indique las fuentes;
* reconozca información faltante;
* evite inventar información;
* identifique cuándo se necesita revisión humana.

### Etapa 4 — Primera prueba

Realizar consultas reales relacionadas con el problema seleccionado.

---

# 21:20 – 21:40 | Evaluación del MVP

**Duración:** 20 minutos

Cada solución deberá superar al menos **cinco pruebas**.

| Prueba | Objetivo                                  |
| ------ | ----------------------------------------- |
| T1     | Encontrar información explícita           |
| T2     | Combinar información de varios documentos |
| T3     | Responder una pregunta ambigua            |
| T4     | Manejar información inexistente           |
| T5     | Manejar una consulta de mayor riesgo      |

Para cada prueba registrar:

```text
Pregunta
   ↓
Respuesta
   ↓
Fuente utilizada
   ↓
¿Correcta?
   ↓
¿Completa?
   ↓
¿Inventó información?
```

---

# 21:40 – 21:50 | Mejora de la solución

**Duración:** 10 minutos

A partir de las pruebas anteriores:

1. identificar el principal problema;
2. determinar su posible causa;
3. modificar la configuración;
4. repetir la prueba.

Podrían modificarse:

* documentos;
* instrucciones;
* prompt;
* configuración RAG;
* modelo;
* estrategia de recuperación.

### Principio

> **Una aplicación de IA debe evaluarse y mejorarse utilizando evidencia, no solamente observando que genera respuestas convincentes.**

---

# 21:50 – 21:57 | Presentación rápida de MVP

**Duración:** 7 minutos

Algunos grupos presentarán brevemente:

### Problema

¿Qué estamos resolviendo?

### Solución

¿Qué construimos?

### IA

¿Qué modelo/componentes utilizamos y por qué?

### Evidencia

¿Qué ocurrió durante las pruebas?

### Valor

¿Qué mejoraría dentro del proceso actual?

---

# 21:57 – 22:00 | Cierre

## De chatbot a aplicación de IA

Durante el taller hemos recorrido:

```text
Problema
   ↓
Conocimiento
   ↓
Documentos
   ↓
Embeddings
   ↓
RAG
   ↓
LLM
   ↓
Evaluación
   ↓
Control
   ↓
Proceso
   ↓
Valor
```

---

# Producto de la clase

Cada participante o grupo deberá conservar:

* MVP funcional;
* documentos utilizados;
* configuración principal;
* instrucciones del asistente;
* cinco preguntas de evaluación;
* resultados obtenidos;
* decisiones de IA justificadas;
* riesgos identificados;
* propuesta de integración.

---

# Criterio fundamental

La actividad **no consiste en demostrar que un chatbot puede responder preguntas**.

La solución deberá poder responder:

> **¿Qué problema resolvemos?**

> **¿Por qué necesitamos IA?**

> **¿Por qué utilizamos RAG?**

> **¿Por qué seleccionamos este modelo?**

> **¿Cómo sabemos que funciona?**

> **¿Qué sucede cuando se equivoca?**

> **¿Dónde debe intervenir una persona?**

Una aplicación de IA genera valor cuando la tecnología seleccionada es adecuada para el **problema, conocimiento, riesgo y proceso** en el que será utilizada.
