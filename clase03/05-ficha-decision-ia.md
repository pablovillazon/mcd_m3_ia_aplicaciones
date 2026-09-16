# Ficha de Decisión de IA — MVP

**Programa:** Maestría en Ciencia de Datos, Inteligencia Artificial y Negocios
**Módulo:** IA y Aplicaciones
**Clase 3:** Taller de Aplicaciones de Inteligencia Artificial

**Nombre / Grupo:** ____________________________________________

**Nombre del MVP:** ____________________________________________

---

# 1. Problema

## ¿Qué problema queremos resolver?

Describa el problema en máximo 3 líneas.

```text id="k99y5s"
Actualmente:

____________________________________________________

____________________________________________________
```

## ¿Quién tiene este problema?

```text id="2f6zvo"
Usuario / área:

____________________________________________________
```

---

# 2. Valor esperado

¿Qué mejora esperamos obtener?

Marque las opciones correspondientes:

* [ ] Reducir tiempo
* [ ] Reducir costos
* [ ] Automatizar trabajo repetitivo
* [ ] Facilitar acceso al conocimiento
* [ ] Mejorar consistencia de respuestas
* [ ] Apoyar decisiones
* [ ] Mejorar atención al usuario
* [ ] Reducir errores
* [ ] Otro: ______________________________

## Explique brevemente

```text id="rsguvc"
____________________________________________________

____________________________________________________
```

---

# 3. ¿Por qué utilizar IA?

Explique por qué este problema se beneficiaría de Inteligencia Artificial en lugar de resolverse únicamente mediante:

* búsqueda tradicional;
* reglas;
* formularios;
* base de datos;
* automatización convencional.

```text id="g4gnpu"
Utilizamos IA porque:

____________________________________________________

____________________________________________________
```

---

# 4. ¿Por qué utilizar RAG?

Marque las características de su conocimiento:

* [ ] Información especializada
* [ ] Información propia de la organización
* [ ] Información que cambia con el tiempo
* [ ] Gran cantidad de documentos
* [ ] Información no estructurada
* [ ] Conocimiento que el LLM podría desconocer
* [ ] Necesidad de identificar fuentes
* [ ] Otro: ______________________________

## Justificación

```text id="3whuqu"
Utilizamos RAG porque:

____________________________________________________

____________________________________________________
```

---

# 5. Fuentes de conocimiento

¿Qué información utilizará la aplicación?

| Fuente | Tipo                    | Propia / Pública | ¿Actualizable? |
| ------ | ----------------------- | ---------------- | -------------- |
|        | PDF / DOCX / TXT / otro |                  |                |
|        |                         |                  |                |
|        |                         |                  |                |
|        |                         |                  |                |

Ejemplos:

* contratos;
* manuales;
* normativa;
* procedimientos;
* políticas;
* libros;
* informes;
* documentación técnica;
* preguntas frecuentes.

---

# 6. Privacidad de la información

Los documentos contienen:

* [ ] Información pública
* [ ] Información interna
* [ ] Información confidencial
* [ ] Datos personales
* [ ] Información sensible
* [ ] No aplica

## ¿Existe autorización para procesarlos?

* [ ] Sí
* [ ] No
* [ ] Debe verificarse

## Control propuesto

```text id="cltql6"
____________________________________________________

____________________________________________________
```

> Para el taller utilice documentos públicos, anonimizados, ficticios o información que esté autorizado a procesar.

---

# 7. Arquitectura propuesta

Complete los componentes utilizados.

```text id="gbvpf3"
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
____________________________
    │
    ▼
Vector Database
    │
    ▼
____________________________
    │
    ▼
Retriever / RAG
    │
    ▼
____________________________
    │
    ▼
LLM
    │
    ▼
____________________________
    │
    ▼
USUARIO
```

---

# 8. Selección del LLM

## Modelo

```text id="9d0wst"
LLM:

____________________________________________________

Proveedor:

____________________________________________________
```

## Modalidad

* [ ] Local
* [ ] Cloud

---

# 9. Justificación del LLM

Evalúe los criterios más importantes para su caso.

| Criterio            | Importancia         | Justificación |
| ------------------- | ------------------- | ------------- |
| Calidad             | Alta / Media / Baja |               |
| Privacidad          | Alta / Media / Baja |               |
| Costo               | Alta / Media / Baja |               |
| Latencia            | Alta / Media / Baja |               |
| Idioma              | Alta / Media / Baja |               |
| Ventana de contexto | Alta / Media / Baja |               |
| Hardware            | Alta / Media / Baja |               |
| Facilidad de uso    | Alta / Media / Baja |               |

## ¿Por qué seleccionó este modelo?

```text id="cwnc0m"
____________________________________________________

____________________________________________________

____________________________________________________
```

---

# 10. Modelo de Embeddings

```text id="c5u2ka"
Modelo:

____________________________________________________

Proveedor:

____________________________________________________
```

## ¿Qué función cumple?

```text id="kufljc"
____________________________________________________

____________________________________________________
```

---

# 11. ¿LLM y Embedding Model son lo mismo?

Explique brevemente la función de cada uno.

```text id="qfj3ym"
Embedding Model:

____________________________________________________


LLM:

____________________________________________________
```

---

# 12. Comportamiento del asistente

## ¿Qué debe hacer?

```text id="plzw7f"
____________________________________________________

____________________________________________________
```

## ¿Qué NO debe hacer?

```text id="dssg1g"
____________________________________________________

____________________________________________________
```

## ¿Qué debe hacer cuando no encuentra información?

```text id="86pwur"
____________________________________________________

____________________________________________________
```

---

# 13. Evaluación

Se ejecutarán cinco tipos de prueba.

| Test | Descripción                               | Resultado |
| ---- | ----------------------------------------- | --------- |
| T1   | Información explícita                     |           |
| T2   | Información distribuida en varias fuentes |           |
| T3   | Pregunta ambigua                          |           |
| T4   | Información inexistente                   |           |
| T5   | Consulta de riesgo                        |           |

---

# 14. Principal problema encontrado

Durante las pruebas, ¿cuál fue el resultado más problemático?

```text id="5kt26i"
____________________________________________________

____________________________________________________
```

## Posible causa

* [ ] Documento incorrecto
* [ ] Información faltante
* [ ] Chunk incorrecto
* [ ] Retrieval incorrecto
* [ ] Prompt / instrucciones
* [ ] LLM
* [ ] Pregunta ambigua
* [ ] Configuración
* [ ] Otra: ______________________________

---

# 15. Mejora realizada

## ¿Qué modificó?

```text id="irh0cy"
____________________________________________________

____________________________________________________
```

## ¿Mejoró el resultado?

* [ ] Sí
* [ ] Parcialmente
* [ ] No

## Evidencia

```text id="10pzoz"
Antes:

____________________________________________________


Después:

____________________________________________________
```

---

# 16. Nivel de automatización

Clasifique las principales acciones de la solución.

**A — Automatizable**
Puede ejecutarse automáticamente con bajo riesgo.

**H — Human-in-the-Loop**
La IA realiza el trabajo preliminar, pero una persona debe validar.

**P — Decisión Profesional**
La decisión debe permanecer bajo responsabilidad humana.

| Acción | A / H / P | Justificación |
| ------ | --------- | ------------- |
|        |           |               |
|        |           |               |
|        |           |               |

---

# 17. Riesgos

Seleccione los principales riesgos identificados.

* [ ] Alucinaciones
* [ ] Recuperación incorrecta
* [ ] Información incompleta
* [ ] Información desactualizada
* [ ] Privacidad
* [ ] Seguridad
* [ ] Sesgos
* [ ] Exceso de confianza del usuario
* [ ] Automatización incorrecta
* [ ] Costos
* [ ] Dependencia del proveedor
* [ ] Otro: ______________________________

## Riesgo principal

```text id="45dnzt"
____________________________________________________
```

## Control propuesto

```text id="p2n8d8"
____________________________________________________

____________________________________________________
```

---

# 18. Decisión humana

## ¿Qué NO permitiría que la IA decida automáticamente?

```text id="r4ifxo"
____________________________________________________

____________________________________________________
```

## ¿Por qué?

```text id="kndsf3"
____________________________________________________

____________________________________________________
```

---

# 19. Valor del MVP

Complete la comparación.

| Situación actual | Con el MVP |
| ---------------- | ---------- |
|                  |            |
|                  |            |
|                  |            |

## Principal valor generado

```text id="d2l0x6"
____________________________________________________

____________________________________________________
```

---

# 20. Decisión final

Después de construir y probar el MVP:

## ¿Continuaría desarrollando esta solución?

* [ ] Sí
* [ ] Sí, pero necesita cambios importantes
* [ ] Necesitamos más evidencia
* [ ] No

## Justifique

```text id="8zzx68"
____________________________________________________

____________________________________________________
```

---

# 21. De MVP a producción

¿Qué necesitaría agregar antes de utilizar esta aplicación realmente dentro de una organización?

Seleccione lo que corresponda:

* [ ] Autenticación
* [ ] Autorización
* [ ] Gestión de usuarios
* [ ] Protección de documentos
* [ ] Control de acceso por documento
* [ ] Monitoreo
* [ ] Logs
* [ ] Auditoría
* [ ] Evaluación continua
* [ ] Actualización del conocimiento
* [ ] Gestión de costos
* [ ] Alta disponibilidad
* [ ] Integración con otros sistemas
* [ ] Human-in-the-Loop
* [ ] Políticas de uso
* [ ] Otro: ______________________________

---

# 22. Resumen ejecutivo del MVP

Complete finalmente en máximo cinco líneas:

```text id="fyghz5"
Nuestro MVP utiliza ________________________________

para resolver _____________________________________

mediante __________________________________________

seleccionamos _____________________________________

porque ____________________________________________
```

---

# Pregunta final

> **¿La incorporación de IA realmente mejora este proceso o solamente agrega una nueva tecnología?**

Justifique su respuesta utilizando la evidencia obtenida durante el taller.

```text id="e91x8q"
____________________________________________________

____________________________________________________

____________________________________________________
```
