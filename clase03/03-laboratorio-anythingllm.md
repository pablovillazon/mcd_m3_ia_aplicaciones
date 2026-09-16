# Laboratorio Guiado — Construcción de una Aplicación RAG con AnythingLLM

**Programa:** Maestría en Ciencia de Datos, Inteligencia Artificial y Negocios
**Módulo:** IA y Aplicaciones
**Clase 3:** Taller de Aplicaciones de Inteligencia Artificial
**Duración estimada:** 25–30 minutos
**Modalidad:** Laboratorio guiado

---

# 1. Objetivo

Construir una aplicación sencilla basada en **RAG (Retrieval-Augmented Generation)** utilizando AnythingLLM.

Al finalizar el laboratorio tendremos un asistente capaz de:

* utilizar documentos como fuente de conocimiento;
* buscar información relevante dentro de ellos;
* responder preguntas utilizando ese contexto;
* identificar las fuentes utilizadas;
* reconocer situaciones donde la información disponible no es suficiente.

---

# 2. ¿Qué construiremos?

Implementaremos conceptualmente la siguiente arquitectura:

```text
              DOCUMENTOS
                  │
                  ▼
            Procesamiento
                  │
                  ▼
              Chunks
                  │
                  ▼
          Embedding Model
                  │
                  ▼
           Vector Database
                  │
                  │
Usuario ──► Pregunta
                  │
                  ▼
              Retriever
                  │
                  ▼
        Fragmentos relevantes
                  │
                  ▼
                 LLM
                  │
                  ▼
        Respuesta + fuentes
```

AnythingLLM nos permitirá implementar esta arquitectura sin necesidad de programarla desde cero.

---

# 3. Requisitos

Para realizar el laboratorio necesitaremos:

* AnythingLLM;
* acceso a un modelo de lenguaje;
* 3 a 5 documentos de prueba;
* aproximadamente 25 minutos.

Los documentos pueden ser:

* PDF;
* TXT;
* DOCX;
* documentación técnica;
* procedimientos;
* políticas;
* reglamentos;
* manuales;
* documentación académica.

> Para el laboratorio evite utilizar documentos confidenciales, datos personales sensibles o información que no esté autorizado a procesar.

---

# 4. Paso 1 — Abrir AnythingLLM

Inicie AnythingLLM.

Dependiendo de la instalación utilizada, podrá trabajar mediante:

* aplicación Desktop;
* instalación local;
* servidor;
* contenedor.

Para este laboratorio utilizaremos la interfaz gráfica.

---

# 5. Paso 2 — Verificar el modelo de lenguaje

Antes de crear nuestra aplicación debemos identificar qué **LLM** utilizará.

Revise la configuración correspondiente al proveedor del modelo.

Dependiendo del entorno podrían existir diferentes alternativas.

Por ejemplo:

```text
Cloud

OpenAI
Anthropic
Google
otros proveedores
```

o:

```text
Local

Ollama
LM Studio
otros modelos locales
```

---

# 6. Primera decisión de IA

Antes de continuar registre:

```text
LLM seleccionado:
________________________________________

Proveedor:
________________________________________

Local / Cloud:
________________________________________

¿Por qué utilizamos esta alternativa?
________________________________________
________________________________________
```

No es necesario realizar todavía una comparación exhaustiva.

El objetivo es comenzar a comprender que:

> **Seleccionar un modelo también es una decisión de arquitectura.**

---

# 7. Paso 3 — Crear un Workspace

Cree un nuevo Workspace.

Nombre sugerido:

```text
Demo-RAG-Clase3
```

El Workspace representará el espacio donde tendremos:

* documentos;
* contexto;
* instrucciones;
* conversaciones.

Podemos imaginarlo como el espacio de conocimiento de nuestra aplicación.

---

# 8. Paso 4 — Incorporar documentos

Agregue entre **3 y 5 documentos**.

Para esta primera demostración es conveniente utilizar documentos relativamente pequeños.

Ejemplos:

```text
manual.pdf

politica-interna.pdf

procedimiento.txt

preguntas-frecuentes.docx
```

---

# 9. ¿Qué ocurre cuando incorporamos documentos?

Conceptualmente ocurre un proceso similar a:

```text
Documento
    │
    ▼
Extracción de texto
    │
    ▼
Fragmentación
    │
    ▼
Chunks
    │
    ▼
Embeddings
    │
    ▼
Vector Database
```

El documento completo normalmente **no se envía al LLM en cada pregunta**.

Primero se divide en fragmentos que posteriormente pueden recuperarse según su relevancia.

---

# 10. ¿Qué es un Chunk?

Supongamos que tenemos un manual de 100 páginas.

En lugar de utilizar todo el manual:

```text
Manual completo
████████████████████████████████
```

podemos dividirlo:

```text
Chunk 1
████

Chunk 2
████

Chunk 3
████

Chunk 4
████

...
```

Cuando el usuario realiza una pregunta, el sistema intentará recuperar solamente los fragmentos más relevantes.

---

# 11. Paso 5 — Incorporar los documentos al Workspace

Una vez cargados los archivos:

1. seleccione los documentos;
2. agréguelos al Workspace;
3. espere hasta que termine su procesamiento.

Verifique que los documentos aparezcan asociados al espacio de trabajo.

---

# 12. Paso 6 — Identificar el modelo de embeddings

Revise la configuración relacionada con **Embeddings**.

Registre:

```text
Embedding Model:
________________________________________

Proveedor:
________________________________________
```

Ahora tenemos dos modelos que pueden cumplir funciones diferentes:

```text
Embedding Model
      │
      ▼
Representar y recuperar información


LLM
      │
      ▼
Interpretar contexto y generar respuesta
```

---

# 13. Pregunta de análisis

Discuta brevemente:

> ¿Por qué necesitamos un modelo de embeddings si ya tenemos un LLM?

La respuesta conceptual es:

```text
Embeddings
     ↓
¿QUÉ información puede ser relevante?


LLM
     ↓
¿CÓMO responder utilizando esa información?
```

Esta separación será importante al justificar posteriormente nuestro MVP.

---

# 14. Paso 7 — Configurar las instrucciones del asistente

Configure las instrucciones del Workspace.

Puede utilizar inicialmente:

```text
Eres un asistente especializado en los documentos
proporcionados en este espacio de trabajo.

Responde utilizando prioritariamente la información
contenida en los documentos.

Cuando respondas:

1. Identifica la información relevante.
2. Responde de manera clara y concreta.
3. Utiliza los documentos disponibles como evidencia.
4. Indica las fuentes utilizadas cuando estén disponibles.
5. No inventes información que no aparezca en las fuentes.
6. Si no existe información suficiente, indícalo explícitamente.
7. Diferencia hechos de interpretaciones.
8. Cuando una decisión requiera criterio profesional,
   indica que necesita revisión humana.
```

---

# 15. Paso 8 — Primera pregunta

Realice una pregunta cuya respuesta aparezca **explícitamente en uno de los documentos**.

Ejemplo:

```text
¿Cuál es el procedimiento establecido para ______?
```

o:

```text
¿Según el documento, cuál es el plazo para ______?
```

Observe la respuesta.

---

# 16. No evalúe solamente el texto

Analice:

```text
¿La respuesta es correcta?

¿Encontró el documento correcto?

¿Utilizó el fragmento correcto?

¿La respuesta coincide con la fuente?

¿Indicó la fuente?

¿Agregó información que no estaba presente?
```

Una respuesta bien escrita no necesariamente es una respuesta correcta.

---

# 17. Paso 9 — Revisar las fuentes

Observe las fuentes o referencias utilizadas por AnythingLLM.

Conceptualmente ocurrió:

```text
Pregunta
    │
    ▼
Embedding de la pregunta
    │
    ▼
Búsqueda por similitud
    │
    ▼
Chunks relevantes
    │
    ▼
Contexto
    │
    ▼
LLM
    │
    ▼
Respuesta
```

---

# 18. Paso 10 — Pregunta que combina información

Realice ahora una pregunta cuya respuesta requiera información presente en **dos documentos diferentes**.

Por ejemplo:

```text
Considerando el procedimiento A y la política B,
¿qué debería hacerse cuando ocurre __________?
```

Observe:

* qué documentos recupera;
* qué fragmentos utiliza;
* si combina correctamente la información.

---

# 19. Paso 11 — Pregunta ambigua

Realice una pregunta deliberadamente incompleta.

Por ejemplo:

```text
¿Puedo aprobarlo?
```

o:

```text
¿Qué debemos hacer con este caso?
```

Observe qué hace el asistente.

Pregúntese:

> ¿Solicita información adicional o intenta responder de todas maneras?

---

# 20. Paso 12 — La prueba más importante

Realice una pregunta cuya respuesta **NO exista en los documentos**.

Por ejemplo:

```text
¿Cuál fue la facturación total de la organización
durante el año 2025?
```

Utilice una pregunta que usted sepa que no puede responderse utilizando los documentos cargados.

---

# 21. Observe el comportamiento

Podrían ocurrir diferentes resultados:

```text
Caso A

"No existe información suficiente..."
        ✓
```

```text
Caso B

El modelo responde utilizando
conocimiento general.
        ?
```

```text
Caso C

El modelo inventa una respuesta.
        ✗
```

Esta prueba nos permite observar un riesgo fundamental de los LLM:

## Alucinación

Una respuesta puede ser lingüísticamente convincente y, aun así, no estar respaldada por evidencia.

---

# 22. RAG no significa automáticamente "respuesta correcta"

Un sistema RAG puede fallar en diferentes lugares.

```text
Pregunta
   │
   ▼
Retrieval ──────► ¿Recuperó información correcta?
   │
   ▼
Contexto ───────► ¿Recuperó suficiente información?
   │
   ▼
LLM ────────────► ¿Interpretó correctamente?
   │
   ▼
Respuesta ──────► ¿Representó correctamente la evidencia?
```

Por tanto:

> **Cuando una aplicación RAG falla, el problema no necesariamente está en el LLM.**

---

# 23. Paso 13 — Mejorar las instrucciones

Modifique las instrucciones del asistente.

Por ejemplo, refuerce:

```text
Responde únicamente cuando exista evidencia suficiente
en los documentos proporcionados.

Si no encuentras evidencia suficiente, responde:

"NO EXISTE INFORMACIÓN SUFICIENTE EN LAS FUENTES
DISPONIBLES."

No completes la respuesta utilizando suposiciones.
```

Repita la pregunta anterior.

---

# 24. Compare

Registre:

| Elemento                | Antes | Después |
| ----------------------- | ----- | ------- |
| Respuesta correcta      |       |         |
| Utilizó fuentes         |       |         |
| Inventó información     |       |         |
| Reconoció incertidumbre |       |         |
| Resultado aceptable     |       |         |

---

# 25. Paso 14 — Analizar una respuesta incorrecta

Si encuentra una respuesta incorrecta, no cambie inmediatamente de modelo.

Primero investigue:

```text
¿El documento contiene la respuesta?
            │
            ▼
¿El sistema recuperó el documento?
            │
            ▼
¿Recuperó el fragmento correcto?
            │
            ▼
¿El contexto era suficiente?
            │
            ▼
¿Las instrucciones eran claras?
            │
            ▼
¿El LLM interpretó incorrectamente?
```

Esta secuencia constituye una forma sencilla de **diagnóstico de aplicaciones RAG**.

---

# 26. Resultado del laboratorio

Al finalizar debería disponer de:

```text
Workspace
   +
Documentos
   +
Embedding Model
   +
Vector Database
   +
Retriever
   +
LLM
   +
Instrucciones
   +
Pruebas
```

Es decir:

## Una aplicación RAG mínima funcional

---

# 27. Registro del laboratorio

Complete:

### Modelo

```text
LLM utilizado:
________________________________________

Local / Cloud:
________________________________________
```

### Embeddings

```text
Embedding Model:
________________________________________
```

### Conocimiento

```text
Cantidad de documentos:
________________________________________

Tipo de documentos:
________________________________________
```

### Pruebas

```text
Pregunta con respuesta conocida:
________________________________________

Resultado:
________________________________________
```

```text
Pregunta que combina documentos:
________________________________________

Resultado:
________________________________________
```

```text
Pregunta sin respuesta:
________________________________________

Resultado:
________________________________________
```

---

# 28. Reflexión

Responda brevemente:

### 1.

¿El LLM conoce realmente los documentos cargados o recibe fragmentos relevantes durante cada consulta?

---

### 2.

¿Qué componente permite localizar esos fragmentos?

---

### 3.

¿El modelo de embeddings y el LLM cumplen la misma función?

---

### 4.

¿Qué ocurrió cuando preguntó algo que no estaba en los documentos?

---

### 5.

¿Qué riesgo tendría utilizar esta aplicación automáticamente dentro de un proceso real?

---

# 29. Del laboratorio al Taller MVP

En este laboratorio todos construimos esencialmente la misma aplicación.

En el siguiente ejercicio cambiaremos la pregunta.

Ya no será:

> **¿Cómo construimos un RAG?**

Será:

> **¿Qué problema de mi organización, profesión, negocio o proyecto podría resolver utilizando esta arquitectura?**

El siguiente paso será diseñar y construir su propio:

# MVP de Aplicación de Inteligencia Artificial

donde deberá justificar:

```text
PROBLEMA
   ↓
¿Por qué IA?
   ↓
¿Por qué RAG?
   ↓
¿Qué conocimiento?
   ↓
¿Qué Embeddings?
   ↓
¿Qué LLM?
   ↓
¿Por qué ese modelo?
   ↓
¿Cómo evaluarlo?
   ↓
¿Qué riesgos existen?
   ↓
¿Qué debe controlar una persona?
```

> **AnythingLLM es la herramienta utilizada para el laboratorio. El objetivo académico es comprender y justificar la arquitectura de IA que estamos construyendo.**
