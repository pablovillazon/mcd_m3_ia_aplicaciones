# Actividad 1 — Extracción y estructuración de información

**Tiempo:** 20 minutos  
**Modalidad:** Grupos de 2–4 participantes

## Situación

Las organizaciones reciben información en correos, solicitudes, contratos, reportes y otros documentos. Antes de utilizarla para análisis o decisiones, es necesario convertir parte de esa información en datos estructurados.

En esta actividad utilizaremos un LLM para realizar esa transformación.

## Objetivo

Experimentar cómo un modelo de lenguaje puede **extraer información relevante de texto libre y convertirla en datos estructurados**, verificando posteriormente la calidad del resultado.

## Instrucciones

1. Seleccionen **uno de los tres casos** proporcionados.
2. Lean el documento e identifiquen qué información sería útil extraer.
3. Diseñen un prompt indicando **qué campos debe identificar y en qué formato debe responder**.
4. Ejecuten el prompt con un LLM.
5. Comparen el resultado con el texto original.
6. Identifiquen al menos **dos errores, omisiones o ambigüedades**.
7. Mejoren el prompt y vuelvan a ejecutar el análisis.

## Formato sugerido

Soliciten una salida estructurada similar a:

```json
{
  "campo_1": "",
  "campo_2": "",
  "campo_3": "",
  "observaciones": ""
}
```

## Entregable

- Prompt inicial.
- Resultado inicial.
- Errores encontrados.
- Prompt mejorado.
- Resultado final.

## Pregunta de cierre

> ¿Confiarían directamente en los datos extraídos por la IA para alimentar un sistema o tomar una decisión? ¿Por qué?
