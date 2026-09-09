---
marp: false
theme: default
paginate: true
---

# IA y Aplicaciones

## Clase 2

### NLP, IA Generativa y Large Language Models

**Maestría en Ciencia de Datos, Inteligencia Artificial y Negocios**

**Pregunta guía**

> ¿Cómo podemos utilizar modelos de lenguaje para transformar información no estructurada en conocimiento, decisiones y acciones?

---

# 1. De la IA al lenguaje

En la clase anterior analizamos:

* Machine Learning
* Redes neuronales
* Deep Learning
* Aplicaciones de IA

Ahora abordaremos un problema diferente:

> **¿Cómo puede una máquina trabajar con lenguaje humano?**

Ejemplos:

* contratos
* correos
* informes
* consultas
* expedientes
* conversaciones

---

# 2. El lenguaje como dato

Para una persona:

> “El cliente solicita ampliar el plazo de pago porque sus ingresos disminuyeron.”

Podemos identificar:

* cliente
* solicitud
* motivo
* situación financiera
* posible acción

Para una computadora, inicialmente:

> **el texto es una secuencia de símbolos.**

El reto es convertirlo en una representación que permita **analizarlo y procesarlo**.

---

# 3. ¿Qué es NLP?

## Natural Language Processing

El **Procesamiento de Lenguaje Natural (NLP)** reúne técnicas que permiten a las computadoras:

* analizar texto;
* clasificar información;
* extraer entidades;
* traducir;
* resumir;
* responder preguntas;
* generar lenguaje.

### Aplicaciones

**NLP → lenguaje → información → acción**

---

# 4. NLP tradicional

Los primeros sistemas dependían fuertemente de:

* reglas;
* diccionarios;
* patrones;
* palabras clave;
* expresiones regulares.

Ejemplo:

```text
SI contiene "factura"
Y contiene "vencida"
→ Categoría: Cobranza
```

### Ventaja

Comportamiento controlado.

### Limitación

El lenguaje humano es **ambiguo, contextual y variable**.

---

# 5. Del texto a una representación matemática

Los modelos de Machine Learning necesitan trabajar con representaciones numéricas.

Una palabra puede representarse mediante un vector:

```text
"banco"
      ↓
[0.21, -0.73, 0.15, ..., 0.42]
```

Estas representaciones se conocen como:

## Embeddings

Permiten capturar relaciones semánticas entre elementos.

---

# 6. El contexto importa

Consideremos:

> “El cliente acudió al banco para solicitar un crédito.”

y:

> “El banco de la plaza fue reparado.”

La palabra **banco** aparece en ambos casos.

Pero su significado depende del:

* contexto;
* palabras cercanas;
* estructura de la oración;
* intención.

### Problema

> **La misma palabra puede representar conceptos diferentes.**

---

# 7. Transformers

Los **Transformers** introdujeron una forma más efectiva de representar las relaciones entre elementos de una secuencia.

Idea central:

> **Attention permite determinar qué partes del contexto son relevantes para interpretar cada elemento.**

Ejemplo:

```text
El cliente solicitó un crédito
             ↑
        ¿qué significa?
             ↑
      contexto completo
```

---

# 8. Attention — idea conceptual

No necesitamos memorizar la matemática para comprender su aplicación.

Podemos pensar en:

```text
Palabra actual
      ↓
¿Qué otras palabras son relevantes?
      ↓
Asignación de importancia
      ↓
Representación contextual
```

Esto permite trabajar mejor con:

* relaciones entre palabras;
* contexto;
* dependencias;
* significado.

---

# 9. ¿Qué es un LLM?

## Large Language Model

Un LLM es un modelo entrenado con grandes cantidades de texto para aprender patrones del lenguaje.

Conceptualmente:

```text
Grandes cantidades de texto
            ↓
        Entrenamiento
            ↓
     Modelo de lenguaje
            ↓
Predicción / generación de texto
```

El modelo aprende **regularidades estadísticas y representaciones complejas del lenguaje**.

---

# 10. ¿Qué hace realmente un LLM?

Ante una entrada:

> “El informe financiero muestra un incremento de…”

el modelo calcula qué continuación resulta más probable según lo aprendido y el contexto.

De forma simplificada:

```text
Contexto
   ↓
Representación
   ↓
Modelo
   ↓
Predicción
   ↓
Nuevo token
   ↓
Predicción siguiente
   ↓
...
```

### Importante

> Generar lenguaje coherente **no garantiza que la información sea verdadera**.

---

# 11. IA Generativa

La IA Generativa produce contenido nuevo a partir de una instrucción o contexto.

Puede generar:

* texto;
* imágenes;
* código;
* audio;
* resúmenes;
* documentos.

En esta clase nos concentramos principalmente en:

## IA Generativa + LLMs

---

# 12. LLM ≠ ChatGPT

Es importante diferenciar conceptos.

| Concepto          | Función                                                     |
| ----------------- | ----------------------------------------------------------- |
| **LLM**           | Modelo de lenguaje                                          |
| **IA Generativa** | Tecnología/categoría para generar contenido                 |
| **ChatGPT**       | Aplicación/interfaz basada en modelos de IA                 |
| **Copilot**       | Asistente integrado en un contexto de trabajo               |
| **RAG**           | Estrategia para proporcionar conocimiento externo al modelo |

### Idea clave

> **El modelo es una pieza. La solución es mucho más que el modelo.**

---

# 13. ¿Qué puede hacer un LLM?

### Transformar

* resumir;
* traducir;
* reformular;
* convertir formatos.

### Analizar

* clasificar;
* extraer información;
* comparar;
* identificar patrones.

### Generar

* respuestas;
* informes;
* propuestas;
* código.

### Asistir

* responder preguntas;
* apoyar decisiones;
* interactuar con usuarios.

---

# 14. Del prompt a la solución

Un error frecuente es pensar:

> “Tenemos ChatGPT → tenemos una solución de IA.”

En realidad:

```text
Problema
   ↓
Proceso
   ↓
Datos / documentos
   ↓
Modelo
   ↓
Instrucciones
   ↓
Validación
   ↓
Acción
   ↓
Medición
```

### La pregunta importante no es:

> ¿Qué prompt puedo escribir?

### Sino:

> **¿Qué problema profesional quiero resolver?**

---

# 15. Ejemplo: análisis de contratos

### Situación

Una organización recibe cientos de contratos.

Una persona debe revisar:

* fechas;
* partes;
* obligaciones;
* montos;
* cláusulas;
* riesgos.

### IA generativa

Puede ayudar a:

```text
Contrato
   ↓
Extracción
   ↓
Clasificación
   ↓
Identificación de cláusulas
   ↓
Resumen
   ↓
Revisión humana
```

La IA **asiste** el proceso.

No necesariamente reemplaza la responsabilidad profesional.

---

# 16. Ejemplo: análisis financiero

Un analista recibe un reporte mensual.

El LLM puede:

* identificar variaciones;
* resumir resultados;
* explicar indicadores;
* comparar períodos;
* generar preguntas para profundizar.

Pero:

> **La interpretación financiera y la decisión siguen requiriendo criterio profesional.**

---

# 17. Ejemplo: soporte tecnológico

Un sistema recibe:

> “El servicio dejó de responder después del último despliegue.”

Un asistente puede:

1. clasificar el incidente;
2. identificar posibles causas;
3. consultar documentación;
4. sugerir acciones;
5. generar una respuesta.

Pero una acción crítica puede requerir:

> **validación humana antes de ejecutarse.**

---

# 18. El problema del conocimiento

Supongamos que preguntamos:

> “¿Cuál es el procedimiento interno para aprobar un crédito?”

El modelo puede generar una respuesta plausible.

Pero:

* ¿conoce nuestro procedimiento?
* ¿está actualizado?
* ¿puede demostrar de dónde obtuvo la respuesta?
* ¿qué ocurre si inventa una política?

Necesitamos proporcionar **conocimiento confiable y contextualizado**.

---

# 19. RAG

## Retrieval-Augmented Generation

RAG combina:

**Recuperación de información + generación mediante LLM**

```text
Pregunta
   ↓
Buscar información relevante
   ↓
Documentos / conocimiento
   ↓
Contexto
   ↓
LLM
   ↓
Respuesta fundamentada
```

Esto permite utilizar información específica de:

* empresas;
* normativa;
* manuales;
* contratos;
* procedimientos;
* documentación técnica.

---

# 20. RAG no elimina todos los riesgos

RAG puede mejorar:

* contextualización;
* trazabilidad;
* actualización;
* fundamentación.

Pero todavía debemos evaluar:

* calidad de los documentos;
* recuperación correcta;
* interpretación del LLM;
* información contradictoria;
* permisos de acceso;
* privacidad.

> **La arquitectura mejora el problema; no elimina la necesidad de control.**

---

# 21. Riesgos de los LLM

## Alucinaciones

Información incorrecta presentada de forma convincente.

## Sesgos

Los resultados pueden reproducir patrones presentes en los datos.

## Privacidad

No debemos enviar información sensible sin evaluar previamente las condiciones de uso.

## Seguridad

Los sistemas pueden estar expuestos a instrucciones o entradas maliciosas.

## Dependencia

Una organización puede delegar demasiado criterio a un sistema automático.

---

# 22. ¿Cómo evaluamos una solución?

No basta con preguntar:

> “¿La respuesta parece buena?”

Debemos definir criterios.

### Calidad

* exactitud;
* completitud;
* consistencia.

### Negocio

* tiempo ahorrado;
* reducción de errores;
* productividad;
* satisfacción.

### Riesgo

* información incorrecta;
* privacidad;
* sesgo;
* impacto de errores.

---

# 23. IA como asistente profesional

Una aplicación madura puede seguir este patrón:

```text
          PROFESIONAL
               ↓
             IA
               ↓
       Información /
       recomendación
               ↓
       VALIDACIÓN
          HUMANA
               ↓
            DECISIÓN
               ↓
             ACCIÓN
```

La IA aumenta las capacidades del profesional.

### No necesariamente sustituye al profesional.

---

# 24. Ahora: de la teoría a la práctica

## Vamos a experimentar

Durante las siguientes actividades trabajaremos con situaciones reales de:

**Finanzas · Legal · Tecnología**

Analizaremos:

1. Extracción de información.
2. Clasificación de documentos.
3. Asistentes profesionales.
4. RAG.

### Regla de la clase

> **No debemos aceptar automáticamente una respuesta de IA.**

Debemos preguntarnos:

**¿Es correcta?
¿Es verificable?
¿Es segura?
¿Es útil?
¿Genera valor?**

---

# 25. Actividad 1

## Extracción y estructuración

**Problema**

Transformar información no estructurada en datos utilizables.

```text
Documento
    ↓
LLM
    ↓
Información estructurada
    ↓
Verificación
```

### Tiempo

**20 minutos**

### Producto

Prompt + resultado + errores identificados.

---

# 26. Actividad 2

## Clasificación de documentos

Diseñar un sistema que determine:

* categoría;
* prioridad;
* justificación;
* acción recomendada.

### Pregunta

> ¿Qué tan confiable sería automatizar esta clasificación?

### Tiempo

**25 minutos**

---

# 27. Actividad 3

## Asistente profesional

Elegir un escenario:

**Finanzas · Legal · Tecnología**

Diseñar:

```text
Problema
   ↓
Información
   ↓
LLM
   ↓
Resultado
   ↓
Validación
   ↓
Acción
```

### Tiempo

**30 minutos**

---

# 28. Actividad 4

## RAG

Compararemos:

### A

LLM utilizando conocimiento general.

### B

LLM utilizando documentación proporcionada.

Evaluaremos:

* precisión;
* fundamentación;
* trazabilidad;
* riesgos.

### Tiempo

**30 minutos**

---

# 29. Idea central

> **Un LLM puede generar respuestas.**
>
> **Una solución profesional de IA debe generar resultados confiables, verificables y útiles.**

La diferencia está en:

**Datos + contexto + modelo + proceso + evaluación + control**

---

# 30. Próxima clase

## De asistentes a sistemas inteligentes

La siguiente pregunta será:

> **¿Qué ocurre cuando conectamos IA con datos, sistemas y procesos empresariales?**

### Próximos temas

* Sistemas de recomendación.
* Automatización inteligente.
* IA + RPA.
* Agentes.
* Banca.
* Retail.
* Gobierno.

**Del modelo → al proceso → al valor empresarial.**

---

# Bibliografía y recursos

* Goodfellow, I., Bengio, Y., & Courville, A. *Deep Learning*. MIT Press.
* Jurafsky, D. & Martin, J. H. *Speech and Language Processing*.
* Vaswani, A. et al. *Attention Is All You Need*. 2017.
* Brown, T. et al. *Language Models are Few-Shot Learners*. 2020.
* Lewis, P. et al. *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks*. 2020.
* Documentación técnica de los proveedores de LLM utilizados durante las prácticas.

---
