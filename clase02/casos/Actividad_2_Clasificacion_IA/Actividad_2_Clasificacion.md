# Actividad 2 — Clasificación inteligente de documentos

**Tiempo:** 25 minutos  
**Modalidad:** Grupos de 2–4 participantes

## Situación

Una organización recibe diariamente documentos y solicitudes que deben ser clasificados antes de enviarlos al área correspondiente.

El objetivo es experimentar si un LLM puede realizar esta tarea de forma consistente y qué controles serían necesarios antes de automatizarla.

## Objetivo

Utilizar un LLM para **clasificar documentos, determinar su prioridad y proponer una acción**, verificando posteriormente la calidad de las decisiones.

## Instrucciones

1. Seleccionen uno de los tres conjuntos de documentos.
2. Revisen los documentos y definan las categorías que utilizarán.
3. Diseñen un prompt que solicite:
   - categoría;
   - prioridad;
   - justificación breve;
   - acción recomendada.
4. Ejecuten el análisis sobre todos los documentos.
5. Revisen manualmente los resultados.
6. Identifiquen al menos **dos clasificaciones discutibles o incorrectas**.
7. Modifiquen el prompt para mejorar la consistencia y repitan el análisis.

## Formato sugerido

```text
Documento: DOC-01
Categoría:
Prioridad: Alta / Media / Baja
Justificación:
Acción recomendada:
```

## Entregable

- Categorías definidas.
- Prompt utilizado.
- Resultado de la clasificación.
- Dos errores o casos discutibles.
- Versión mejorada del prompt.
- Resultado final.

## Pregunta de cierre

> ¿En qué condiciones permitirían que esta clasificación se ejecute automáticamente y cuándo exigirían revisión humana?
