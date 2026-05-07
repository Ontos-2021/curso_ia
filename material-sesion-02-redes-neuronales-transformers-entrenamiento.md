# Material teorico - Sesion 2: Redes neuronales, transformers y entrenamiento

![Portada - Redes neuronales y transformers](assets/portada-sesion-02-redes-neuronales-transformers.png)

## Proposito de la sesion

Esta segunda sesion tiene una tarea muy concreta: abrir la caja negra sin volver la clase innecesariamente matematica.

En la sesion 1 los participantes entendieron que un LLM recibe contexto, procesa tokens y genera una respuesta. Ahora toca responder una pregunta mas profunda: como puede un sistema hacer eso de forma tan potente y, al mismo tiempo, tan imperfecta.

No hace falta convertir al grupo en especialistas de machine learning. Pero si deben salir con una comprension conceptual, ordenada y util de estos puntos:

- Que es una red neuronal.
- Que son pesos, parametros y aprendizaje.
- Que es un embedding.
- Que problema resuelve la atencion.
- Que es un transformer.
- Que significa entrenar un modelo.
- Cual es la diferencia entre pretraining, fine-tuning y RLHF.
- Cual es la diferencia entre entrenamiento e inferencia.
- Por que estos modelos tienen capacidades impresionantes y limites estructurales.

La meta no es memorizar terminologia. La meta es construir un modelo mental serio sobre como nacen estas herramientas.

## Por que esta sesion importa

Muchas personas usan modelos modernos como si fueran una especie de inteligencia difusa que simplemente "sabe" cosas. Ese error se paga caro.

Si no entiendes como se entrena un modelo, es facil creer que todo se resuelve con un prompt mejor. Si no entiendes que un modelo opera sobre representaciones numericas, es facil imaginar que "comprende" exactamente como un humano. Si no distingues entrenamiento de inferencia, es facil confundir una conversacion con aprendizaje real.

Esta sesion corrige esas intuiciones defectuosas.

Cuando una persona entiende, aunque sea a nivel conceptual, que hay embeddings, capas, atencion, perdida, ajuste de pesos y etapas de alineacion, deja de tratar al modelo como magia y empieza a tratarlo como tecnologia.

## Resultado esperado de aprendizaje

Al terminar esta sesion, cada participante deberia poder explicar algo parecido a esto:

> Un modelo moderno no responde porque "tenga ideas" como un humano, sino porque fue entrenado sobre muchisimos datos para convertir tokens en representaciones numericas, procesarlas a traves de una arquitectura como transformer y producir la siguiente salida mas probable. Durante el entrenamiento ajusta parametros para reducir error; durante la inferencia usa lo ya aprendido para responder. Su comportamiento final depende de la arquitectura, los datos, el objetivo de entrenamiento y las capas de alineacion aplicadas despues.

## Mapa de la sesion

| Bloque | Idea central | Pregunta que responde |
|---|---|---|
| Representaciones | Tokens, vectores y embeddings | Como pasa el lenguaje a un formato procesable |
| Arquitectura | Redes neuronales, atencion y transformers | Como se organiza internamente el modelo |
| Aprendizaje | Loss, ajuste de pesos y entrenamiento | Como mejora el sistema con datos |
| Alineacion | Pretraining, fine-tuning y RLHF | Como cambia su comportamiento segun la etapa |
| Uso real | Inferencia, costo, latencia y limites | Que ocurre cuando el modelo ya esta en produccion |

**Ruta sugerida de lectura:** Representaciones -> Arquitectura -> Aprendizaje -> Alineacion -> Uso real

## 1. Abrir la caja negra

En la sesion anterior dejamos una idea central: un modelo predice el siguiente token.

Esa frase es correcta, pero todavia esta incompleta.

Ahora necesitamos abrirla. Cuando decimos que un modelo predice el siguiente token, en realidad estamos diciendo que hace una larga cadena de transformaciones internas hasta llegar a una distribucion de probabilidades sobre posibles continuaciones.

Ruta general del sistema:

```text
Datos de entrenamiento -> tokenizacion -> embeddings -> capas del modelo -> probabilidades -> ajuste o respuesta
```

Y cuando ya esta en uso:

```text
Prompt -> tokenizacion -> embeddings -> capas transformer -> siguiente token -> respuesta
```

### Idea clave

No existe un salto magico entre texto y respuesta. Existe una cadena de representaciones, calculos y decisiones probabilisticas.

## 2. Que es una red neuronal

Una red neuronal es un sistema compuesto por muchas unidades matematicas conectadas entre si. Cada una recibe señales, las combina y produce una salida que alimenta a otras unidades.

La palabra "neuronal" puede confundir. No significa que el sistema funcione como un cerebro humano real en todos sus detalles. Es un nombre historico para una familia de modelos inspirados de forma muy abstracta en conexiones biologicas.

Lo importante para esta sesion es entender la intuicion:

- Entra informacion.
- Esa informacion atraviesa muchas transformaciones.
- Cada capa detecta o construye patrones.
- Al final aparece una prediccion o una salida.

| Elemento | Funcion conceptual |
|---|---|
| Entrada | Recibe datos, por ejemplo tokens o vectores |
| Pesos | Determinan cuanto influye cada señal |
| Capa | Agrupa muchas transformaciones del mismo nivel |
| Capas profundas | Combinan rasgos simples y producen representaciones mas complejas |
| Salida | Devuelve una prediccion, clasificacion o distribucion de probabilidad |

### Una analogia util

Puedes imaginar una red neuronal como una fabrica de transformaciones. La materia prima entra desordenada; las capas no "piensan" como una persona, pero cada una reordena, filtra y recombina informacion hasta producir algo util al final.

### Idea clave

Una red neuronal no es una base de datos con respuestas guardadas. Es una maquina de transformar entradas en salidas a traves de parametros aprendidos.

## 3. Pesos, parametros y aprendizaje

El conocimiento de un modelo no esta guardado como frases legibles en un archivador. Esta distribuido en numeros.

Esos numeros se llaman parametros. Dentro de ellos, los pesos indican cuanto debe influir una señal sobre otra dentro del modelo.

Cuando un modelo aprende, lo que cambia no es una lista de definiciones escritas a mano. Lo que cambia son millones o miles de millones de valores numericos ajustados durante entrenamiento.

| Concepto | Explicacion simple |
|---|---|
| Parametro | Valor ajustable dentro del modelo |
| Peso | Tipo de parametro que controla la influencia entre señales |
| Aprender | Ajustar parametros para reducir error |
| Modelo mas grande | Tiene mas parametros para capturar mas patrones |

### Imagen mental

Piensa en una consola con una cantidad gigantesca de perillas. Entrenar el modelo consiste en mover esas perillas, una y otra vez, hasta que el sistema se vuelva mejor prediciendo el tipo de salida que se busca.

### Idea clave

Aprender, para el modelo, significa ajustar parametros. No significa entender como un humano ni adquirir conciencia.

## 4. Que es un embedding

Un embedding es una representacion numerica de un token o fragmento de informacion.

Los modelos no trabajan directamente con palabras como nosotros las vemos. Primero convierten esos elementos en vectores: grupos de numeros que capturan relaciones utiles para el modelo.

Dicho de forma practica: un embedding es una forma de ubicar piezas de lenguaje en un espacio matematico donde la cercania representa similitud o relacion.

| Token o concepto | Intuicion del embedding |
|---|---|
| perro | Queda cerca de conceptos como gato, mascota o veterinario |
| abogado | Queda mas cerca de contrato, juicio o cliente |
| pizza | Queda cerca de comida, queso o restaurante |
| Python | Segun el contexto, puede acercarse a lenguaje de programacion o a serpiente |

### Por que esto importa

Gracias a los embeddings, el modelo no solo ve simbolos sueltos. Empieza a operar sobre relaciones. Eso le permite capturar parecido, contexto, asociacion y estructura de una forma que una lista de palabras aisladas no permitiria.

### Importante: el contexto cambia el significado

La misma palabra puede adquirir una representacion distinta segun el contexto.

Ejemplo:

```text
"Python sirve para automatizar tareas"
"Python es una serpiente no venenosa"
```

En ambos casos aparece el mismo token visible, pero el entorno cambia lo que esa palabra significa dentro del modelo.

### Idea clave

Los embeddings son uno de los puentes mas importantes entre lenguaje humano y procesamiento matematico.

## 5. Que problema resuelve la atencion

Si un modelo solo leyera tokens en cadena, sin poder ponderar cuales partes del contexto son mas relevantes, se perderia muchas relaciones importantes.

La atencion resuelve ese problema. Le permite al modelo mirar distintas partes del contexto y asignarles distinta importancia al procesar cada token.

En lenguaje mas simple: no todo el contexto pesa igual para cada decision.

Ejemplo:

```text
El trofeo no cabe en la maleta porque es muy grande.
```

Para interpretar bien la frase, el sistema necesita prestar mas atencion a ciertos terminos que a otros. No basta con leer todo en orden; necesita identificar relaciones relevantes.

| Sin buena atencion | Con atencion |
|---|---|
| Trata el contexto de manera mas plana | Prioriza partes utiles del contexto |
| Pierde relaciones lejanas con mas facilidad | Puede conectar tokens separados |
| Le cuesta mas desambiguar | Mejora la interpretacion contextual |

### Self-attention, explicado sin drama

En un transformer, cada token puede "mirar" a otros tokens del contexto para construir una representacion mas rica de si mismo.

Eso no significa que el modelo lea como un humano. Significa que calcula dependencias entre posiciones del texto para decidir que informacion combinar.

### Idea clave

La atencion es una de las razones por las que los modelos modernos manejan contexto mucho mejor que arquitecturas mas antiguas.

## 6. Que es un transformer

Un transformer es una arquitectura de red neuronal diseñada para procesar secuencias de manera muy eficaz, apoyandose sobre todo en mecanismos de atencion.

Su importancia historica es enorme porque permitio escalar el entrenamiento de modelos de lenguaje con mucho mejor rendimiento que varias arquitecturas anteriores.

No hace falta memorizar sus ecuaciones. Lo importante es comprender sus bloques funcionales.

| Bloque | Funcion |
|---|---|
| Tokenizacion | Divide el texto en unidades procesables |
| Embeddings | Convierte tokens en vectores |
| Informacion posicional | Ayuda al modelo a distinguir orden y ubicacion |
| Self-attention | Conecta tokens entre si segun relevancia |
| Capas de procesamiento | Refinan las representaciones varias veces |
| Salida | Produce probabilidades sobre el siguiente token |

### Por que fue tan importante

El transformer no solo mejoro calidad. Tambien permitio paralelizar mejor ciertos procesos de entrenamiento y trabajar de forma mas potente con relaciones de largo alcance dentro del texto.

### Idea clave

Cuando hoy hablamos de LLMs modernos, casi siempre estamos hablando de modelos construidos sobre la familia de arquitecturas transformer o muy cercanas a ella.

## 7. Del texto a la respuesta: recorrido completo

Ya tenemos las piezas principales. Ahora conviene unirlas en un solo flujo mental.

Recorrido conceptual:

1. El sistema recibe texto.
2. Ese texto se divide en tokens.
3. Cada token se convierte en un embedding.
4. El modelo mezcla embeddings con informacion posicional.
5. Las capas transformer aplican atencion y otras transformaciones.
6. El sistema calcula probabilidades para el siguiente token.
7. Se elige o muestrea un token.
8. Ese token se agrega a la secuencia.
9. El ciclo se repite hasta completar la respuesta.

**Ruta corta:** Texto -> tokens -> embeddings -> capas transformer -> probabilidades -> siguiente token -> respuesta

### Idea clave

El modelo no genera una respuesta completa de golpe. La construye iterativamente, apoyado en representaciones internas cada vez mas refinadas.

## 8. Que significa entrenar un modelo

Entrenar un modelo significa exponerlo a enormes cantidades de datos y ajustar sus parametros para que mejore en una tarea objetivo.

En el caso de los modelos de lenguaje, una gran parte del entrenamiento gira en torno a predecir tokens a partir de contexto.

No es un proceso pequeño ni informal. Requiere:

- Datos en grandes volumenes.
- Muchisimo computo.
- Infraestructura especializada.
- Iteraciones masivas.
- Evaluacion constante.

| Paso del entrenamiento | Que ocurre |
|---|---|
| Datos | Se toman ejemplos de texto, codigo u otros formatos relevantes |
| Prediccion | El modelo intenta anticipar la salida correcta |
| Error | Se mide que tan lejos estuvo de la respuesta deseada |
| Ajuste | Se modifican parametros para reducir ese error |
| Repeticion | El ciclo ocurre una cantidad gigantesca de veces |

### Idea clave

Un modelo no nace sabiendo. Su comportamiento emerge de muchisimas rondas de prediccion, error y ajuste.

## 9. Loss y ajuste de pesos

La loss, o perdida, es una forma de medir que tan equivocada fue la prediccion del modelo.

Si el modelo recibe un contexto y asigna alta probabilidad a una continuacion absurda, la perdida sera mayor. Si concentra la probabilidad en respuestas mas adecuadas, la perdida baja.

Ejemplo conceptual:

```text
Contexto: "El cielo esta muy..."
Objetivo correcto: "azul"
Prediccion del modelo: "democracia"
Resultado: perdida alta
```

Con esa señal de error, el sistema ajusta pesos para que en el futuro distribuya mejor sus probabilidades.

| Concepto | Funcion |
|---|---|
| Loss | Mide el error del modelo |
| Backpropagation | Reparte la señal de error a traves de la red |
| Optimizador | Decide como actualizar los parametros |
| Ajuste de pesos | Cambia el modelo para que falle menos en iteraciones futuras |

### Lo importante para principiantes

No hace falta derivar ninguna formula. Basta con entender la logica:

```text
Prediccion -> error -> ajuste -> nueva prediccion
```

### Idea clave

La calidad del modelo no aparece por magia. Aparece porque el entrenamiento premia predicciones mejores y castiga predicciones peores a escala masiva.

## 10. Pretraining

El pretraining es la gran fase de entrenamiento general.

Aqui el modelo aprende patrones amplios del lenguaje, del codigo, del formato, del estilo y de muchas regularidades presentes en sus datos.

Es la etapa que le da una base generalista.

| El pretraining le da al modelo | Pero no le garantiza |
|---|---|
| Sintaxis y estructura | Verdad perfecta |
| Asociaciones semanticas | Actualizacion en tiempo real |
| Patrones de estilo | Confiabilidad absoluta en dominios criticos |
| Capacidad amplia de continuacion | Comportamiento alineado con todas las expectativas humanas |

### Idea clave

Pretraining crea la base del modelo. No lo vuelve automaticamente seguro, obediente ni experto en todo.

## 11. Fine-tuning

El fine-tuning es una etapa posterior en la que el modelo ya preentrenado se ajusta con datos mas especificos o con un objetivo mas concreto.

Sirve para especializar comportamiento.

Ejemplos:

- Un asistente legal entrenado sobre documentos juridicos.
- Un asistente de soporte afinado para responder en cierto formato.
- Un modelo preparado para extraer datos estructurados de facturas.

| Fine-tuning puede mejorar | Pero tambien puede degradar |
|---|---|
| Especializacion por dominio | Flexibilidad general |
| Consistencia de formato | Cobertura amplia |
| Rendimiento en tareas concretas | Balance si los datos son malos o muy estrechos |

### Idea clave

Fine-tuning no es "hacer mas inteligente" al modelo en abstracto. Es empujarlo hacia un comportamiento mas especifico.

## 12. RLHF

RLHF significa Reinforcement Learning from Human Feedback.

La idea general es simple: despues de la fase base, se usa retroalimentacion humana para empujar al modelo hacia respuestas que las personas consideran mas utiles, mas claras, mas seguras o mas alineadas con ciertas expectativas.

Secuencia conceptual:

1. El modelo produce respuestas posibles.
2. Personas o sistemas de preferencia comparan esas respuestas.
3. Se construye una señal de recompensa.
4. El modelo se ajusta para preferir salidas mejor valoradas.

### Que suele mejorar con RLHF

- Obediencia a instrucciones.
- Tono mas util o mas conversacional.
- Rechazo de ciertas respuestas no deseadas.
- Mejora aparente en utilidad general.

### Lo que RLHF no hace

- No convierte al modelo en una fuente perfecta de verdad.
- No elimina todos los errores.
- No reemplaza buen contexto, buenas herramientas ni evaluacion.

### Idea clave

RLHF alinea comportamiento. No reescribe las leyes de fondo del modelo.

## 13. Entrenamiento, fine-tuning y RLHF en una sola vista

| Etapa | Objetivo principal | Resultado tipico |
|---|---|---|
| Pretraining | Aprender patrones generales a gran escala | Base amplia de lenguaje y estructura |
| Fine-tuning | Especializar el modelo | Mejor rendimiento en tareas o dominios concretos |
| RLHF | Alinear respuestas con preferencias humanas | Respuestas mas utiles, obedientes o seguras |

### Idea clave

El comportamiento final del modelo es el resultado acumulado de varias capas de entrenamiento, no de una sola fase milagrosa.

## 14. Que es la inferencia

La inferencia es el momento en el que usamos un modelo ya entrenado para obtener una salida.

Aqui ya no estamos ensenandole desde cero. Estamos aprovechando lo que aprendio antes.

Durante la inferencia:

- El modelo recibe prompt y contexto.
- Procesa la entrada con sus parametros actuales.
- Calcula probabilidades.
- Genera respuesta token por token.

**Ruta de inferencia:** Prompt + contexto -> modelo ya entrenado -> probabilidades -> salida

### Por que importa esta distincion

Muchos errores conceptuales nacen aqui. Una conversacion normal con un chatbot no significa que el modelo este reentrenandose en ese momento.

### Idea clave

Entrenamiento cambia el modelo. Inferencia usa el modelo.

## 15. Entrenamiento versus inferencia

| Dimension | Entrenamiento | Inferencia |
|---|---|---|
| Objetivo | Aprender o ajustar parametros | Generar una salida util |
| Datos | Enormes volumenes y muchas iteraciones | El prompt y su contexto inmediato |
| Computo | Muy alto y prolongado | Alto, pero mucho menor que entrenar |
| Parametros | Se modifican | Se mantienen fijos |
| Tiempo | Puede durar dias, semanas o meses | Suele medirse en segundos o menos |
| Resultado | Un modelo mejorado o ajustado | Una respuesta concreta |

### Idea clave

Confundir entrenamiento con inferencia es una de las fuentes mas comunes de malentendidos sobre IA moderna.

## 16. Tamano, costo, latencia y capacidad

No todos los modelos sirven igual para todas las tareas.

En la practica, siempre aparecen compromisos entre capacidad, costo, velocidad y facilidad de despliegue.

| Factor | Si sube mucho | Lo que suele pasar |
|---|---|---|
| Tamano del modelo | Mas parametros y mas computo | Puede mejorar capacidad, pero suben costo y latencia |
| Calidad de datos | Mejor curacion y cobertura | Suele mejorar bastante el resultado |
| Contexto disponible | Mas informacion en la entrada | Puede ayudar mucho o meter ruido |
| Alineacion | Mas restricciones y guias | Puede mejorar seguridad, pero a veces reducir libertad |

### Un punto importante

Mas grande no siempre significa mejor para tu caso. A veces un modelo mas pequeno, mas barato o mas especializado resuelve mejor una tarea concreta.

### Idea clave

Elegir modelo es una decision de producto y de ingenieria, no solo una carrera por usar el modelo mas grande posible.

## 17. Donde nacen muchos limites del modelo

Parte de los errores de un modelo no vienen de un prompt malo. Vienen de como fue construido.

Fuentes tipicas de limite:

- Datos incompletos, sesgados o ruidosos.
- Objetivo de entrenamiento que optimiza probabilidad, no verdad absoluta.
- Restricciones de contexto.
- Compromisos de costo y tamano.
- Alineacion que a veces vuelve al modelo mas cauteloso o mas rigido.
- Falta de acceso a herramientas o datos actuales.

### Idea clave

Entender arquitectura y entrenamiento no solo explica fortalezas; tambien explica por que un modelo puede sonar convincente y aun asi fallar.

## 18. Tres analogias utiles

### 1. Embeddings como coordenadas de significado

No son definiciones de diccionario. Son posiciones numericas que permiten que el modelo opere sobre cercanias y relaciones.

### 2. Atencion como foco dinamico

No todo el contexto pesa igual. La atencion ayuda al modelo a decidir que partes mirar mas en cada paso.

### 3. Entrenamiento como ajuste masivo de perillas

El modelo no aprende escribiendo apuntes internos. Aprende ajustando parametros una cantidad enorme de veces.

## 19. Ejemplos guiados

Los siguientes ejemplos aterrizan tres ideas centrales: embeddings, atencion y diferencia entre entrenamiento e inferencia.

### Demo 1: cercania semantica sin matematicas

Observa esta lista de palabras:

- perro
- gato
- veterinario
- contrato
- juzgado
- pizza

Para pensar:

- Cuales pondrian mas cerca entre si y por que.
- Que palabra queda claramente lejos del resto.
- Como podria usar esa cercania un sistema numerico.

### Demo 2: que parte del contexto importa mas

Observa esta frase:

```text
El servidor no arranca porque el archivo de configuracion esta corrupto.
```

Para pensar:

- Que elemento parece ser la causa del problema.
- Que palabras son realmente importantes para interpretar la frase.
- Por que leer todo "plano" seria peor que ponderar relevancias.

### Demo 3: entrenamiento o inferencia

Observa estas tres situaciones e intenta clasificarlas:

1. Un laboratorio ajusta un modelo durante semanas con miles de GPUs.
2. Una persona le pide a un chatbot que resuma un PDF.
3. Una empresa especializa un modelo para soporte tecnico interno.

Una clasificacion razonable seria:

- Caso 1: entrenamiento.
- Caso 2: inferencia.
- Caso 3: ajuste adicional, por ejemplo fine-tuning.

## 20. Actividad practica de la sesion

### Actividad: del dato a la respuesta

Elige una tarea, por ejemplo:

- Resumir un contrato.
- Clasificar correos de soporte.
- Generar una descripcion de producto.
- Ayudar a programar una funcion.
- Responder preguntas sobre un manual tecnico.

Luego construye una explicacion del recorrido completo del sistema usando esta plantilla:

| Paso | Que ocurre en este caso |
|---|---|
| Datos o conocimiento base | |
| Tokenizacion | |
| Embeddings | |
| Atencion o arquitectura | |
| Tipo de entrenamiento relevante | |
| Momento de inferencia | |
| Riesgos o limites | |

### Segunda parte: comparar perfiles de modelo

Elige dos de estos perfiles y compara cual conviene mas para la tarea:

- Modelo pequeno y barato.
- Modelo grande y generalista.
- Modelo afinado para dominio especifico.

Preguntas de apoyo:

- Cual ofrece mejor velocidad.
- Cual parece mas capaz.
- Cual convendria para produccion con costo controlado.
- Donde podria fallar cada uno.

### Entregable de la actividad

Entrega:

- Una tabla con el recorrido desde datos hasta respuesta.
- Una explicacion breve de donde se entrena y donde se usa el modelo.
- Una comparacion argumentada entre dos perfiles de modelo.

Un buen entregable no se limita a repetir palabras tecnicas. Debe mostrar que el grupo entiende como se conectan las piezas.

## 21. Mini evaluacion de comprension

Responder en 3 a 5 lineas cada pregunta:

1. Que es una red neuronal en terminos conceptuales.
2. Que es un embedding y por que importa.
3. Que problema resuelve la atencion.
4. Cual es la diferencia entre entrenamiento e inferencia.
5. Para que sirven pretraining, fine-tuning y RLHF.
6. Por que un modelo puede ser muy util y aun asi equivocarse.

La meta no es repetir definiciones vacias. La meta es explicar el proceso con claridad.

## 22. Glosario esencial

| Termino | Definicion simple |
|---|---|
| Red neuronal | Sistema de capas que transforma entradas en salidas mediante parametros ajustables |
| Parametro | Valor interno que puede cambiar durante entrenamiento |
| Peso | Parametro que regula la influencia entre señales |
| Embedding | Representacion numerica de un token o concepto |
| Atencion | Mecanismo para ponderar que partes del contexto importan mas |
| Transformer | Arquitectura moderna basada en atencion para procesar secuencias |
| Loss | Medida del error del modelo |
| Backpropagation | Metodo para propagar error y ajustar la red |
| Optimizador | Algoritmo que actualiza parametros para reducir error |
| Pretraining | Entrenamiento general a gran escala |
| Fine-tuning | Ajuste adicional para tareas o dominios especificos |
| RLHF | Alineacion del modelo a partir de feedback humano |
| Inferencia | Uso del modelo ya entrenado para generar una salida |
| Latencia | Tiempo que tarda el sistema en responder |

## 23. Ideas para recordar

- Un modelo moderno convierte lenguaje en representaciones numericas antes de responder.
- Los embeddings son el puente entre tokens y calculo.
- La atencion ayuda al modelo a decidir que parte del contexto mirar mas.
- Entrenar significa ajustar parametros; inferir significa usar el modelo.
- Pretraining da base general; fine-tuning especializa; RLHF alinea comportamiento.
- Un modelo no falla solo por un mal prompt; tambien falla por sus limites estructurales.
- Elegir modelo es una decision de producto, costo y riesgo, no solo de potencia bruta.

## 24. Cierre conceptual

La gran leccion de esta sesion es que un modelo moderno no es una voz misteriosa que aparece desde la nada. Es el resultado de una arquitectura concreta, de datos concretos y de procesos concretos de entrenamiento y alineacion.

Cuando un estudiante entiende esto, cambia su relacion con la IA. Deja de verla como una caja negra absoluta y empieza a verla como un sistema con piezas, etapas, costos, compromisos y limites. Ese cambio es decisivo, porque prepara el terreno para todo lo que sigue: prompting, APIs, agentes, herramientas, evaluacion y despliegue.

Ese es el objetivo real de esta sesion: que el grupo deje de preguntar solo "que respondio el modelo" y empiece a preguntar tambien "como fue construido para responder asi".