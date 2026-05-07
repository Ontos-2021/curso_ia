# Material teorico - Sesion 3: Prompting y chat con asistentes

![Portada de la sesion 3 sobre prompting y chat con asistentes](assets/portada-material-teorico-sesion-3-prompting-y-chat-con-asistentes.png)

## Proposito de la sesion

Esta tercera sesion tiene una funcion decisiva: convertir el uso de IA en una habilidad deliberada.

En las sesiones anteriores entendiste que un modelo trabaja con tokens, contexto, arquitectura, entrenamiento e inferencia. Ahora toca pasar de la comprension del sistema a la calidad de la interaccion.

La pregunta central ya no es solo que es un modelo, sino como darle instrucciones para que trabaje mejor.

En esta sesion vas a construir una base practica sobre estos conceptos:

- Que es prompting en terminos serios.
- Por que un buen prompt no es poesia, sino especificacion util.
- Como estructurar instrucciones con rol, objetivo, contexto, restricciones y formato.
- Que diferencia hay entre zero-shot y few-shot.
- Como iterar un prompt sin improvisar.
- Como reducir respuestas vagas, alucinaciones y salidas poco utiles.
- Como pedir resultados que realmente sirvan para pensar, decidir o construir.

La meta no es aprender trucos aislados. La meta es desarrollar criterio para conversar con asistentes de manera mas precisa, productiva y confiable.

## Por que esta sesion importa

Mucha gente usa IA como si fuera una ruleta elegante: escribe algo rapido, recibe una respuesta, cruza los dedos y espera que salga bien.

Eso no es una metodologia. Eso es improvisacion.

Cuando una persona aprende prompting con criterio, cambia por completo su forma de trabajar:

- Pide mejor.
- Evalua mejor.
- Itera mejor.
- Detecta antes los huecos de contexto.
- Reduce ambiguedad innecesaria.
- Obtiene salidas mas faciles de usar dentro de un flujo real.

Un asistente no necesita palabras bonitas. Necesita instrucciones utiles.

## Resultado esperado de aprendizaje

Al terminar esta sesion, cada participante deberia poder explicar algo parecido a esto:

> Prompting no es escribirle "algo inteligente" a una IA, sino diseñar una entrada que le deje claro al sistema que tarea debe resolver, con que contexto debe trabajar, que restricciones debe respetar y en que formato debe responder. Un buen prompt reduce ambiguedad, mejora la calidad de salida y facilita la evaluacion posterior. La calidad del resultado depende tanto del modelo como de la calidad de la especificacion que recibe.

## Mapa de la sesion

| Bloque | Idea central | Pregunta que responde |
|---|---|---|
| Fundamentos | Que es prompting y que no es | Que significa pedir bien |
| Estructura | Rol, objetivo, contexto, restricciones y formato | Que piezas hacen un prompt util |
| Tecnicas | Zero-shot, few-shot e iteracion | Como mejorar una instruccion |
| Calidad | Claridad, verificabilidad y control de alucinaciones | Como obtener respuestas mas confiables |
| Uso real | Bibliotecas de prompts y trabajo con asistentes | Como llevar esto a producto y flujo de trabajo |

**Ruta sugerida de lectura:** Fundamentos -> Estructura -> Tecnicas -> Calidad -> Uso real

## 1. Que es prompting

Prompting es el acto de diseñar la entrada que recibe un modelo o asistente para orientar su salida.

Dicho de forma directa: es la forma en que conviertes una necesidad humana en una instruccion operable para un sistema probabilistico.

Eso significa que un prompt no es solo una frase suelta. Puede incluir:

- Una tarea.
- Un objetivo.
- Contexto.
- Restricciones.
- Ejemplos.
- Un formato esperado.
- Criterios de calidad.

### Idea clave

Prompting no es adornar la pregunta. Es diseñar una especificacion de trabajo.

## 2. Lo que un prompt no es

Hay varios errores comunes al aprender prompting.

| Error | Que suele pasar |
|---|---|
| Escribir algo muy breve y esperar precision maxima | La respuesta sale generica o ambigua |
| Pensar que mas texto siempre es mejor | A veces solo agregas ruido |
| Usar lenguaje dramatico o inflado | No mejora la estructura del problema |
| Pedir muchas cosas a la vez sin ordenar prioridades | El modelo mezcla objetivos |
| No definir formato de salida | La respuesta sale poco usable |

### Idea clave

Un prompt no mejora por sonar sofisticado. Mejora cuando reduce ambiguedad y organiza mejor la tarea.

## 3. La diferencia entre pedir y especificar

Mira estos dos casos:

```text
Caso A: Hazme un plan de marketing.
```

```text
Caso B: Diseña un plan de marketing de 30 dias para una tienda online de ropa deportiva. El objetivo es aumentar conversion en Instagram y email. Presupuesto bajo. Publico: mujeres de 20 a 35 años. Formato: tabla semanal con objetivo, accion, canal y metrica.
```

El segundo prompt no es mejor porque sea mas largo. Es mejor porque especifica mejor el trabajo.

### Comparacion util

| Prompt debil | Prompt fuerte |
|---|---|
| Formula un deseo | Formula una tarea concreta |
| Deja huecos clave | Reduce incertidumbre |
| Dificulta evaluar la salida | Facilita evaluar la salida |
| Obliga al modelo a improvisar demasiado | Ayuda al modelo a priorizar |

### Idea clave

La diferencia entre pedir y especificar es una de las bases de todo el curso.

## 4. Las cinco piezas de un prompt robusto

Una estructura muy util para principiantes es esta:

| Pieza | Funcion | Ejemplo |
|---|---|---|
| Rol | Define desde que perspectiva debe responder | Actua como consultor de producto |
| Objetivo | Explica que debe lograr | Diseña un plan de 4 semanas |
| Contexto | Aporta informacion relevante | Es para principiantes con poco presupuesto |
| Restricciones | Marca limites y condiciones | No uses jerga innecesaria |
| Formato | Define como debe entregar la respuesta | Responde en tabla con columnas fijas |

### Plantilla base

```text
Actua como [rol].

Objetivo:
[que debe lograr]

Contexto:
- [dato 1]
- [dato 2]
- [dato 3]

Restricciones:
- [limite 1]
- [limite 2]

Formato de salida:
[estructura esperada]
```

### Idea clave

No siempre necesitas las cinco piezas, pero cuanto mas ambigua sea la tarea, mas te conviene usarlas.

## 5. Rol: para que sirve y cuando sobra

Definir un rol puede ser util porque orienta el tono, la profundidad y el tipo de respuesta.

Ejemplos:

- Actua como profesor para principiantes.
- Actua como analista de producto.
- Actua como editor de textos claros.
- Actua como desarrollador senior de Python.

Pero hay un matiz importante.

### Cuando el rol ayuda

- Cuando cambia el punto de vista esperado.
- Cuando afecta tono o nivel tecnico.
- Cuando aclara tipo de salida.

### Cuando el rol no arregla nada

- Cuando la tarea sigue mal definida.
- Cuando falta contexto basico.
- Cuando no hay formato de salida.

### Idea clave

El rol puede mejorar una respuesta, pero no compensa una tarea mal planteada.

## 6. Objetivo: la parte mas importante del prompt

Si el objetivo es vago, casi todo lo demas tambalea.

Un buen objetivo responde, al menos, a estas preguntas:

- Que quieres que haga el modelo.
- Para que lo quieres.
- Que aspecto de la tarea importa mas.

### Ejemplos

| Objetivo debil | Objetivo fuerte |
|---|---|
| Mejora esto | Reescribe este texto para que sea mas claro y breve |
| Ayudame con IA | Diseña un plan de estudio de 6 semanas para aprender IA aplicada |
| Haz codigo | Escribe una funcion en Python que valide emails y agregue tests |

### Idea clave

Si no puedes definir el objetivo con claridad, el modelo tampoco va a resolverlo con claridad.

## 7. Contexto: la materia prima de una buena respuesta

El contexto le da al modelo informacion que no puede adivinar con seguridad.

Puede incluir:

- Nivel de conocimiento del usuario.
- Tipo de audiencia.
- Dominio del problema.
- Datos del negocio.
- Restricciones tecnicas.
- Documentos relevantes.
- Historial previo.

### Ejemplo practico

```text
Quiero aprender IA.
```

Comparalo con:

```text
Quiero aprender IA para construir aplicaciones utiles.
Soy principiante.
Tengo 2 horas al dia.
Quiero llegar a un prototipo desplegado en 8 semanas.
```

El segundo prompt le quita al modelo muchas decisiones innecesarias.

### Idea clave

Un mal prompt muchas veces no falla por mala redaccion, sino por contexto insuficiente.

## 8. Restricciones: el arte de poner limites utiles

Las restricciones le dicen al modelo por donde no debe ir.

Ejemplos utiles:

- No uses jerga tecnica innecesaria.
- No inventes datos que no esten en el texto.
- Limita la respuesta a 10 puntos.
- Si falta informacion, dilo explicitamente.
- No propongas herramientas de pago.

### Por que importan

Sin restricciones, el modelo tiende a rellenar huecos, expandirse de mas o asumir cosas que nadie pidio.

### Idea clave

Las restricciones no empobrecen el prompt. Lo vuelven mas controlable.

## 9. Formato de salida: pedir respuestas usables

Mucha gente recibe respuestas mediocres no porque el modelo falle, sino porque nunca definio como queria usarlas.

Puedes pedir formatos como:

- Tabla.
- Lista priorizada.
- JSON.
- Checklist.
- Plan por etapas.
- Comparativa con pros y contras.
- Respuesta breve con subtitulos.

### Ejemplo

```text
Formato de salida:
- Tabla con columnas: problema, impacto, solucion, prioridad.
```

### Idea clave

Un buen formato no solo mejora la lectura. Mejora la capacidad de revisar, copiar, programar o integrar la salida en un flujo posterior.

## 10. Zero-shot y few-shot

Estas dos tecnicas son fundamentales.

| Tecnica | Que significa |
|---|---|
| Zero-shot | Pides la tarea sin dar ejemplos |
| Few-shot | Das uno o varios ejemplos para orientar el patron esperado |

### Cuando zero-shot suele bastar

- Tareas simples.
- Formatos conocidos.
- Explicaciones generales.
- Clasificaciones faciles.

### Cuando few-shot suele ayudar mucho

- Estilos especificos.
- Clasificaciones ambiguas.
- Formatos estrictos.
- Extracciones delicadas.
- Tareas con muchos matices.

### Mini ejemplo

```text
Clasifica cada mensaje como soporte, venta o facturacion.

Ejemplos:
- "No puedo entrar a mi cuenta" -> soporte
- "Quiero cambiar mi plan" -> venta
- "No me llego la factura" -> facturacion
```

### Idea clave

Few-shot no es decorar el prompt con ejemplos. Es enseñar el patron que quieres que el modelo imite.

## 11. Prompting iterativo

Esperar el prompt perfecto al primer intento es una mala estrategia.

Trabajar bien con asistentes implica iterar.

### Ciclo recomendado

1. Escribe una primera version clara.
2. Observa que fallo.
3. Identifica si falto objetivo, contexto, restriccion o formato.
4. Corrige solo esa pieza.
5. Vuelve a probar.

**Ciclo basico:** prompt inicial -> salida -> diagnostico -> ajuste -> nueva salida

### Error comun

Cambiar cinco cosas a la vez y luego no saber que mejoro realmente.

### Idea clave

Iterar bien no es reescribirlo todo cada vez. Es ajustar variables concretas.

## 12. Como diagnosticar un prompt que salio mal

Cuando una respuesta no sirve, conviene preguntarse:

- La tarea estaba clara.
- El objetivo estaba bien definido.
- Faltaba contexto clave.
- Habia demasiadas cosas a la vez.
- El formato estaba especificado.
- Pedi algo que el modelo no podia verificar.

### Tabla de diagnostico

| Problema en la salida | Posible causa en el prompt |
|---|---|
| Muy generica | Falta de contexto |
| Muy larga o desordenada | Falta de restricciones o formato |
| Incorrecta o inventada | Tarea no verificable o contexto insuficiente |
| Poco accionable | Objetivo mal definido |
| Mezcla prioridades | Prompt con demasiadas tareas simultaneas |

### Idea clave

Un prompt malo no se corrige solo con "hazlo mejor". Se corrige identificando la causa del fallo.

## 13. Como reducir alucinaciones

No existe una forma absoluta de eliminar alucinaciones, pero si hay formas de reducirlas.

### Estrategias utiles

- Pide que el modelo distinga entre hechos y suposiciones.
- Pide que diga cuando falta informacion.
- Dale documentos concretos o contexto verificable.
- Limita el alcance de la tarea.
- Pide pasos de razonamiento visibles cuando aporten claridad.
- Pide citas o referencias cuando el caso lo requiera.

### Ejemplo

```text
Si no encuentras la informacion en el texto, dilo explicitamente y no inventes una respuesta.
```

### Idea clave

El modelo inventa menos cuando le dejas menos huecos y le permites admitir incertidumbre.

## 14. Como pedir respuestas mas utiles

Una respuesta util no siempre es la mas larga ni la mas brillante. Es la que mejor sirve para la tarea real.

### Preguntas utiles al diseñar un prompt

- Quiero una idea, un plan, una decision o una salida estructurada.
- La quiero para leer, para ejecutar o para integrar en otra herramienta.
- Necesito amplitud o precision.
- Quiero exploracion o quiero cierre.

### Ejemplo comparativo

| Necesidad real | Prompt mejor orientado |
|---|---|
| Quiero priorizar tareas | Devuelveme una tabla con prioridad, impacto y esfuerzo |
| Quiero decidir entre opciones | Compara tres opciones con pros, contras y recomendacion final |
| Quiero empezar rapido | Dame una primera version minima viable, no una solucion completa |

### Idea clave

La mejor respuesta no es la mas impresionante. Es la mas util para la siguiente accion.

## 15. Chat con asistentes: diferencia entre una pregunta suelta y una conversacion de trabajo

Trabajar con un asistente no es lo mismo que lanzar prompts aislados.

En una conversacion de trabajo, el historial importa. El contexto acumulado importa. Las instrucciones anteriores importan.

### Que cambia en chat

- Puedes iterar sobre una misma tarea.
- Puedes corregir sin reiniciar desde cero.
- Puedes construir contexto progresivamente.
- Puedes refinar tono, formato y profundidad.

### Riesgo comun

Si acumulas demasiado ruido en la conversacion, el asistente tambien puede degradarse.

### Idea clave

Un chat no es una bolsa infinita de contexto. Es una herramienta poderosa, pero necesita orden.

## 16. Cuando conviene reiniciar una conversacion

A veces seguir en el mismo chat ayuda. A veces perjudica.

Conviene reiniciar cuando:

- La tarea cambio por completo.
- El historial ya esta contaminado con supuestos incorrectos.
- El modelo arrastra un formato que ya no quieres.
- El contexto previo mete mas ruido que ayuda.

### Regla practica

Si sientes que estas corrigiendo al asistente mas de lo que avanzas, puede que el problema ya no sea el prompt, sino el estado de la conversacion.

## 17. Prompting para planificacion, creatividad y codigo

No todas las tareas se piden igual.

### A. Planificacion

Conviene pedir:

- Objetivo claro.
- Horizonte de tiempo.
- Restricciones reales.
- Entregables.
- Formato estructurado.

### B. Creatividad

Conviene pedir:

- Tono.
- Referencias de estilo.
- Criterios de calidad.
- Variantes multiples.
- Limites claros para evitar dispersion.

### C. Codigo

Conviene pedir:

- Lenguaje exacto.
- Input y output esperados.
- Restricciones tecnicas.
- Casos borde.
- Tests o ejemplos de uso.

### Idea clave

Un mismo modelo puede servir para muchas tareas, pero cada tipo de tarea necesita una especificacion distinta.

## 18. Ejemplos guiados

Los siguientes ejemplos muestran como cambia la calidad de un prompt cuando mejora su estructura.

### Ejemplo 1: plan vago versus plan util

```text
Hazme un plan para aprender IA.
```

Comparalo con:

```text
Actua como mentor de IA aplicada.

Objetivo:
Diseñar un plan de 8 semanas para aprender IA con foco en construir aplicaciones utiles.

Contexto:
- Nivel principiante.
- 2 horas al dia.
- Objetivo final: construir y desplegar un prototipo simple.

Restricciones:
- No uses matematicas avanzadas.
- Prioriza practica sobre teoria.

Formato de salida:
- Tabla por semana con objetivo, practica y entregable.
```

Para pensar:

- Que informacion aporta la segunda version.
- Que hace mas facil evaluar la calidad de la salida.
- Que parte de la mejora viene del formato y cual del contexto.

### Ejemplo 2: pedir una mejora de texto

```text
Mejora este texto.
```

Comparalo con:

```text
Reescribe este texto para una landing page.

Objetivo:
Hacerlo mas claro, mas breve y mas persuasivo.

Contexto:
- Audiencia: pequenos negocios.
- Tono: profesional y directo.

Restricciones:
- Maximo 120 palabras.
- No uses frases vacias ni humo.

Formato de salida:
- Devuelveme la version final y debajo una lista con 3 cambios clave.
```

Para pensar:

- Que cambia cuando defines audiencia y tono.
- Por que pedir cambios clave ayuda a revisar la respuesta.

### Ejemplo 3: pedir codigo util

```text
Haz una funcion en Python.
```

Comparalo con:

```text
Escribe una funcion en Python llamada validate_email.

Objetivo:
Validar si un email tiene un formato basico correcto.

Restricciones:
- No uses librerias externas.
- Devuelve True o False.
- Incluye manejo de casos borde simples.

Formato de salida:
- Primero la funcion.
- Luego 5 ejemplos de prueba.
- Luego una breve explicacion de limitaciones.
```

Para pensar:

- Que errores evita el segundo prompt.
- Que hace mas reutilizable la salida.

## 19. Actividad practica de la sesion

### Actividad: reparar prompts defectuosos

Toma tres prompts pobres y reescribelos hasta volverlos utiles.

Puedes usar ejemplos como estos:

- Hazme una estrategia.
- Explica Docker.
- Crea un texto para vender mi producto.
- Ayudame con este error.
- Haz un plan para mi negocio.

Para cada uno, crea:

1. Una version minima mejorada.
2. Una version robusta con rol, objetivo, contexto, restricciones y formato.
3. Una breve explicacion de por que mejora.

### Segunda parte: biblioteca de prompts utiles

Construye una pequena biblioteca personal con al menos un prompt para cada categoria:

- Planificacion.
- Escritura.
- Analisis.
- Codigo.
- Aprendizaje.

### Entregable de la actividad

Al terminar, entrega:

- Tres prompts reparados con su version anterior y posterior.
- Una biblioteca minima de 5 prompts utiles.
- Una nota breve explicando que patrones te funcionaron mejor.

Un buen entregable no solo muestra prompts mas largos. Muestra prompts mejor pensados.

## 20. Mini evaluacion de comprension

Responder en 3 a 5 lineas cada pregunta:

1. Que diferencia hay entre pedir y especificar.
2. Para que sirve definir rol, contexto y formato.
3. Cuando conviene usar few-shot.
4. Como puede reducirse el riesgo de alucinacion.
5. Por que un chat largo no siempre mejora la calidad de una respuesta.

La idea no es repetir recetas de memoria, sino demostrar criterio al diseñar instrucciones.

## 21. Glosario esencial

| Termino | Definicion simple |
|---|---|
| Prompt | Entrada que orienta el comportamiento del modelo |
| Prompting | Diseño deliberado de instrucciones para obtener una salida util |
| Rol | Perspectiva o perfil desde el que debe responder el asistente |
| Contexto | Informacion relevante para resolver mejor la tarea |
| Restriccion | Limite o condicion que la respuesta debe respetar |
| Formato de salida | Estructura esperada para la respuesta |
| Zero-shot | Pedir una tarea sin ejemplos previos |
| Few-shot | Pedir una tarea mostrando uno o varios ejemplos |
| Alucinacion | Respuesta inventada o injustificada presentada con seguridad |
| Iteracion | Proceso de mejorar un prompt a partir de la salida obtenida |
| Asistente | Producto o interfaz que organiza la interaccion con el modelo |

## 22. Ideas para recordar

- Un buen prompt no impresiona; orienta.
- Un prompt robusto reduce ambiguedad y mejora la evaluacion.
- Mas texto no siempre significa mejor contexto.
- El formato de salida importa tanto como la tarea.
- Few-shot sirve para enseñar un patron, no para adornar la entrada.
- Iterar bien es ajustar variables concretas, no reescribir todo a ciegas.
- Una respuesta elegante no siempre es una respuesta util.

## 23. Cierre conceptual

La gran leccion de esta sesion es que trabajar con asistentes no consiste en "hablar bonito" con la IA. Consiste en convertir una necesidad difusa en una instruccion clara, evaluable y util.

Un buen prompt no sustituye el pensamiento. Lo obliga a ordenarse.

Cuando aprendes a definir objetivo, contexto, restricciones y formato, dejas de pedir respuestas por intuicion y empiezas a diseñar interacciones de trabajo. Ese cambio es enorme, porque conecta directamente con todo lo que viene despues: productos con IA, APIs, agentes, herramientas, automatizacion y desarrollo.

Ese es el verdadero objetivo de la sesion 3: que dejes de preguntarte solo "que puedo pedirle al modelo" y empieces a preguntarte tambien "como debo estructurar esta tarea para obtener una salida realmente util".
