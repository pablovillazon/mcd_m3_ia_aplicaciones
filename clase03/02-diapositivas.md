# Taller de Aplicaciones de Inteligencia Artificial

## De documentos y conocimiento a un MVP con IA

**Maestría en Ciencia de Datos, Inteligencia Artificial y Negocios**
**Módulo: IA y Aplicaciones**

---

# Pregunta de la clase

> ## ¿Cómo podemos transformar el conocimiento de una organización en una aplicación de IA que genere valor?

Hoy no construiremos solamente un chatbot.

Construiremos un **MVP de una aplicación de IA**.

---

# De la Clase 2 a la Clase 3

En la clase anterior trabajamos con:

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

Hoy implementaremos estos conceptos.

---

# El conocimiento de una organización

¿Dónde se encuentra?

* Contratos
* Procedimientos
* Políticas
* Reglamentos
* Informes
* Manuales
* Libros
* Tickets
* Documentación técnica
* Preguntas frecuentes
* Bases documentales

Gran parte de este conocimiento es **no estructurado**.

---

# Un problema frecuente

Imagine una organización con:

```text
500 contratos

2.000 procedimientos

10.000 informes

50.000 tickets

100.000 documentos
```

Un usuario pregunta:

> ¿Cuál es el procedimiento aplicable a esta situación?

¿Cómo encontramos la información correcta?

---

# Primera alternativa

Podríamos preguntar directamente a un LLM:

```text
Usuario
   ↓
Pregunta
   ↓
LLM
   ↓
Respuesta
```

Pero aparece un problema.

---

# ¿De dónde obtiene la respuesta?

El modelo puede utilizar:

* conocimiento aprendido durante entrenamiento;
* información incluida en el prompt;
* patrones estadísticos;
* contexto de la conversación.

Pero puede **no conocer nuestros documentos internos**.

---

# El problema

Necesitamos conectar:

```text
       LLM

        +

Conocimiento propio
de la organización
```

Aquí aparece:

# RAG

**Retrieval-Augmented Generation**

---

# ¿Qué es RAG?

RAG combina dos procesos.

## Retrieval

Buscar información relevante.

## Generation

Generar una respuesta utilizando esa información.

```text
Buscar
  +
Generar
```

---

# Arquitectura básica

```text
Pregunta
   ↓
Búsqueda
   ↓
Documentos relevantes
   ↓
Contexto
   ↓
LLM
   ↓
Respuesta
```

El modelo recibe **información relevante antes de responder**.

---

# Arquitectura completa

```text
PDF   DOCX   TXT   HTML
 │      │     │      │
 └──────┴─────┴──────┘
            ↓
      Procesamiento
            ↓
       Fragmentación
            ↓
        Embeddings
            ↓
      Base vectorial
            ↓
        Retriever
            ↑
         Pregunta
            ↓
          Contexto
            ↓
           LLM
            ↓
         Respuesta
```

---

# Paso 1 — Documentos

Podemos utilizar diferentes fuentes:

```text
PDF
DOCX
TXT
Markdown
Web
Manuales
Políticas
Contratos
Normativa
```

Pero un documento completo puede ser demasiado grande.

Necesitamos dividirlo.

---

# Paso 2 — Chunks

Un **chunk** es un fragmento de información.

Ejemplo:

```text
Documento de 100 páginas
          ↓
      Fragmentación
          ↓
┌────────┬────────┬────────┐
│Chunk 1 │Chunk 2 │Chunk 3 │ ...
└────────┴────────┴────────┘
```

El sistema posteriormente buscará los fragmentos más relevantes.

---

# ¿Por qué importa el tamaño del chunk?

### Chunk demasiado pequeño

Puede perder contexto.

### Chunk demasiado grande

Puede incorporar información irrelevante.

Por tanto:

> **La fragmentación también es una decisión de diseño.**

---

# Paso 3 — Embeddings

¿Cómo puede una computadora comparar el significado de dos textos?

Mediante una representación numérica.

```text
"Política de vacaciones"

        ↓

Embedding Model

        ↓

[0.12, -0.41, 0.87, ...]
```

Esto se conoce como **embedding**.

---

# Embeddings

Textos con significados relacionados pueden obtener representaciones cercanas.

```text
"solicitar vacaciones"

        ≈

"pedir días libres"
```

Aunque no utilicen exactamente las mismas palabras.

Esto permite realizar:

# Búsqueda semántica

---

# Algo importante

En una aplicación RAG podemos utilizar **más de un modelo de IA**.

```text
Embedding Model
      ↓
Representar / buscar información


LLM
      ↓
Comprender / generar respuesta
```

Por tanto:

> **Seleccionar el LLM no es la única decisión de IA.**

---

# Paso 4 — Base vectorial

Necesitamos almacenar los embeddings.

```text
Chunk 1 → Vector 1

Chunk 2 → Vector 2

Chunk 3 → Vector 3

Chunk 4 → Vector 4
```

Una **base vectorial** permite almacenar y buscar estas representaciones.

---

# Paso 5 — Retrieval

El usuario pregunta:

> ¿Cuál es el procedimiento para solicitar vacaciones?

La pregunta también se transforma en un embedding.

```text
Pregunta
   ↓
Embedding
   ↓
Comparación
   ↓
Chunks similares
```

---

# Recuperación

El sistema podría recuperar:

```text
Chunk 27
Política de vacaciones

Chunk 83
Procedimiento de RRHH

Chunk 105
Reglamento interno
```

Estos fragmentos se convierten en el **contexto** para el LLM.

---

# Paso 6 — Generación

Ahora el modelo recibe:

```text
INSTRUCCIONES

+

PREGUNTA

+

DOCUMENTOS RECUPERADOS
```

y genera la respuesta.

---

# Entonces...

RAG no significa:

> "El modelo aprendió nuestros documentos."

Significa:

> **"El sistema recuperó información relevante y la proporcionó al modelo como contexto."**

Esta diferencia es fundamental.

---

# RAG vs entrenamiento

## RAG

Proporcionamos conocimiento durante la consulta.

## Fine-tuning

Modificamos el comportamiento del modelo mediante entrenamiento adicional.

No son lo mismo.

---

# ¿Necesitamos Fine-tuning?

Para muchas aplicaciones empresariales basadas en documentos:

```text
Conocimiento especializado
        +
Documentos cambiantes
        +
Necesidad de fuentes
```

RAG suele ser una alternativa natural a evaluar antes de modificar un modelo.

---

# Pero...

# RAG no garantiza respuestas correctas

Pueden ocurrir errores en diferentes etapas.

---

# ¿Dónde puede fallar?

```text
Documentos
    ↓
¿Documento correcto?

Fragmentación
    ↓
¿Chunk adecuado?

Embeddings
    ↓
¿Representación adecuada?

Retrieval
    ↓
¿Recuperó la información correcta?

LLM
    ↓
¿Interpretó correctamente?

Respuesta
    ↓
¿Está sustentada?
```

---

# Un sistema RAG tiene dos grandes problemas

## Retrieval

¿Encontramos la información correcta?

## Generation

¿Generamos una respuesta correcta utilizando esa información?

Debemos evaluar ambos.

---

# Ahora debemos elegir un modelo

Pregunta frecuente:

> ## ¿Cuál es el mejor LLM?

La pregunta está incompleta.

La pregunta correcta es:

> ## ¿Cuál es el modelo adecuado para nuestro problema?

---

# Criterios para seleccionar un LLM

Consideremos:

* Calidad
* Privacidad
* Costo
* Latencia
* Idioma
* Ventana de contexto
* Hardware
* Disponibilidad
* Integración
* Tipo de tarea

No existe una única respuesta para todos los proyectos.

---

# Local vs Cloud

## Modelo Cloud

```text
Aplicación
    ↓
Internet
    ↓
Proveedor
    ↓
LLM
```

### Ventajas posibles

* modelos potentes;
* menor infraestructura local;
* facilidad de uso.

### Aspectos a evaluar

* privacidad;
* costo;
* dependencia del proveedor;
* conectividad.

---

# Modelo Local

```text
Aplicación
    ↓
Infraestructura propia
    ↓
LLM
```

### Ventajas posibles

* mayor control;
* privacidad;
* funcionamiento local.

### Aspectos a evaluar

* hardware;
* mantenimiento;
* velocidad;
* capacidad del modelo.

---

# Una decisión, no una preferencia

No deberíamos decir:

> "Elegimos un modelo local porque es mejor."

Deberíamos justificar:

> "Elegimos ejecución local porque los documentos contienen información que no debe enviarse a servicios externos y disponemos de infraestructura suficiente."

La diferencia es:

# JUSTIFICACIÓN

---

# También debemos justificar RAG

No basta decir:

> "Utilizamos RAG porque es una tecnología moderna."

Una mejor justificación sería:

> "La aplicación necesita consultar documentación interna que cambia periódicamente y las respuestas deben estar vinculadas a fuentes verificables."

---

# Antes de elegir IA

Primero debemos responder:

```text
¿Qué problema tenemos?
        ↓
¿Qué información necesitamos?
        ↓
¿Qué tarea queremos mejorar?
        ↓
¿Qué riesgo existe?
        ↓
¿Qué tecnología necesitamos?
```

Y recién entonces:

```text
¿Qué modelo utilizamos?
```

---

# Del chatbot a la aplicación

Un chatbot podría ser:

```text
Pregunta → LLM → Respuesta
```

Nuestra aplicación será:

```text
                 Documentos
                     ↓
                 Embeddings
                     ↓
Pregunta → Retrieval → Contexto
                         ↓
                        LLM
                         ↓
                     Respuesta
                         ↓
                    Validación
                         ↓
                      Proceso
```

---

# Herramienta del taller

# AnythingLLM

Utilizaremos una plataforma que nos permitirá experimentar con:

* documentos;
* workspaces;
* modelos de lenguaje;
* embeddings;
* RAG;
* instrucciones;
* recuperación;
* diferentes proveedores.

La herramienta es un medio.

> **El objetivo es comprender la arquitectura.**

---

# Nuestro MVP

Cada participante podrá trabajar sobre su propia área.

### Finanzas

Asistente para políticas, procedimientos o documentación financiera.

### Legal

Consulta de contratos, normativa o procedimientos.

### Tecnología

Manuales, incidentes, arquitectura o documentación técnica.

---

# Otros ejemplos

### Educación

Reglamentos, contenidos y material académico.

### Gobierno

Normativa y procedimientos.

### Empresa

Procesos internos y conocimiento organizacional.

### Proyecto personal

Libros, investigaciones o documentación especializada.

---

# El MVP debe comenzar con un problema

Complete:

```text
Actualmente ____________________________

La solución será utilizada por _________

La información disponible es ___________

Queremos que la IA pueda _______________

Esto permitiría ________________________

Si la IA se equivoca podría ____________
```

---

# No cargar documentos por cargar documentos

Pregunte:

> ¿Qué información necesita realmente la aplicación?

La calidad de una base RAG depende también de:

* relevancia;
* calidad;
* actualización;
* estructura;
* duplicados;
* permisos.

---

# Seguridad y privacidad

Antes de incorporar un documento:

### Pregunte

* ¿Estoy autorizado a utilizarlo?
* ¿Contiene información confidencial?
* ¿Contiene datos personales?
* ¿Dónde se procesará?
* ¿Qué proveedor recibirá la información?
* ¿Quién podrá consultar el sistema?

---

# Definir comportamiento

Nuestro asistente debería saber qué hacer cuando encuentra información.

Pero también:

> ## ¿Qué debe hacer cuando NO encuentra información?

Una respuesta válida puede ser:

> "No encuentro evidencia suficiente en los documentos disponibles."

Eso puede ser mejor que una respuesta inventada.

---

# Grounding

Queremos que las respuestas estén **ancladas en evidencia**.

```text
Respuesta
   ↓
Evidencia
   ↓
Documento
```

Deberíamos poder preguntar:

> ¿De dónde salió esta afirmación?

---

# Trazabilidad

Una solución profesional debería facilitar:

* fuente utilizada;
* documento;
* fragmento relevante;
* evidencia;
* revisión.

Esto aumenta la capacidad de verificar la respuesta.

---

# Human-in-the-Loop

No todas las acciones deberían automatizarse.

```text
Bajo riesgo
    ↓
Automatización


Riesgo medio
    ↓
IA + validación


Alto riesgo
    ↓
Decisión profesional
```

---

# El MVP no termina cuando responde

Debemos probarlo.

# ¿Cómo sabemos que funciona?

---

# Cinco pruebas mínimas

### T1 — Información explícita

La respuesta está directamente en un documento.

### T2 — Combinación

Necesita información de varios documentos.

### T3 — Ambigüedad

La pregunta admite diferentes interpretaciones.

### T4 — Información inexistente

La respuesta no está disponible.

### T5 — Riesgo

La respuesta podría influir en una decisión importante.

---

# Ejemplo de evaluación

| Test | Respuesta correcta | Fuente correcta | Inventó |
| ---- | ------------------ | --------------- | ------- |
| T1   | Sí                 | Sí              | No      |
| T2   | Sí                 | Sí              | No      |
| T3   | Parcial            | Sí              | No      |
| T4   | —                  | —               | **No**  |
| T5   | Parcial            | Sí              | No      |

Una respuesta fluida no significa necesariamente una respuesta correcta.

---

# Si falla...

No cambiemos inmediatamente el LLM.

Preguntemos primero:

```text
¿Problema del documento?

¿Problema del chunk?

¿Problema del retrieval?

¿Problema del prompt?

¿Problema del modelo?

¿Problema de la pregunta?
```

Diagnosticar antes de modificar.

---

# Diseño de nuestro MVP

Cada grupo deberá justificar:

```text
PROBLEMA
   ↓
¿Por qué IA?
   ↓
¿Por qué RAG?
   ↓
¿Qué documentos?
   ↓
¿Qué embeddings?
   ↓
¿Qué LLM?
   ↓
¿Por qué ese modelo?
   ↓
¿Cómo evaluarlo?
   ↓
¿Qué riesgos?
   ↓
¿Qué controla una persona?
```

---

# Criterio de éxito

No buscamos:

> "Mi chatbot funciona."

Buscamos poder afirmar:

> **"Construimos una solución para este problema, utilizamos estos componentes por estas razones y tenemos evidencia inicial de cómo funciona."**

---

# De MVP a proceso empresarial

Hoy construiremos:

```text
Documentos
    ↓
RAG
    ↓
LLM
    ↓
Respuesta
```

Pero una solución real puede evolucionar hacia:

```text
             ┌── Documentos
             │
             ├── Base de datos
Usuario → IA ├── CRM
             ├── ERP
             ├── Email
             └── APIs
                   ↓
                 Acción
```

---

# IA + Automatización

El siguiente nivel consiste en pasar de:

> **"La IA responde."**

a:

> **"La IA participa en un proceso."**

Ejemplo:

```text
Documento recibido
      ↓
Clasificación
      ↓
Extracción
      ↓
Consulta RAG
      ↓
Recomendación
      ↓
Validación humana
      ↓
Acción
```

---

# Pero más autonomía implica...

```text
Más autonomía
      ↓
Mayor impacto potencial
      ↓
Mayor necesidad de controles
```

Por eso debemos diseñar:

* límites;
* permisos;
* validación;
* trazabilidad;
* evaluación;
* intervención humana.

---

# El objetivo del taller

Al finalizar tendremos:

## Un MVP funcional

*

## Una justificación de arquitectura

*

## Evidencia mediante pruebas

*

## Identificación de riesgos

---

# Producto esperado

Cada grupo deberá poder explicar:

### 1. Problema

¿Qué resolvemos?

### 2. Conocimiento

¿Qué documentos utilizamos?

### 3. Arquitectura

¿Cómo funciona?

### 4. IA

¿Qué modelos/componentes seleccionamos?

### 5. Justificación

¿Por qué?

### 6. Evaluación

¿Cómo sabemos que funciona?

### 7. Control

¿Qué debe seguir haciendo una persona?

---

# La pregunta más importante

No es:

> ## ¿Qué modelo utilizaste?

Es:

> ## ¿Por qué esta arquitectura de IA es adecuada para este problema?

---

# Idea central

```text
        PROBLEMA
           ↓
       CONOCIMIENTO
           ↓
       ARQUITECTURA
           ↓
           IA
           ↓
       EVALUACIÓN
           ↓
        CONTROL
           ↓
         VALOR
```

---

# Ahora construiremos

## Del concepto al MVP

**Problema → Documentos → RAG → LLM → Evaluación → Valor**

### Taller de Aplicaciones de IA
