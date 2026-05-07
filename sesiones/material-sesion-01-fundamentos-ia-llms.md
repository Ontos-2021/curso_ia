# Material teorico - Sesion 1: Fundamentos de IA y LLMs

![Portada - Fundamentos de IA](../assets/portada-fundamentos-ia.png)

## Proposito de la sesion

Esta primera sesion tiene una funcion decisiva: construir el mapa mental que los estudiantes usaran durante todo el curso.

Antes de aprender prompting, agentes, APIs, Git, Docker o despliegue, necesitan entender que estan usando cuando hablan con una IA. No hace falta convertirlos en investigadores de machine learning, pero si deben salir con una comprension clara, precisa y practica de estos conceptos:

- Que es inteligencia artificial.
- Que es machine learning.
- Que es deep learning.
- Que es un LLM.
- Que es un token.
- Que significa que un modelo predice el siguiente token.
- Que es el contexto.
- Que diferencia hay entre modelo, chat, asistente y producto.

La meta no es simplificar hasta volverlo superficial. La meta es explicar lo complejo con elegancia, con claridad y con una sensacion real de descubrimiento.

## Por que esta sesion importa

Para muchas personas, la IA aparece primero como una experiencia sorprendente: uno escribe una pregunta y recibe una respuesta que parece inteligente, articulada y muchas veces util. Ese primer asombro es legitimo, pero si se queda ahi, el aprendizaje queda incompleto.

Esta sesion busca transformar el asombro en comprension.

Porque cuando una persona entiende que un modelo procesa tokens, trabaja con contexto y genera respuestas paso a paso, deja de ver a la IA como una caja negra misteriosa y empieza a verla como una herramienta poderosa que puede dirigir con mas criterio.

## Resultado esperado de aprendizaje

Al terminar esta sesion, cada participante deberia poder explicar, con sus propias palabras, algo parecido a esto:

> Un LLM es un modelo entrenado con grandes cantidades de texto para predecir secuencias de tokens. Cuando chateamos con una IA, no estamos hablando directamente con una conciencia ni con una base de datos magica, sino con un sistema que recibe contexto, calcula probabilidades y genera una respuesta token por token. La calidad de la respuesta depende del modelo, del contexto, de las instrucciones, del producto que lo envuelve y de las herramientas disponibles.

## Mapa de la sesion

| Bloque | Idea central | Pregunta que responde |
|---|---|---|
| Panorama general | IA, machine learning y deep learning no son lo mismo | En que parte del mapa estamos |
| Lenguaje | Modelo de lenguaje, LLM y token | Que procesa realmente el sistema |
| Mecanica | Prediccion del siguiente token y contexto | Como genera una respuesta |
| Sistema real | Modelo, chat, asistente y producto | Que estamos usando cuando abrimos una app de IA |

**Ruta sugerida de lectura:** Panorama general -> Lenguaje -> Mecanica -> Sistema real

## 1. Que es inteligencia artificial

La inteligencia artificial es un campo amplio que busca crear sistemas capaces de realizar tareas que normalmente asociamos con inteligencia humana.

Dicho de una manera mas cercana: es el intento de lograr que una maquina pueda percibir, decidir, clasificar, recomendar, responder o generar algo de forma que, vista desde afuera, nos parezca inteligente.

Por ejemplo:

- Reconocer imagenes.
- Entender lenguaje.
- Traducir textos.
- Recomendar canciones.
- Detectar fraude.
- Generar codigo.
- Resumir documentos.
- Planificar tareas.

La IA no es una unica tecnologia. Es una familia de tecnicas, modelos y sistemas.

Una forma simple de verlo:

| Nivel | Que incluye | Idea practica |
|---|---|---|
| IA | Todo el campo | Sistemas que perciben, clasifican, recomiendan o generan |
| Machine learning | Subconjunto de IA | Aprende patrones desde datos |
| Deep learning | Subconjunto de machine learning | Usa redes neuronales con muchas capas |
| Modelos generativos | Subconjunto de deep learning | Generan texto, imagen, audio o codigo |
| LLMs | Tipo de modelo generativo | Trabajan especialmente bien con lenguaje |

### Idea clave

No toda IA es ChatGPT. ChatGPT es un producto construido sobre modelos de lenguaje. Los modelos de lenguaje son solo una parte del mundo de la IA.

## 2. Machine learning: aprender patrones desde datos

Machine learning significa que, en vez de programar todas las reglas a mano, entrenamos un sistema con datos para que aprenda patrones.

Esta idea es una de las grandes transiciones de la computacion moderna. Ya no siempre le decimos a la maquina exactamente que hacer en cada caso. Muchas veces le mostramos ejemplos, definimos un objetivo y dejamos que aprenda regularidades por si misma.

Ejemplo clasico:

En vez de escribir reglas como:

```text
Si el email contiene "ganaste dinero" y muchos signos de exclamacion, marcar como spam.
```

Podemos darle miles o millones de ejemplos de correos marcados como spam o no spam. El modelo aprende patrones estadisticos que le permiten clasificar correos nuevos.

### Comparacion simple

| Enfoque | Como funciona | Ejemplo |
|---|---|---|
| Programacion tradicional | Una persona escribe reglas explicitas | Si pasa X, hacer Y |
| Machine learning | El sistema aprende patrones desde ejemplos | Despues de ver muchos casos, predice si uno nuevo es spam |

### Idea clave

Machine learning no elimina la programacion. Cambia una parte del trabajo: en vez de escribir todas las reglas, diseñamos datos, objetivos, entrenamiento, evaluacion e integracion.

## 3. Deep learning: redes neuronales con muchas capas

Deep learning es una rama de machine learning basada en redes neuronales profundas.

Una red neuronal es un sistema matematico formado por muchas unidades conectadas que transforman datos de entrada en resultados de salida.

Para esta primera sesion no necesitamos entrar en matematicas. Lo importante es captar la intuicion general: la informacion entra, atraviesa varias transformaciones internas y sale convertida en una prediccion o respuesta.

| Etapa | Que ocurre |
|---|---|
| Entrada | El sistema recibe texto, imagen, audio o codigo |
| Capa 1 | Detecta rasgos simples o senales basicas |
| Capa 2 | Combina esos rasgos y encuentra relaciones |
| Capas profundas | Construye representaciones mas complejas |
| Salida | Entrega una clasificacion, una prediccion o una respuesta |

**Imagen mental:** Entrada -> Transformaciones internas -> Salida

En una aplicacion real, la entrada puede ser texto, imagen, audio o codigo. La salida puede ser una clasificacion, una prediccion, una respuesta, una imagen o una accion sugerida.

### Idea clave

Deep learning permite aprender patrones muy complejos, pero tambien hace que los modelos sean mas dificiles de interpretar. Sabemos entrenarlos y usarlos, pero no siempre podemos explicar cada decision interna paso a paso como si fuera una regla escrita por un humano.

## 4. Que es un modelo de lenguaje

Un modelo de lenguaje es un modelo entrenado para trabajar con lenguaje.

Su tarea central es aprender patrones en secuencias de texto.

No solo aprende palabras aisladas. Aprende relaciones entre palabras, entre frases, entre estilos, entre formatos, entre preguntas y respuestas, entre codigo y documentacion, entre una instruccion y la forma en que suele resolverse.

Por ejemplo, si ve esta frase:

```text
El cielo esta muy...
```

Puede estimar que algunas continuaciones son mas probables que otras:

| Posible siguiente palabra | Probabilidad aproximada |
|---|---:|
| azul | Alta |
| nublado | Alta |
| frio | Media |
| bicicleta | Baja |
| democracia | Baja |

Esto no significa que el modelo "sepa" como una persona. Significa que aprendio relaciones estadisticas y semanticas entre fragmentos de lenguaje.

## 5. Que es un LLM

LLM significa Large Language Model, o modelo de lenguaje grande.

Es un modelo de lenguaje entrenado con enormes cantidades de texto y con una arquitectura capaz de capturar relaciones complejas entre palabras, ideas, codigo, formatos, estilos y patrones de razonamiento.

La palabra grande no solo alude al volumen de datos. Tambien sugiere escala en capacidad, parametros, diversidad de tareas y alcance practico. Por eso un mismo modelo puede resumir un contrato, explicar una idea, escribir un email o ayudarte a programar.

Un LLM puede hacer muchas tareas porque muchas tareas pueden expresarse como transformaciones de lenguaje:

- Pregunta -> respuesta.
- Texto largo -> resumen.
- Idea vaga -> plan.
- Requisitos -> codigo.
- Error -> explicacion.
- Datos -> analisis.
- Instrucciones -> procedimiento.
- Conversacion -> siguiente respuesta.

### Mapa conceptual

| Fase | Que entra o sucede | Que sale |
|---|---|---|
| Recibe | Preguntas, codigo, documentos, instrucciones | Un contexto de trabajo |
| Procesa | Patrones, relaciones, formato, contexto | Una estimacion de la mejor continuacion |
| Produce | Texto token por token | Respuestas, resumenes, ideas, codigo |

**En una frase:** Entrada de lenguaje -> procesamiento probabilistico -> salida util

### Una analogia util

Un LLM puede imaginarse como un motor de continuacion inteligente.

No es simplemente autocompletar palabras. Es mucho mas potente que eso. Pero su mecanismo base sigue siendo generar una continuacion probable y util segun el contexto recibido.

Esa es una idea hermosa y poderosa a la vez: de un principio relativamente simple emerge un comportamiento que, a nuestra escala humana, puede parecer sorprendentemente sofisticado.

La diferencia es la escala:

- Un autocompletado comun predice frases cortas.
- Un LLM moderno puede sostener instrucciones, estilo, formato, ejemplos, codigo, razonamiento aparente y conversaciones largas.

## 6. Que es un token

Un token es una unidad de texto que el modelo procesa.

No siempre equivale a una palabra completa. Un token puede ser:

- Una palabra corta.
- Parte de una palabra.
- Un signo de puntuacion.
- Un espacio.
- Un fragmento de codigo.

Ejemplo conceptual:

```text
Texto: "Construir productos con IA"

Tokens aproximados:
["Constru", "ir", " productos", " con", " IA"]
```

El tokenizador exacto depende del modelo. Lo importante es entender que el modelo no ve el texto exactamente como nosotros. Primero lo convierte en tokens.

Flujo simplificado:

1. El usuario escribe texto.
2. El sistema lo divide en tokens.
3. El modelo procesa esos tokens como representaciones internas.
4. El modelo genera nuevos tokens.
5. El sistema convierte esos tokens en texto legible.

**Secuencia basica:** Texto humano -> tokenizacion -> modelo -> nuevos tokens -> texto generado

### Por que importan los tokens

Los tokens importan por tres razones:

- Costo: muchos proveedores cobran segun tokens de entrada y salida.
- Limite: los modelos tienen una ventana maxima de contexto.
- Rendimiento: mas contexto no siempre significa mejor respuesta; a veces significa mas ruido.

### Token de LLM versus API token

Esta confusion es comun y conviene eliminarla desde el inicio.

| Concepto | Significado |
|---|---|
| Token de LLM | Unidad de texto procesada por el modelo |
| API token o API key | Credencial usada para autenticarte frente a un servicio |

Un token de LLM es parte del lenguaje. Una API key es una llave de acceso.

## 7. Como responde un LLM: prediccion del siguiente token

Cuando un LLM genera una respuesta, no la escribe toda de una sola vez. La produce paso a paso.

Primero recibe un contexto. Luego calcula cual podria ser el siguiente token. Despues agrega ese token al contexto y vuelve a calcular el siguiente. Repite este proceso hasta completar la respuesta.

Secuencia real, sin magia:

1. Recibe el prompt y el contexto disponible.
2. Calcula que token podria venir despues.
3. Elige uno segun sus probabilidades y parametros de generacion.
4. Agrega ese token al texto ya producido.
5. Repite el ciclo hasta cerrar la respuesta.

**Ciclo base:** Contexto inicial -> siguiente token -> nuevo contexto -> siguiente token -> respuesta final

### Ejemplo simplificado

Entrada:

```text
Explica que es Docker en una frase:
```

El modelo podria generar:

```text
Docker
Docker es
Docker es una
Docker es una herramienta
Docker es una herramienta para
Docker es una herramienta para empaquetar
Docker es una herramienta para empaquetar aplicaciones...
```

Nosotros vemos una respuesta fluida. Internamente, se construye token por token.

Ese contraste entre lo que vemos y lo que realmente ocurre es una de las ideas mas fascinantes de esta sesion: por fuera parece una respuesta espontanea; por dentro, es una secuencia de decisiones probabilisticas muy rapidas.

### Punto importante

El modelo no "busca" una respuesta fija guardada en una tabla. Calcula probabilidades segun lo que aprendio durante entrenamiento y segun el contexto que recibe en ese momento.

## 8. Que es el contexto

El contexto es todo lo que el modelo recibe y puede usar para generar una respuesta.

Si hubiera que elegir una sola palabra para explicar por que una respuesta de IA sale bien o sale mal, esa palabra seria contexto.

Puede incluir:

- La pregunta del usuario.
- Mensajes anteriores de la conversacion.
- Instrucciones del sistema.
- Archivos adjuntos.
- Fragmentos de codigo.
- Resultados de herramientas.
- Reglas del producto.
- Ejemplos dados en el prompt.

| Parte del contexto | Ejemplo |
|---|---|
| Instrucciones del sistema | "Responde como profesor para principiantes" |
| Mensaje del usuario | La pregunta o tarea actual |
| Historial | Lo que ya se dijo antes en la conversacion |
| Archivos o codigo | PDFs, notas, snippets, repositorios |
| Resultados de herramientas | Busquedas, consultas, ejecucion de codigo |
| Reglas del producto | Limites, permisos, formato de salida |
| Ejemplos del prompt | Casos modelo que orientan la respuesta |

### Ventana de contexto

La ventana de contexto es la cantidad maxima de tokens que el modelo puede considerar en una interaccion.

Si la conversacion, los archivos o las instrucciones superan ese limite, el sistema debe recortar, resumir o seleccionar que informacion enviar.

### Analogias utiles

El contexto es como la mesa de trabajo del modelo.

Si en la mesa estan los documentos correctos, las instrucciones claras y los ejemplos relevantes, el modelo trabaja mejor.

Si la mesa esta llena de ruido, informacion contradictoria o faltan datos clave, el modelo improvisa mas.

Esta analogia vale oro para enseñar: un mal contexto no arruina solo una respuesta; arruina la calidad del pensamiento que el sistema puede desplegar.

### Idea clave

Un buen resultado depende tanto del modelo como del contexto. Muchas respuestas malas no ocurren porque el modelo sea inutil, sino porque el contexto era incompleto, ambiguo o mal seleccionado.

## 9. Contexto no es memoria permanente

Una confusion frecuente: pensar que si el modelo respondio algo una vez, entonces "lo aprendio".

En general, cuando interactuamos con un LLM mediante un producto, el modelo no modifica sus pesos ni se reentrena durante esa conversacion.

Lo que cambia es el contexto que el producto le entrega.

Regla practica:

| Factor | Influye en la respuesta actual | Comentario |
|---|---|---|
| Contexto temporal de esta interaccion | Si | Cambia de una consulta a otra y orienta la respuesta |
| Pesos del modelo ya entrenado | Si | Determinan lo que el modelo ya aprendio antes de usarse |
| Aprendizaje automatico en tiempo real dentro de cada chat | No | Eso no ocurre de forma normal en una conversacion comun |

### Distincion importante

| Concepto | Que significa |
|---|---|
| Entrenamiento | Proceso que modifica el modelo para que aprenda patrones |
| Inferencia | Uso del modelo ya entrenado para generar una respuesta |
| Contexto | Informacion temporal que el modelo recibe en una interaccion |
| Memoria de producto | Funcion agregada por una app para guardar datos y volver a usarlos |

El modelo base no aprende automaticamente de cada chat. Algunos productos pueden guardar memoria, pero eso es una capa del producto, no necesariamente un cambio en el modelo.

## 10. Modelo, chat, asistente y producto

Estos cuatro conceptos suelen mezclarse. Conviene separarlos desde el principio.

| Concepto | Explicacion simple | Ejemplo |
|---|---|---|
| Modelo | Sistema que procesa entrada y genera salida | GPT, Claude, Gemini, Llama |
| Chat | Interfaz conversacional para hablar con un modelo | Una ventana de conversacion |
| Asistente | Modelo con instrucciones, herramientas o comportamiento definido | Un asistente de codigo, soporte o escritura |
| Producto | Aplicacion completa construida alrededor del modelo | ChatGPT, Copilot, Cursor, una app propia |

### Mapa de capas

| Capa | Funcion | Ejemplos |
|---|---|---|
| Modelo | Genera la salida token por token | GPT, Claude, Gemini, Llama |
| API o motor de inferencia | Da acceso tecnico al modelo | API de OpenAI, Anthropic, Google |
| Chat o asistente | Organiza instrucciones, herramientas y contexto | Un asistente de codigo o de soporte |
| Producto | Suma interfaz, usuarios, historial, permisos y memoria | ChatGPT, Copilot, Cursor, una app propia |

**Capas del sistema:** Modelo -> API -> Asistente -> Producto

### Ejemplo concreto

ChatGPT no es solo un modelo.

Es un producto que puede incluir:

- Una interfaz conversacional.
- Historial.
- Proyectos.
- Archivos.
- Herramientas.
- Instrucciones.
- Memoria.
- Control de usuarios.
- Modelos diferentes segun la tarea.

El modelo es el motor. El producto es el vehiculo completo.

## 11. Que puede hacer muy bien un LLM

Los LLMs son especialmente fuertes en tareas de lenguaje y transformacion simbolica.

Cuando se los usa bien, tienen algo muy potente: convierten lenguaje en palanca de trabajo. Una idea borrosa puede transformarse en estructura. Un documento largo puede transformarse en claridad. Un problema tecnico puede transformarse en un primer camino de solucion.

Ejemplos:

- Resumir informacion.
- Reescribir textos.
- Generar ideas.
- Explicar conceptos.
- Traducir.
- Crear estructuras.
- Escribir borradores.
- Ayudar a programar.
- Analizar requisitos.
- Convertir formatos.
- Simular conversaciones.

### Patron general

Muchas tareas utiles se pueden expresar asi:

**Patron operativo:** Entrada desordenada + instrucciones claras + contexto relevante -> salida util

## 12. Donde fallan los LLMs

Un LLM puede ser muy potente y aun asi fallar.

Y esto no le quita interes; al contrario. Entender sus limites es lo que permite usarlo con madurez.

Errores comunes:

- Inventar informacion cuando no sabe.
- Responder con seguridad aunque este equivocado.
- Perder detalles en contextos largos.
- Ser sensible a instrucciones ambiguas.
- Confundir objetivos si hay informacion contradictoria.
- Generar codigo que parece correcto pero no corre.
- No distinguir bien entre hechos actuales y patrones aprendidos.

### Idea clave

Un LLM no debe tratarse como una fuente infalible de verdad. Debe tratarse como un motor de generacion y razonamiento asistido que necesita contexto, verificacion y criterio humano.

## 13. Tres modelos mentales para usar IA con criterio

### 1. El modelo como motor de prediccion

Sirve para recordar que genera respuestas calculando continuaciones probables, no accediendo a una verdad absoluta.

### 2. El modelo como colaborador junior muy rapido

Puede producir mucho, ayudar a pensar y acelerar tareas, pero necesita direccion, contexto y revision.

### 3. El modelo como parte de un sistema

En una app real, el modelo es solo una pieza. Tambien importan la interfaz, los datos, las herramientas, los permisos, los costos, los logs y el despliegue.

## 14. Ejemplos guiados

Los siguientes ejemplos muestran como cambia la calidad de una respuesta cuando cambia el contexto.

### Prompt 1: pobre en contexto

```text
Hazme un plan para estudiar IA.
```

Para pensar:

- La respuesta puede ser util, pero es generica.
- No sabe el nivel del estudiante.
- No sabe el objetivo.
- No sabe el tiempo disponible.
- No sabe si el foco es teoria, producto, automatizacion o codigo.

### Prompt 2: con contexto minimo

```text
Quiero aprender IA para construir aplicaciones utiles. Soy principiante, tengo 2 horas al dia durante 6 semanas y quiero terminar con un proyecto desplegado. Hazme un plan por semanas con objetivos, practica y entregables.
```

Para pensar:

- Que datos nuevos ayudaron al modelo.
- Que partes de la respuesta son mas accionables.
- Que informacion todavia podria faltar.

### Prompt 3: con rol, formato y restricciones

```text
Actua como profesor de IA aplicada para principiantes.

Objetivo: diseñar un plan de 6 semanas para que una persona construya una app simple con IA y la despliegue.

Contexto:
- Nivel inicial.
- 2 horas de estudio al dia.
- Interes principal: construir productos, no investigar matematicas avanzadas.
- Debe incluir prompting, APIs, variables de entorno, Git, Docker y deploy.

Formato de salida:
- Tabla por semana.
- Objetivo de la semana.
- Conceptos clave.
- Practica.
- Entregable.

Restriccion:
- No uses jerga innecesaria.
```

Para pensar:

- Como cambia la precision.
- Como cambia la estructura.
- Como cambia la facilidad para evaluar la respuesta.

## 15. Actividad practica de la sesion

### Actividad: mismo objetivo, distinto contexto

Elige una tarea simple, por ejemplo:

- Crear un plan de estudio.
- Diseñar una app sencilla.
- Escribir una descripcion de producto.
- Planificar una semana de trabajo.
- Explicar un concepto tecnico.

Luego pidela al asistente de tres formas:

1. Prompt vago.
2. Prompt con contexto.
3. Prompt con rol, contexto, restricciones y formato.

### Entregable de la actividad

Al terminar, responde:

- Que prompt produjo mejor resultado.
- Que informacion cambio mas la calidad de la respuesta.
- Que errores aparecieron.
- Que aprendieron sobre contexto.

Un buen entregable no solo muestra el mejor prompt. Tambien explica por que funciono mejor.

## 16. Mini evaluacion de comprension

Responder en 3 a 5 lineas cada pregunta:

La idea no es repetir definiciones de memoria, sino explicar con claridad y criterio.

1. Que es un LLM.
2. Que es un token.
3. Por que el contexto cambia la calidad de una respuesta.
4. Cual es la diferencia entre modelo y producto.
5. Por que no debemos confiar ciegamente en una respuesta generada por IA.

## 17. Glosario esencial

| Termino | Definicion simple |
|---|---|
| IA | Campo que busca crear sistemas capaces de realizar tareas asociadas con inteligencia |
| Machine learning | Tecnica donde un sistema aprende patrones desde datos |
| Deep learning | Rama de machine learning basada en redes neuronales profundas |
| Modelo | Sistema entrenado para transformar entradas en salidas |
| LLM | Modelo de lenguaje grande capaz de procesar y generar texto |
| Token | Unidad de texto procesada por el modelo |
| Contexto | Informacion que el modelo recibe para generar una respuesta |
| Ventana de contexto | Limite de tokens que el modelo puede considerar |
| Inferencia | Uso de un modelo entrenado para generar una respuesta |
| Prompt | Instruccion o entrada que se entrega al modelo |
| Chat | Interfaz conversacional para interactuar con un modelo |
| Asistente | Sistema con modelo, instrucciones y posiblemente herramientas |
| Producto | Aplicacion completa construida alrededor de uno o mas modelos |

## 18. Ideas para recordar

- Un LLM no responde desde magia; responde desde patrones, contexto y probabilidades.
- Un token no es una palabra exacta; es una unidad interna de texto.
- El contexto es la materia prima de una buena respuesta.
- ChatGPT no es solo un modelo; es un producto construido alrededor de modelos.
- Una respuesta convincente no siempre es una respuesta correcta.
- La IA potencia el trabajo cuando se combina con criterio humano.

## 19. Cierre conceptual

La primera gran leccion del curso es esta: trabajar bien con IA no consiste en encontrar el prompt perfecto, sino en entender el sistema.

Un modelo recibe contexto, procesa tokens y genera una respuesta. Un producto toma ese modelo y le agrega interfaz, memoria, archivos, herramientas, reglas, permisos y experiencia de usuario. Un buen constructor de productos con IA debe saber moverse entre ambos niveles: el nivel del modelo y el nivel del sistema.

Si los participantes entienden esto desde la primera sesion, todo lo que viene despues tiene una base mucho mas solida: prompting, APIs, agentes, MCP, Git, Docker y despliegue dejan de ser temas sueltos y empiezan a formar parte de un mismo flujo de construccion.

Ese es el verdadero objetivo de esta apertura: que la IA deje de sentirse como un truco impresionante y empiece a sentirse como un territorio que se puede comprender, habitar y construir.