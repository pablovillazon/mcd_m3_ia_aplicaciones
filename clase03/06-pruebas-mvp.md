# Plan de Pruebas — MVP de Aplicación de IA con RAG

**Programa:** Maestría en Ciencia de Datos, Inteligencia Artificial y Negocios
**Módulo:** IA y Aplicaciones
**Clase 3:** Taller de Aplicaciones de Inteligencia Artificial

**Nombre / Grupo:** ____________________________________________

**Nombre del MVP:** ____________________________________________

---

# 1. Propósito

Una aplicación de IA no debe evaluarse únicamente preguntando:

> **¿La respuesta parece correcta?**

Durante este ejercicio evaluaremos sistemáticamente el MVP construido con RAG.

Buscaremos comprobar:

* si recupera información correcta;
* si utiliza las fuentes adecuadas;
* si responde basándose en evidencia;
* si reconoce información faltante;
* si evita inventar información;
* cómo se comporta ante preguntas ambiguas;
* cómo responde ante consultas de mayor riesgo.

---

# 2. Principio de evaluación

Una respuesta generada por un LLM puede ser:

* clara;
* extensa;
* profesional;
* convincente;

y aun así ser **incorrecta**.

Por ello debemos evaluar al menos tres componentes:

```text id="bkg6jf"
RECUPERACIÓN
     ↓
¿Encontró la información correcta?

CONTEXTO
     ↓
¿La información recuperada era suficiente?

GENERACIÓN
     ↓
¿El LLM utilizó correctamente esa información?
```

---

# 3. Antes de comenzar

Registre la configuración utilizada.

## LLM

```text id="2c8btf"
Modelo:
____________________________________________

Proveedor:
____________________________________________

Local / Cloud:
____________________________________________
```

## Embeddings

```text id="h4y3xi"
Modelo:
____________________________________________

Proveedor:
____________________________________________
```

## Conocimiento

```text id="m65nhf"
Cantidad de documentos:
____________________________________________

Tipos:
____________________________________________
```

---

# 4. Escala de resultados

Utilizaremos tres niveles.

## CORRECTA

La respuesta:

* coincide con la evidencia;
* utiliza correctamente las fuentes;
* no agrega información falsa;
* responde adecuadamente a la pregunta.

## PARCIAL

La respuesta:

* contiene información correcta;
* pero está incompleta;
* utiliza evidencia insuficiente;
* omite alguna condición importante;
* o introduce una interpretación discutible.

## FALLIDA

La respuesta:

* contradice los documentos;
* inventa información;
* utiliza una fuente incorrecta;
* presenta una inferencia como hecho;
* responde cuando debería reconocer que no existe evidencia suficiente.

---

# 5. Test T1 — Información explícita

## Objetivo

Verificar si el sistema puede recuperar información que aparece claramente en un documento.

### Ejemplos

**Legal**

> ¿Cuál es el plazo establecido para la renovación del contrato?

**Finanzas**

> ¿Qué documentos se requieren para realizar la solicitud?

**Tecnología**

> ¿Qué procedimiento debe ejecutarse después de un incidente?

**Educación**

> ¿Cuál es el requisito establecido para aprobar la asignatura?

---

## Diseñe su prueba

### Pregunta

```text id="m4vsm7"
____________________________________________________

____________________________________________________
```

### Respuesta correcta esperada

Antes de consultar el sistema escriba qué debería responder.

```text id="ovf77i"
____________________________________________________

____________________________________________________
```

### Documento donde se encuentra

```text id="ljogyi"
____________________________________________________
```

---

## Ejecute

### Resultado obtenido

```text id="vkrzsn"
____________________________________________________

____________________________________________________
```

### Evaluación

* [ ] CORRECTA
* [ ] PARCIAL
* [ ] FALLIDA

### ¿Utilizó la fuente correcta?

* [ ] Sí
* [ ] No
* [ ] No fue posible determinarlo

---

# 6. Test T2 — Información distribuida

## Objetivo

Evaluar si el sistema puede responder utilizando información presente en **dos o más documentos**.

La respuesta no debería encontrarse completamente en una sola fuente.

### Ejemplo conceptual

```text id="jmfowz"
Documento A
    ↓
Regla general

+

Documento B
    ↓
Situación particular

=

Respuesta
```

### Pregunta

```text id="d2x5gq"
____________________________________________________

____________________________________________________
```

### Documentos necesarios

```text id="2r0gmg"
1. __________________________________________

2. __________________________________________
```

### Respuesta esperada

```text id="fb89lo"
____________________________________________________

____________________________________________________
```

---

## Resultado

```text id="0v3kgq"
____________________________________________________

____________________________________________________
```

### Evaluación

* [ ] CORRECTA
* [ ] PARCIAL
* [ ] FALLIDA

### ¿Recuperó todas las fuentes necesarias?

* [ ] Sí
* [ ] Parcialmente
* [ ] No

---

# 7. Test T3 — Pregunta ambigua

## Objetivo

Observar qué ocurre cuando el usuario realiza una pregunta que **no contiene suficiente información**.

Ejemplos:

> ¿Puedo aprobarlo?

> ¿Esto está permitido?

> ¿Qué hacemos?

> ¿Corresponde aplicar el procedimiento?

Una buena respuesta no necesariamente debe responder inmediatamente.

Podría solicitar información adicional.

---

## Pregunta

```text id="rf3kpf"
____________________________________________________
```

## ¿Qué información falta?

```text id="pq0hhu"
____________________________________________________

____________________________________________________
```

---

## Resultado

```text id="cwwy84"
____________________________________________________

____________________________________________________
```

### El sistema:

* [ ] Solicitó información adicional.
* [ ] Reconoció la ambigüedad.
* [ ] Respondió haciendo explícitas sus suposiciones.
* [ ] Respondió como si tuviera toda la información.
* [ ] Inventó información.

### Evaluación

* [ ] CORRECTA
* [ ] PARCIAL
* [ ] FALLIDA

---

# 8. Test T4 — Información inexistente

## Objetivo

Evaluar qué ocurre cuando la respuesta **no existe en los documentos**.

Esta es una de las pruebas más importantes.

Diseñe una pregunta que parezca razonable dentro del dominio, pero cuya respuesta usted sepa que no está disponible.

### Ejemplo

Si los documentos contienen información financiera pero no datos de facturación:

> ¿Cuál fue la facturación total de la empresa durante 2025?

---

## Pregunta

```text id="7t9e48"
____________________________________________________

____________________________________________________
```

### Resultado esperado

El sistema debería reconocer que no dispone de evidencia suficiente.

---

## Resultado obtenido

```text id="ybdr1c"
____________________________________________________

____________________________________________________
```

### El sistema:

* [ ] Indicó que no existe información suficiente.
* [ ] Solicitó información adicional.
* [ ] Respondió utilizando conocimiento externo.
* [ ] Generó una respuesta sin evidencia.
* [ ] Inventó datos.

### Evaluación

* [ ] CORRECTA
* [ ] PARCIAL
* [ ] FALLIDA

---

# 9. Test T5 — Consulta de riesgo

## Objetivo

Evaluar cómo se comporta la aplicación cuando una respuesta incorrecta podría producir consecuencias importantes.

Ejemplos:

### Finanzas

> ¿Debemos aprobar esta solicitud?

### Legal

> ¿Debemos terminar inmediatamente el contrato?

### Tecnología

> ¿Debemos ejecutar el rollback en producción?

### Negocio

> ¿Debemos rechazar automáticamente este reclamo?

---

## Pregunta

```text id="5ayfdq"
____________________________________________________

____________________________________________________
```

---

## ¿Cuál sería el riesgo de una respuesta incorrecta?

```text id="jsjgzp"
____________________________________________________

____________________________________________________
```

---

## Resultado obtenido

```text id="0w6uxl"
____________________________________________________

____________________________________________________
```

### El sistema:

* [ ] Presentó evidencia.
* [ ] Reconoció incertidumbre.
* [ ] Identificó información faltante.
* [ ] Recomendó revisión humana.
* [ ] Presentó una recomendación como decisión definitiva.
* [ ] Inventó información.

### Evaluación

* [ ] CORRECTA
* [ ] PARCIAL
* [ ] FALLIDA

---

# 10. Resumen de pruebas

Complete:

| Test             | Resultado | Fuente correcta | Inventó información | Revisión humana |
| ---------------- | --------- | --------------- | ------------------- | --------------- |
| T1 — Explícita   |           |                 |                     |                 |
| T2 — Distribuida |           |                 |                     |                 |
| T3 — Ambigua     |           |                 |                     |                 |
| T4 — Inexistente |           |                 |                     |                 |
| T5 — Riesgo      |           |                 |                     |                 |

---

# 11. Resultado global

Cantidad de pruebas:

```text id="jqd7zv"
CORRECTAS: ______ / 5

PARCIALES: ______ / 5

FALLIDAS: ______ / 5
```

No utilizaremos este resultado como una medida absoluta de calidad.

Cinco pruebas son insuficientes para demostrar que un sistema está listo para producción.

Su objetivo es introducir una forma **sistemática y reproducible de evaluar el MVP**.

---

# 12. Diagnóstico

Seleccione la prueba que produjo el resultado más problemático.

```text id="nmmc2r"
Test:
____________________________________________

Problema observado:
____________________________________________
```

Ahora determine dónde podría encontrarse el problema.

```text id="0vmydw"
Pregunta
   │
   ▼
¿Era clara?
   │
   ▼
Documento
   │
   ▼
¿Contenía la información?
   │
   ▼
Retrieval
   │
   ▼
¿Recuperó el documento correcto?
   │
   ▼
Chunk
   │
   ▼
¿Recuperó suficiente contexto?
   │
   ▼
Prompt
   │
   ▼
¿Las instrucciones eran adecuadas?
   │
   ▼
LLM
   │
   ▼
¿Interpretó correctamente?
```

---

# 13. Clasifique el posible origen

* [ ] Pregunta del usuario
* [ ] Información inexistente
* [ ] Documento
* [ ] Procesamiento del documento
* [ ] Chunking
* [ ] Embeddings
* [ ] Retrieval
* [ ] Prompt / instrucciones
* [ ] LLM
* [ ] Configuración
* [ ] Otro: ______________________________

---

# 14. Proponga una mejora

No cambie automáticamente el LLM.

Primero determine qué componente podría estar causando el problema.

## Hipótesis

```text id="ipih3a"
Creemos que el problema ocurre porque:

____________________________________________________

____________________________________________________
```

## Modificación

```text id="ejxjfl"
Modificaremos:

____________________________________________________

____________________________________________________
```

---

# 15. Repita la prueba

Ejecute nuevamente **la misma pregunta**.

### Resultado anterior

```text id="s5iq86"
____________________________________________________
```

### Resultado nuevo

```text id="dt4z6n"
____________________________________________________
```

### Resultado

* [ ] Mejoró
* [ ] No cambió significativamente
* [ ] Empeoró

---

# 16. ¿Tenemos evidencia de mejora?

Explique:

```text id="m33ddp"
____________________________________________________

____________________________________________________
```

Esta comparación introduce una práctica importante:

> **Las modificaciones de una aplicación de IA deberían evaluarse utilizando pruebas reproducibles.**

---

# 17. Evaluación del Retrieval

Seleccione una pregunta y observe las fuentes recuperadas.

## Pregunta

```text id="qfn8v9"
____________________________________________________
```

## Fuente esperada

```text id="okmv4f"
____________________________________________________
```

## Fuente recuperada

```text id="zt5y2k"
____________________________________________________
```

### Resultado

* [ ] Correcta
* [ ] Parcialmente relevante
* [ ] Incorrecta

---

# 18. Retrieval vs Generation

Utilice esta regla durante el diagnóstico.

### Caso A

```text id="p66h37"
Fuente incorrecta
      +
Respuesta incorrecta
```

Primero investigue el **Retrieval**.

### Caso B

```text id="q3o4yw"
Fuente correcta
      +
Respuesta incorrecta
```

Investigue:

* prompt;
* instrucciones;
* contexto;
* comportamiento del LLM.

### Caso C

```text id="2rw8qm"
Fuente correcta
      +
Respuesta correcta
```

Resultado esperado.

---

# 19. Evaluación de Grounding

Para una respuesta importante pregúntese:

> **¿Puedo encontrar evidencia para esta afirmación en los documentos recuperados?**

Seleccione una afirmación producida por el sistema.

```text id="rzp43j"
AFIRMACIÓN:

____________________________________________________
```

### Evidencia encontrada

```text id="54yvub"
____________________________________________________
```

### Clasificación

* [ ] Sustentada por evidencia.
* [ ] Parcialmente sustentada.
* [ ] Sin evidencia.
* [ ] Contradice la evidencia.

---

# 20. Prueba de Human-in-the-Loop

Seleccione una acción propuesta por el sistema.

```text id="7ej8x7"
ACCIÓN:

____________________________________________________
```

Clasifique:

### A — Automatizable

Bajo riesgo y reglas claras.

### H — Human-in-the-Loop

La IA prepara la acción, pero una persona debe aprobarla.

### P — Decisión Profesional

La decisión debe permanecer bajo responsabilidad humana.

```text id="euwr3a"
Clasificación: A / H / P

Justificación:

____________________________________________________

____________________________________________________
```

---

# 21. Resultado final del MVP

Después de las pruebas, clasifique el MVP.

### Nivel 1 — Demostración

* responde algunas preguntas;
* necesita pruebas adicionales;
* existen errores importantes.

### Nivel 2 — MVP

* resuelve el problema principal;
* funciona en los casos probados;
* existen controles básicos;
* todavía no está listo para producción.

### Nivel 3 — Candidato a piloto

* resultados consistentes en un conjunto mayor de pruebas;
* riesgos identificados;
* fuentes verificables;
* controles definidos;
* puede evaluarse con usuarios reales en un entorno controlado.

Seleccione:

```text id="ur74j6"
[ ] Nivel 1 — Demostración

[ ] Nivel 2 — MVP

[ ] Nivel 3 — Candidato a piloto
```

## Evidencia para esta clasificación

```text id="wvyu72"
____________________________________________________

____________________________________________________

____________________________________________________
```

---

# 22. Antes de producción

Incluso si las cinco pruebas fueron correctas:

> **Esto NO demuestra que la aplicación esté lista para producción.**

Una solución real debería considerar además:

```text id="5mmyxi"
Evaluación con más casos
        +
Seguridad
        +
Privacidad
        +
Autenticación
        +
Autorización
        +
Monitoreo
        +
Auditoría
        +
Control de costos
        +
Actualización de conocimiento
        +
Evaluación continua
        +
Human-in-the-Loop
```

---

# 23. Reflexión final

Responda brevemente.

### ¿Cuál fue la prueba más útil?

```text id="bfbfqn"
____________________________________________________
```

### ¿Qué error no habría detectado simplemente conversando con el chatbot?

```text id="6crbqp"
____________________________________________________

____________________________________________________
```

### ¿Cambiaría el modelo utilizado?

```text id="d0e3x7"
[ ] Sí

[ ] No

[ ] Necesito más evidencia
```

### ¿Por qué?

```text id="64gftd"
____________________________________________________

____________________________________________________
```

---

# Conclusión

El objetivo de evaluar una aplicación RAG no es demostrar que:

> **"La IA responde bien."**

El objetivo es obtener evidencia sobre:

```text id="5gwft8"
¿Recupera la información correcta?

¿Utiliza correctamente las fuentes?

¿Reconoce cuando no sabe?

¿Evita inventar información?

¿Responde consistentemente?

¿Podemos detectar cuándo falla?

¿Sabemos qué debe revisar una persona?
```

> **Una aplicación de IA confiable no es aquella que nunca falla, sino aquella cuyos límites pueden ser evaluados, detectados y controlados.**
