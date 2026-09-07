---
marp: false
theme: default
paginate: true
---

# IA y Aplicaciones

## Clase 1
### Fundamentos de Inteligencia Artificial, Redes Neuronales y Deep Learning

**Maestría en Ciencia de Datos, Inteligencia Artificial y Negocios**

Septiembre 2026

---

# Módulo: IA y Aplicaciones

## Ruta de aprendizaje

### Clase 1
Fundamentos de IA, Redes Neuronales y Deep Learning

### Clase 2
NLP moderno e IA Generativa

### Clase 3
Sistemas de Recomendación y Automatización Inteligente

### Clase 4
Aplicaciones sectoriales y Proyecto Integrador

---

# Pregunta inicial

> ## ¿Dónde tiene sentido utilizar Inteligencia Artificial?

No comenzamos preguntando:

> "¿Qué herramienta de IA utilizaremos?"

Comenzamos preguntando:

> **"¿Qué problema queremos resolver?"**

---

# Objetivos de la Clase 1

Al finalizar la sesión podremos:

- Comprender el panorama general de la IA.
- Diferenciar IA, Machine Learning y Deep Learning.
- Comprender los fundamentos de las redes neuronales.
- Reconocer aplicaciones de Deep Learning.
- Analizar cuándo utilizar IA.
- Identificar oportunidades y limitaciones de aplicación.

---

# El mapa general de la IA

```text
                 INTELIGENCIA ARTIFICIAL
                           │
              ┌────────────┴────────────┐
              │                         │
       IA basada en reglas        Machine Learning
                                        │
                              ┌─────────┴─────────┐
                              │                   │
                       Métodos clásicos       Deep Learning
                                                  │
                                      ┌───────────┴───────────┐
                                      │                       │
                                    NLP              Visión Artificial
                                      │
                               IA Generativa
                                      │
                                    LLMs
```

---

# ¿Qué es Inteligencia Artificial?

La Inteligencia Artificial comprende sistemas capaces de realizar tareas asociadas con capacidades cognitivas como:

- Percibir.
- Clasificar.
- Predecir.
- Aprender.
- Generar.
- Razonar.
- Planificar.
- Interactuar mediante lenguaje.
- Apoyar decisiones.

---

# IA no es una sola tecnología

La Inteligencia Artificial es un conjunto de:

- Métodos.
- Modelos.
- Algoritmos.
- Arquitecturas.
- Sistemas.
- Aplicaciones.

Por eso:

> **ChatGPT no es sinónimo de Inteligencia Artificial.**

Es una aplicación basada en determinados modelos y tecnologías de IA.

---

# Tres niveles para entender la IA

## Inteligencia Artificial

Campo general.

↓

## Machine Learning

Modelos que aprenden patrones a partir de datos.

↓

## Deep Learning

Modelos basados principalmente en redes neuronales profundas.

---

# Machine Learning

En Machine Learning:

```text
DATOS
  ↓
ALGORITMO
  ↓
MODELO
  ↓
PREDICCIÓN / DECISIÓN
```

El sistema aprende relaciones y patrones a partir de ejemplos.

---

# Ejemplo

## Predicción de abandono de clientes

Datos disponibles:

- Antigüedad.
- Frecuencia de uso.
- Reclamos.
- Pagos.
- Consumo.
- Tipo de plan.

Pregunta:

> ¿Qué clientes tienen mayor probabilidad de abandonar?

---

# Machine Learning

## Aprendizaje supervisado

Tenemos ejemplos donde conocemos el resultado.

```text
ENTRADA + RESULTADO CONOCIDO
             ↓
          MODELO
             ↓
       APRENDIZAJE
```

Ejemplos:

- Fraude / no fraude.
- Abandona / no abandona.
- Spam / no spam.
- Cliente riesgoso / no riesgoso.

---

# Aprendizaje no supervisado

No conocemos previamente el resultado.

Buscamos:

- Patrones.
- Grupos.
- Estructuras.
- Comportamientos inusuales.

Ejemplo:

```text
CLIENTES
   ↓
ALGORITMO
   ↓
SEGMENTOS
```

---

# Deep Learning

Deep Learning utiliza redes neuronales con múltiples capas.

Su capacidad principal es:

> **Aprender representaciones complejas a partir de grandes cantidades de datos.**

Es especialmente relevante para:

- Imágenes.
- Audio.
- Lenguaje.
- Video.
- Datos complejos.

---

# ¿Por qué Deep Learning?

Porque muchos problemas son difíciles de resolver mediante reglas explícitas.

Por ejemplo:

> ¿Cómo programar todas las reglas posibles para reconocer un rostro?

Existen demasiadas variaciones:

- Iluminación.
- Ángulo.
- Expresión.
- Edad.
- Calidad de imagen.
- Oclusiones.

Una red neuronal puede aprender patrones directamente de los datos.

---

# Redes neuronales

Una red neuronal está inspirada conceptualmente en sistemas biológicos, pero:

> **No es una simulación exacta del cerebro humano.**

Es un modelo matemático compuesto por unidades conectadas que transforman información.

---

# Neurona artificial

Una neurona recibe entradas:

```text
x1
x2
x3
 │
 ▼
[ NEURONA ]
    │
    ▼
    y
```

La neurona combina las entradas y genera una salida.

---

# La idea matemática

De manera simplificada:

```text
z = w1x1 + w2x2 + ... + b
```

Luego:

```text
y = f(z)
```

Donde:

- **x** = entradas.
- **w** = pesos.
- **b** = sesgo.
- **f** = función de activación.

---

# ¿Qué representan los pesos?

Los pesos representan la importancia de las conexiones.

Ejemplo:

```text
Entrada A ── peso 0.8 ──┐
                        │
Entrada B ── peso 0.2 ──┼──► Resultado
                        │
Entrada C ── peso 0.5 ──┘
```

Durante el entrenamiento:

> Los pesos se ajustan para reducir el error.

---

# Función de activación

Una red neuronal necesita mecanismos no lineales.

De forma simplificada:

```text
Entrada
   ↓
Combinación matemática
   ↓
Función de activación
   ↓
Salida
```

Sin no linealidad:

> Una red profunda tendría capacidades muy limitadas.

---

# Arquitectura de una red neuronal

```text
ENTRADA          CAPAS OCULTAS          SALIDA

 x1   ● ───────► ● ───────► ●
 x2   ● ───────► ● ───────► ● ───► y
 x3   ● ───────► ● ───────► ●
 x4   ● ───────► ● ───────► ●
```

Las capas intermedias aprenden diferentes representaciones de los datos.

---

# Deep Learning = más profundidad

```text
Entrada
   ↓
Capa 1
   ↓
Capa 2
   ↓
Capa 3
   ↓
Capa ...
   ↓
Salida
```

La profundidad permite aprender representaciones progresivamente más complejas.

---

# Ejemplo: reconocimiento de imágenes

Una red puede aprender:

```text
Imagen
   ↓
Bordes
   ↓
Formas
   ↓
Partes
   ↓
Objetos
   ↓
Clasificación
```

Estas representaciones no son necesariamente programadas manualmente.

> Son aprendidas durante el entrenamiento.

---

# Entrenamiento

Durante el entrenamiento:

```text
DATOS
  ↓
MODELO
  ↓
PREDICCIÓN
  ↓
COMPARACIÓN CON LA RESPUESTA REAL
  ↓
ERROR
  ↓
AJUSTE DE PESOS
  ↺
```

El proceso se repite muchas veces.

---

# Aprender significa...

De forma simplificada:

> Encontrar una configuración de parámetros que permita al modelo producir buenos resultados.

Pero debemos distinguir:

### Memorizar datos

vs.

### Generalizar a nuevos datos

---

# Entrenamiento vs. inferencia

## Entrenamiento

El modelo aprende a partir de datos.

```text
DATOS HISTÓRICOS
       ↓
ENTRENAMIENTO
       ↓
MODELO
```

## Inferencia

El modelo utiliza lo aprendido.

```text
NUEVOS DATOS
       ↓
MODELO
       ↓
PREDICCIÓN
```

---

# El problema del overfitting

Un modelo puede funcionar muy bien con los datos de entrenamiento...

pero fallar con datos nuevos.

```text
Datos conocidos     → 98 %
Datos nuevos        → 62 %
```

Esto puede indicar:

> **Overfitting**

El objetivo no es memorizar.

El objetivo es generalizar.

---

# ¿Cuándo utilizar Deep Learning?

Deep Learning puede ser apropiado cuando:

- Los datos son complejos.
- Existen grandes cantidades de datos.
- Se trabaja con imágenes, audio o lenguaje.
- Las reglas explícitas son insuficientes.
- Se requiere aprender representaciones complejas.

---

# ¿Cuándo NO utilizar Deep Learning?

No es necesariamente la mejor alternativa cuando:

- Existen pocos datos.
- El problema puede resolverse con reglas simples.
- Un modelo tradicional ofrece resultados suficientes.
- La explicabilidad es crítica.
- El costo computacional es excesivo.
- No existe capacidad técnica para mantener el sistema.

> **Más complejo no significa mejor.**

---

# Principales aplicaciones de Deep Learning

## Visión Artificial

- Detección de objetos.
- Reconocimiento facial.
- Control de calidad.
- Diagnóstico por imágenes.

---

# Principales aplicaciones de Deep Learning

## Procesamiento de Lenguaje Natural

- Traducción.
- Clasificación de texto.
- Resumen.
- Asistentes conversacionales.
- Extracción de información.

---

# Principales aplicaciones de Deep Learning

## Audio

- Reconocimiento de voz.
- Síntesis de voz.
- Transcripción.
- Clasificación de sonidos.

---

# Principales aplicaciones de Deep Learning

## IA Generativa

- Texto.
- Imágenes.
- Audio.
- Código.
- Video.

Los modelos generativos modernos utilizan arquitecturas profundas.

---

# Deep Learning en el módulo

En las próximas clases veremos cómo Deep Learning es parte de:

```text
REDES NEURONALES
        ↓
DEEP LEARNING
        ↓
TRANSFORMERS
        ↓
LLMs
        ↓
IA GENERATIVA
        ↓
APLICACIONES
```

---

# La pregunta correcta

No es:

> "¿Podemos utilizar Deep Learning?"

La pregunta es:

> **¿Deep Learning aporta una ventaja real para este problema?**

---

# Problema → Tecnología

El enfoque profesional debe ser:

```text
PROBLEMA
   ↓
OBJETIVO
   ↓
DATOS
   ↓
DECISIÓN
   ↓
TÉCNICA
   ↓
MODELO
   ↓
APLICACIÓN
   ↓
VALOR
```

---

# La IA no siempre es necesaria

Ejemplo:

Una empresa necesita calcular una factura.

```text
Cantidad × Precio
```

¿Necesitamos una red neuronal?

Probablemente no.

Una solución determinística es:

- Más simple.
- Más barata.
- Más fácil de probar.
- Más explicable.

---

# ¿Cuándo puede tener sentido IA?

La IA resulta especialmente interesante cuando:

- Existe incertidumbre.
- Existen patrones complejos.
- Hay datos históricos.
- Se necesitan predicciones.
- Se trabaja con información no estructurada.
- El problema involucra lenguaje, imágenes o audio.
- Las reglas son difíciles de definir.
- Se necesita personalización.

---

# Automatización ≠ IA

## Automatización tradicional

```text
SI A
ENTONCES B
```

## Inteligencia Artificial

```text
DATOS
  ↓
MODELO
  ↓
PREDICCIÓN / GENERACIÓN
  ↓
DECISIÓN
```

---

# Ejemplo: atención al cliente

```text
CLIENTE
   ↓
SOLICITUD
   ↓
¿QUÉ TIPO DE PROBLEMA?
   ↓
RESPUESTA
```

Podemos utilizar:

### Reglas

Si contiene X → departamento A.

### IA

Analizar significado y contexto.

---

# Una oportunidad de IA

Debe responder al menos cinco preguntas:

## 1. Problema

¿Qué queremos mejorar?

## 2. Datos

¿Qué información tenemos?

## 3. Decisión

¿Qué queremos predecir, recomendar o automatizar?

## 4. Tecnología

¿Qué tipo de IA necesitamos?

## 5. Valor

¿Qué mejora esperamos obtener?

---

# Evaluar una solución de IA

No basta con preguntar:

> "¿El modelo funciona?"

Debemos evaluar:

### Técnica
¿Funciona correctamente?

### Negocio
¿Genera valor?

### Operación
¿Puede implementarse?

### Economía
¿Justifica el costo?

### Riesgo
¿Qué puede salir mal?

### Ética
¿Quién puede verse afectado?

---

# Caso

## Modelo de fraude

El modelo tiene:

**Accuracy = 98 %**

¿Es suficiente?

No necesariamente.

Debemos preguntar:

- ¿Cuántos fraudes detecta?
- ¿Cuántos clientes legítimos bloquea?
- ¿Cuál es el costo de un error?
- ¿Existen sesgos?
- ¿El modelo funciona con datos nuevos?
- ¿Puede utilizarse en producción?

---

# Actividad 1

# ¿Necesitamos IA?

Analizaremos diferentes escenarios organizacionales.

El objetivo es responder:

> **¿Realmente necesitamos Inteligencia Artificial?**

---

# Actividad 1 — Trabajo en grupos

Para cada escenario respondan:

1. ¿Cuál es el problema?
2. ¿Qué proceso se desea mejorar?
3. ¿Qué decisión debe tomarse?
4. ¿Qué datos están disponibles?
5. ¿Puede resolverse con reglas?
6. ¿Existe un patrón complejo?
7. ¿La IA está justificada?
8. ¿Qué enfoque sería adecuado?
9. ¿Qué riesgos existen?

---

# Clasificación

Utilicen una de tres categorías:

## 🟢 IA recomendada

Existe una oportunidad clara.

## 🟡 IA posible

Puede aportar valor, pero requiere mayor análisis.

## 🔴 IA innecesaria

Una solución tradicional puede resolver adecuadamente el problema.

---

# Algunos escenarios de análisis

- Automatización de facturación.
- Predicción de abandono.
- Clasificación de reclamos.
- Control de inventario.
- Mantenimiento predictivo.
- Generación de informes.
- Detección de transacciones inusuales.
- Asistente para políticas internas.

---

# Regla principal de la actividad

No se evaluará solamente:

> "¿La respuesta fue correcta?"

Se evaluará principalmente:

> **¿La decisión está bien argumentada?**

---

# Discusión

Cada grupo deberá seleccionar un escenario y defender:

1. Su decisión.
2. La tecnología propuesta.
3. Los datos necesarios.
4. Los beneficios.
5. Los riesgos.
6. Las limitaciones.

---

# Actividad 2

# Mapa de oportunidades de IA

Seleccionen una organización o sector.

Identifiquen:

- Procesos.
- Problemas.
- Decisiones.
- Datos.
- Posibles aplicaciones de IA.

---

# Ejemplo

## Empresa de Retail

```text
VENTAS
   │
   ├── Personalización
   │
   ├── Recomendaciones
   │
   └── Pronóstico de demanda

CLIENTES
   │
   ├── Segmentación
   │
   ├── Abandono
   │
   └── Atención inteligente

OPERACIONES
   │
   ├── Inventario
   │
   └── Optimización
```

---

# Identificar oportunidades

Para cada oportunidad:

```text
PROCESO
   ↓
PROBLEMA
   ↓
DECISIÓN
   ↓
DATOS
   ↓
TIPO DE IA
   ↓
VALOR
```

---

# Priorización

Evalúen cada oportunidad:

| Criterio | Escala |
|---|---|
| Impacto potencial | 1–5 |
| Disponibilidad de datos | 1–5 |
| Viabilidad técnica | 1–5 |
| Costo | 1–5 |
| Riesgo | 1–5 |
| Facilidad de implementación | 1–5 |

---

# Matriz de oportunidades

```text
                 IMPACTO
                    ↑
                    │
       ALTO         │       ★ PRIORIDAD
                    │
────────────────────┼──────────────────→
                    │
       BAJO         │
                    │
                VIABILIDAD
```

Buscamos oportunidades con:

> **Alto impacto + Alta viabilidad**

---

# Pregunta de discusión

> ¿La tecnología más avanzada siempre produce la mejor solución?

Considerar:

- Datos.
- Costo.
- Complejidad.
- Riesgo.
- Explicabilidad.
- Mantenimiento.
- Valor.

---

# Proyecto integrador

Durante el módulo construiremos una propuesta de aplicación de IA.

La propuesta evolucionará:

```text
CLASE 1
Problema + oportunidad
        ↓
CLASE 2
NLP / IA Generativa
        ↓
CLASE 3
Recomendación / Automatización
        ↓
CLASE 4
Aplicación sectorial + evaluación
```

---

# Para la próxima clase

Seleccionar o traer:

### Un problema organizacional

Debe incluir:

- Organización o sector.
- Problema.
- Proceso afectado.
- Decisión que se busca mejorar.
- Datos disponibles.
- Posible aplicación de IA.

---

# Próxima clase

## NLP moderno e IA Generativa

Veremos:

- Procesamiento moderno del lenguaje.
- Embeddings.
- Transformers.
- LLMs.
- ChatGPT.
- Copilots.
- RAG.
- Aplicaciones empresariales.

---

# Idea clave

> **La IA no es el objetivo.**

La IA es un medio para:

- Resolver problemas.
- Mejorar decisiones.
- Personalizar servicios.
- Automatizar procesos.
- Generar conocimiento.
- Crear valor.

---

# Pregunta final

> ## Si una organización te pide:
>
> ### "Queremos implementar IA"
>
> ¿Qué preguntas deberías hacer antes de seleccionar una tecnología?

---

# Cierre

## De la tecnología al valor

```text
TECNOLOGÍA
    ↓
no es suficiente
```

Debemos conectar:

```text
PROBLEMA
   ↓
DATOS
   ↓
MODELO
   ↓
APLICACIÓN
   ↓
DECISIÓN
   ↓
VALOR
```

# Fin de la Clase 1
