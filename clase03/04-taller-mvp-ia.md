# Taller Principal — Construcción de un MVP de Aplicación de IA

**Programa:** Maestría en Ciencia de Datos, Inteligencia Artificial y Negocios
**Módulo:** IA y Aplicaciones
**Clase 3:** Taller de Aplicaciones de Inteligencia Artificial
**Duración estimada:** 60 minutos
**Modalidad:** Individual o grupos de 2 a 4 participantes

---

# 1. Desafío

Diseñe e implemente un **MVP (Minimum Viable Product) de una aplicación de Inteligencia Artificial** que utilice conocimiento propio de una organización, profesión, negocio o proyecto personal para resolver un problema concreto.

La solución deberá utilizar documentos como fuente de conocimiento y aplicar una arquitectura basada en **RAG (Retrieval-Augmented Generation)**.

Puede utilizar:

* AnythingLLM;
* un LLM local o cloud;
* documentos propios;
* documentos públicos;
* documentación preparada específicamente para el ejercicio.

> **No comience seleccionando un modelo. Comience identificando un problema.**

---

# 2. ¿Qué debe construir?

Al finalizar el taller deberá contar con una solución conceptualmente similar a:

```text id="9y3txr"
             CONOCIMIENTO
                  │
     ┌────────────┼────────────┐
     │            │            │
   PDF          DOCX          TXT
     │            │            │
     └────────────┼────────────┘
                  ▼
             Procesamiento
                  ▼
                Chunks
                  ▼
              Embeddings
                  ▼
            Vector Database
                  │
Usuario ──► Pregunta
                  │
                  ▼
              Retrieval
                  │
                  ▼
                LLM
                  │
                  ▼
             Respuesta
                  │
                  ▼
          Validación humana
```

---

# 3. Regla principal

No se evaluará solamente si el chatbot responde.

La solución deberá poder justificar:

```text id="zcy2bn"
¿Qué problema resuelve?

¿Por qué necesita IA?

¿Por qué necesita RAG?

¿Qué conocimiento utiliza?

¿Qué modelo utiliza?

¿Por qué seleccionó ese modelo?

¿Cómo sabemos si funciona?

¿Qué ocurre cuando falla?

¿Qué debe revisar una persona?

¿Qué valor genera?
```

---

# 4. Paso 1 — Seleccione un problema

Piense en una actividad de su:

* organización;
* profesión;
* negocio;
* trabajo;
* investigación;
* proyecto personal.

Busque un proceso donde actualmente sea necesario:

* buscar información;
* leer documentos;
* interpretar contenido;
* responder preguntas repetitivas;
* comparar documentos;
* consultar procedimientos;
* revisar normativa;
* recuperar conocimiento especializado;
* preparar respuestas o análisis.

Complete:

```text id="s1hktd"
PROBLEMA ACTUAL

Actualmente:
____________________________________________
____________________________________________

Los usuarios necesitan:
____________________________________________

El principal problema es:
____________________________________________

Tiempo/esfuerzo/dificultad actual:
____________________________________________
```

---

# 5. Paso 2 — Defina el usuario

¿Quién utilizará la aplicación?

Ejemplos:

* cliente;
* abogado;
* analista financiero;
* técnico;
* administrador;
* estudiante;
* profesor;
* funcionario;
* vendedor;
* gerente.

Complete:

```text id="l2y1pq"
USUARIO PRINCIPAL

____________________________________________

El usuario utilizará la aplicación para:

____________________________________________
____________________________________________
```

---

# 6. Paso 3 — Identifique el conocimiento

¿Qué información necesita una persona actualmente para resolver ese problema?

Ejemplos:

```text id="qlzgqn"
Contratos
Normativa
Manuales
Políticas
Procedimientos
Reportes
Libros
Artículos
Documentación técnica
Preguntas frecuentes
Catálogos
Reglamentos
```

Complete:

```text id="20t6bh"
FUENTES DE CONOCIMIENTO

1. _________________________________________

2. _________________________________________

3. _________________________________________

4. _________________________________________
```

---

# 7. Seguridad de los documentos

Antes de cargar información pregúntese:

```text id="zcs63s"
¿Tengo autorización para utilizar estos documentos?

¿Contienen información confidencial?

¿Contienen datos personales?

¿Contienen secretos empresariales?

¿Pueden ser procesados por un proveedor externo?
```

Si existe alguna duda, utilice:

* documentos públicos;
* documentos anonimizados;
* datos ficticios;
* documentos preparados para el laboratorio.

---

# 8. Paso 4 — Defina qué hará la IA

Evite definir la solución simplemente como:

> "Un chatbot."

Defina una capacidad concreta.

Ejemplos:

```text id="hl15fv"
Consultar políticas internas.

Analizar contratos.

Responder preguntas sobre procedimientos.

Localizar información técnica.

Consultar normativa.

Asistir en soporte.

Buscar conocimiento académico.

Apoyar análisis documental.

Generar respuestas preliminares.
```

Complete:

```text id="mkq66u"
CAPACIDAD

Queremos que la aplicación pueda:

____________________________________________
____________________________________________
```

---

# 9. Paso 5 — Justifique el uso de IA

Pregúntese:

> ¿Podría resolverse fácilmente mediante una búsqueda tradicional, una base de datos o reglas?

Si la respuesta es sí, explique por qué la IA agrega valor.

Complete:

```text id="a08vjo"
¿POR QUÉ IA?

Utilizamos IA porque:

____________________________________________
____________________________________________
____________________________________________
```

Ejemplos de razones válidas:

* información principalmente no estructurada;
* preguntas expresadas en lenguaje natural;
* necesidad de resumir múltiples fuentes;
* interpretación contextual;
* gran variedad de consultas;
* generación de respuestas adaptadas al contexto.

---

# 10. Paso 6 — Justifique RAG

Pregúntese:

> ¿Por qué no utilizar simplemente un LLM sin documentos?

Complete:

```text id="et4szz"
¿POR QUÉ RAG?

La aplicación necesita consultar:

____________________________________________

Esta información es:

[ ] especializada
[ ] interna
[ ] actualizable
[ ] extensa
[ ] específica del dominio
[ ] no necesariamente conocida por el LLM

Por ello utilizaremos RAG porque:

____________________________________________
____________________________________________
```

---

# 11. Paso 7 — Seleccione la arquitectura

Identifique los componentes de su MVP.

```text id="wxdwj4"
Documentos
    │
    ▼
____________________
Embedding Model
    │
    ▼
____________________
Vector Database
    │
    ▼
____________________
Retriever / RAG
    │
    ▼
____________________
LLM
    │
    ▼
Usuario
```

---

# 12. Paso 8 — Seleccione el LLM

Registre:

```text id="2h8b70"
LLM:
____________________________________________

Proveedor:
____________________________________________

[ ] Local

[ ] Cloud
```

Ahora justifique la decisión.

Considere:

| Criterio                    | Análisis |
| --------------------------- | -------- |
| Calidad de respuestas       |          |
| Privacidad                  |          |
| Costo                       |          |
| Latencia                    |          |
| Idioma                      |          |
| Contexto                    |          |
| Hardware requerido          |          |
| Facilidad de implementación |          |

---

# 13. No existe un "mejor modelo" universal

La pregunta no es:

> ¿Cuál es el mejor LLM?

La pregunta correcta es:

> **¿Cuál es el modelo más adecuado para este problema y estas restricciones?**

Por ejemplo:

```text id="ehm52a"
Alta privacidad
      ↓
Modelo local podría ser conveniente


Alta complejidad de razonamiento
      ↓
Modelo cloud más potente podría ser conveniente


Muchas consultas
      ↓
Costo por consulta se vuelve importante


Hardware limitado
      ↓
Modelo local grande podría no ser viable
```

---

# 14. Paso 9 — Embeddings

Registre el modelo de embeddings utilizado.

```text id="65u2hm"
EMBEDDING MODEL

Modelo:
____________________________________________

Proveedor:
____________________________________________
```

Explique brevemente:

```text id="s3ldmm"
Su función dentro de nuestra arquitectura es:

____________________________________________
____________________________________________
```

---

# 15. Paso 10 — Cree el Workspace

En AnythingLLM:

1. cree un nuevo Workspace;
2. utilice un nombre relacionado con su proyecto;
3. configure el LLM;
4. configure los embeddings;
5. incorpore sus documentos;
6. procese el conocimiento.

Nombre:

```text id="o6zz0d"
____________________________________________
```

---

# 16. Paso 11 — Configure el comportamiento

Defina instrucciones para su asistente.

Puede comenzar con esta estructura:

```text id="i6nxcr"
Eres un asistente especializado en:

[DOMINIO]

Tu función es:

[OBJETIVO]

Utiliza prioritariamente los documentos proporcionados.

Cuando respondas:

1. identifica la información relevante;
2. responde claramente;
3. utiliza evidencia de los documentos;
4. indica las fuentes utilizadas;
5. no inventes información;
6. diferencia hechos de interpretaciones;
7. indica cuando no exista información suficiente;
8. identifica información que debería verificarse;
9. indica cuándo se necesita revisión humana.

Si no existe evidencia suficiente, responde:

"NO EXISTE INFORMACIÓN SUFICIENTE EN LAS FUENTES
DISPONIBLES PARA RESPONDER CON SEGURIDAD."
```

Adapte estas instrucciones a su problema.

---

# 17. Paso 12 — Primera prueba

Realice una pregunta cuya respuesta conozca.

```text id="ojh1l1"
PREGUNTA:

____________________________________________
```

Registre:

```text id="nhz5mg"
RESPUESTA CORRECTA:

[ ] Sí

[ ] Parcialmente

[ ] No


FUENTE CORRECTA:

[ ] Sí

[ ] No


OBSERVACIONES:

____________________________________________
```

---

# 18. Paso 13 — Diseñe pruebas

Una demostración exitosa no significa que el sistema funcione correctamente.

Debe probarlo.

Diseñe como mínimo:

## T1 — Información explícita

Respuesta presente claramente en un documento.

## T2 — Información distribuida

Requiere utilizar dos o más documentos.

## T3 — Pregunta ambigua

Falta información para responder correctamente.

## T4 — Información inexistente

La respuesta no aparece en los documentos.

## T5 — Consulta de riesgo

Una respuesta incorrecta podría generar una decisión inadecuada.

---

# 19. Matriz de evaluación

Complete:

| Test | Pregunta | Correcta | Fuente correcta | Inventó información | Observación |
| ---- | -------- | -------- | --------------- | ------------------- | ----------- |
| T1   |          |          |                 |                     |             |
| T2   |          |          |                 |                     |             |
| T3   |          |          |                 |                     |             |
| T4   |          |          |                 |                     |             |
| T5   |          |          |                 |                     |             |

---

# 20. Paso 14 — Analice los errores

Seleccione el resultado más problemático.

Pregúntese:

```text id="omzqmy"
¿La información existe?

        ↓

¿El documento fue procesado?

        ↓

¿Se recuperó el documento correcto?

        ↓

¿Se recuperó el chunk correcto?

        ↓

¿El contexto era suficiente?

        ↓

¿Las instrucciones eran adecuadas?

        ↓

¿El LLM interpretó incorrectamente?
```

---

# 21. Paso 15 — Mejore el MVP

Realice al menos **una modificación**.

Puede cambiar:

* instrucciones;
* documentos;
* organización del conocimiento;
* configuración RAG;
* modelo;
* parámetros;
* forma de realizar la consulta.

Registre:

```text id="s15gk4"
PROBLEMA DETECTADO

____________________________________________


MODIFICACIÓN

____________________________________________


RESULTADO ANTES

____________________________________________


RESULTADO DESPUÉS

____________________________________________
```

---

# 22. Paso 16 — Identifique el nivel de automatización

Clasifique las acciones de su solución.

### A — Automatizable

Puede ejecutarse automáticamente con bajo riesgo.

### H — Human-in-the-Loop

La IA prepara una respuesta o acción, pero una persona debe aprobarla.

### P — Decisión profesional

La decisión debe permanecer bajo responsabilidad de una persona autorizada.

Complete:

| Acción | A / H / P | Justificación |
| ------ | --------- | ------------- |
|        |           |               |
|        |           |               |
|        |           |               |

---

# 23. Paso 17 — Identifique riesgos

Seleccione los principales riesgos.

```text id="5kqnxp"
[ ] Alucinaciones

[ ] Información desactualizada

[ ] Recuperación incorrecta

[ ] Información incompleta

[ ] Privacidad

[ ] Seguridad

[ ] Sesgos

[ ] Uso incorrecto por usuarios

[ ] Automatización excesiva

[ ] Otro:
____________________________________________
```

---

# 24. Paso 18 — Determine el valor

La existencia de IA no garantiza valor.

Complete:

```text id="9grt06"
PROCESO ACTUAL

____________________________________________


CON EL MVP

____________________________________________


VALOR ESPERADO

[ ] Menor tiempo

[ ] Menor costo

[ ] Mayor acceso al conocimiento

[ ] Mayor consistencia

[ ] Mejor experiencia del usuario

[ ] Reducción de trabajo repetitivo

[ ] Apoyo a decisiones

[ ] Otro:
____________________________________________
```

---

# 25. Escenarios orientativos

Si no dispone de un caso propio puede utilizar alguno de los siguientes.

---

## Caso A — Finanzas

### Problema

Los analistas necesitan consultar manualmente:

* políticas crediticias;
* procedimientos;
* criterios de evaluación;
* preguntas frecuentes.

### MVP

**Asistente de consulta para analistas financieros.**

Podría responder:

> ¿Qué documentos se requieren para este tipo de solicitud?

> ¿Qué procedimiento corresponde?

> ¿Qué información falta?

La aprobación final permanece bajo responsabilidad profesional.

---

## Caso B — Legal

### Problema

Existe una colección de:

* contratos;
* cláusulas estándar;
* normativa;
* procedimientos internos.

### MVP

**Asistente de consulta documental legal.**

Podría:

* localizar cláusulas;
* comparar información;
* identificar obligaciones;
* recuperar normativa relacionada;
* preparar análisis preliminares.

No sustituye la opinión profesional.

---

## Caso C — Tecnología

### Problema

Los técnicos consultan:

* manuales;
* procedimientos;
* incidentes anteriores;
* documentación de sistemas;
* troubleshooting.

### MVP

**Asistente interno de soporte técnico.**

Podría:

* localizar procedimientos;
* recuperar soluciones anteriores;
* identificar pasos de diagnóstico;
* recomendar documentación relevante.

Los cambios críticos requieren aprobación.

---

## Caso D — Educación

### Problema

Estudiantes y docentes necesitan consultar:

* reglamentos;
* programas;
* materiales;
* bibliografía;
* procedimientos académicos.

### MVP

**Asistente académico especializado.**

Podría responder utilizando exclusivamente el conocimiento institucional proporcionado.

---

## Caso E — Negocio / PYME

### Problema

Clientes o trabajadores realizan constantemente preguntas sobre:

* productos;
* servicios;
* políticas;
* procedimientos;
* catálogo;
* garantías.

### MVP

**Asistente de conocimiento del negocio.**

Podría funcionar como primera línea de consulta.

---

## Caso F — Proyecto personal

Seleccione:

* libros;
* artículos;
* notas;
* investigaciones;
* documentación propia.

### MVP

Construya un **asistente especializado en su propio conocimiento**.

---

# 26. Entregable

El resultado del taller incluirá:

### 1. MVP funcional

Workspace configurado y probado.

### 2. Ficha de decisión

Justificación de:

* problema;
* IA;
* RAG;
* LLM;
* embeddings;
* local/cloud;
* documentos.

### 3. Evidencia

Resultados de los cinco tests.

### 4. Mejora

Una modificación realizada a partir de los resultados.

### 5. Riesgos

Principales riesgos identificados.

### 6. Control humano

Definición de qué puede automatizarse y qué necesita supervisión.

---

# 27. Presentación rápida

Prepare una explicación de aproximadamente **2 minutos**.

Utilice esta estructura:

```text id="7udq6w"
1. Nuestro problema es...

2. Construimos...

3. Utilizamos estos documentos...

4. Elegimos este modelo porque...

5. Durante las pruebas descubrimos...

6. El principal riesgo es...

7. El valor para el proceso sería...
```

---

# 28. Criterios de evaluación

| Criterio                              | Peso |
| ------------------------------------- | ---: |
| Problema y valor del caso de uso      |  20% |
| Justificación del uso de IA y RAG     |  20% |
| Justificación de modelo y componentes |  20% |
| MVP funcional                         |  15% |
| Evaluación mediante pruebas           |  15% |
| Riesgos y control humano              |  10% |

---

# 29. Pregunta final

Después de construir su MVP responda:

> **Si mañana esta aplicación tuviera que utilizarse realmente dentro de la organización, ¿qué necesitaríamos agregar antes de considerarla una solución de producción?**

Considere:

* seguridad;
* autenticación;
* permisos;
* privacidad;
* monitoreo;
* evaluación;
* actualización del conocimiento;
* auditoría;
* costos;
* disponibilidad;
* integración con otros sistemas;
* responsabilidad humana.

---

# 30. Conclusión

Durante este taller no hemos construido solamente un chatbot.

Hemos recorrido:

```text id="ypufyo"
PROBLEMA
   ↓
CONOCIMIENTO
   ↓
ARQUITECTURA
   ↓
MODELOS
   ↓
RAG
   ↓
MVP
   ↓
PRUEBAS
   ↓
RIESGOS
   ↓
CONTROL
   ↓
VALOR
```

> **Una buena aplicación de Inteligencia Artificial no comienza preguntando qué modelo utilizar. Comienza identificando un problema y termina demostrando que la solución genera valor de manera controlada y verificable.**
