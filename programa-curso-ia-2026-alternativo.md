# Programa Alternativo del Curso: Construir Productos con IA en 2026

## Vision general

Esta version alternativa del programa esta pensada para alinear el curso con la realidad actual del mercado y con la direccion que esta tomando el desarrollo con IA. Mantiene la base conceptual del programa original, pero sube el estandar en lo que hoy separa una demo atractiva de un producto serio: contexto bien diseñado, salidas estructuradas, evaluacion, observabilidad, seguridad, CI/CD y despliegue reproducible.

La premisa del curso es simple: aprender a usar IA para construir productos utiles, pero sin caer en humo, dependencias ciegas de herramientas o flujos fragiles.

## Objetivo principal

Que cada participante pueda pasar de una idea a una aplicacion util con IA, entendiendo no solo como pedirle cosas a un modelo, sino tambien como conectarlo con herramientas, validar su comportamiento, controlar sus riesgos y desplegarlo con una base razonable de ingenieria.

## Perfil de los participantes

- Principiantes con interes en IA aplicada.
- Personas que quieren construir productos, automatizaciones o asistentes reales.
- Equipos que quieren aprender un flujo moderno de trabajo con IA y desarrollo.

## Resultados esperados

Al terminar el curso, cada participante deberia poder:

- Explicar que es un LLM, que es un token y como funciona el contexto.
- Entender a nivel conceptual como funcionan las redes neuronales modernas y el entrenamiento.
- Diseñar prompts e instrucciones con criterio.
- Distinguir entre modelo, producto, workflow y agente.
- Usar salidas estructuradas para reducir fragilidad en apps con IA.
- Entender cuando conviene usar contexto directo, RAG o herramientas externas.
- Consumir APIs con claves seguras y variables de entorno.
- Comprender MCP como capa estandar de integracion.
- Usar asistentes de desarrollo como VS Code, GitHub Copilot, Cursor o Claude Code con mayor control.
- Versionar proyectos con Git y colaborar en equipo.
- Dockerizar una app y entender su camino a produccion.
- Implementar una base minima de CI/CD.
- Desplegar una app funcional y evaluar si realmente se comporta como se espera.

## Principios del programa

Este programa parte de algunas ideas clave que hoy son centrales en el desarrollo con IA:

- No todo problema requiere un agente.
- El contexto es una disciplina de diseño, no un detalle menor.
- Las apps con IA deben medirse, no solo admirarse.
- Las salidas estructuradas son mejores que el texto libre cuando la app depende del resultado.
- Los asistentes aceleran, pero no reemplazan criterio tecnico.
- Un producto robusto necesita logs, validaciones, seguridad y despliegue reproducible.

## Formato recomendado

- Modalidad: curso modular.
- Duracion sugerida: 10 sesiones.
- Duracion por sesion: 90 a 120 minutos.
- Enfoque sugerido: 20 por ciento concepto, 30 por ciento demo, 50 por ciento practica.

## Estructura del programa

### Modulo 1. Fundamentos de IA, LLMs y tokens

**Objetivo**

Dar una base clara sobre que es un modelo de lenguaje y como funciona a nivel practico.

**Contenidos**

- Que es IA, machine learning, deep learning y LLM.
- Que es un token.
- Como predice texto un modelo.
- Ventana de contexto.
- Diferencia entre modelo, chat, asistente y producto.

**Ejercicio practico**

- Comparar respuestas usando distinto nivel de contexto.
- Analizar como cambia costo, calidad y control cuando cambia la cantidad de tokens.

**Resultado del modulo**

Los participantes entienden la unidad economica y tecnica basica de los sistemas con IA: tokens, contexto y prediccion.

### Modulo 2. Redes neuronales, transformers y entrenamiento

**Objetivo**

Entender de forma conceptual como se construyen y entrenan los modelos modernos.

**Contenidos**

- Redes neuronales.
- Embeddings.
- Atencion y transformers.
- Entrenamiento, loss y ajuste de pesos.
- Pretraining, fine-tuning y RLHF.
- Diferencia entre entrenamiento, inferencia y uso en producto.

**Ejercicio practico**

- Dibujar el recorrido desde datos hasta respuesta final.
- Identificar por que un modelo puede responder bien a unas tareas y fallar en otras.

**Resultado del modulo**

Los participantes dejan de tratar al modelo como una caja negra absoluta y entienden sus limites estructurales.

### Modulo 3. Prompting, instrucciones y salidas estructuradas

**Objetivo**

Aprender a diseñar interacciones robustas con modelos, no solo prompts bonitos.

**Contenidos**

- Rol, objetivo, contexto, restricciones y formato.
- Zero-shot y few-shot.
- Prompting iterativo.
- Como pedir resultados verificables.
- Texto libre versus JSON.
- Structured outputs, schemas y validacion.
- Function calling y tool calling a nivel conceptual.

**Ejercicio practico**

- Convertir un prompt ambiguo en una instruccion util.
- Transformar una salida libre en una salida estructurada para una app.

**Resultado del modulo**

Los participantes aprenden que una app seria no deberia depender solo de texto libre cuando necesita procesar resultados de forma fiable.

### Modulo 4. Context engineering, RAG y productos con IA

**Objetivo**

Entender como se construye contexto util para una aplicacion y cuando usar recuperacion de informacion externa.

**Contenidos**

- Contexto explicito e implicito.
- Contexto persistente.
- Memoria.
- Archivos, instrucciones y estado.
- Que es RAG.
- Embeddings y busqueda semantica a nivel conceptual.
- Cuando conviene usar RAG, archivos, herramientas o prompt directo.
- Ejemplos de productos tipo ChatGPT Projects.

**Ejercicio practico**

- Diseñar la estrategia de contexto para un asistente de planificacion o research.
- Decidir que va en prompt, que va en memoria y que va en busqueda externa.

**Resultado del modulo**

Los participantes entienden que el verdadero valor de muchas apps con IA no esta solo en el modelo, sino en como se le entrega el contexto correcto.

### Modulo 5. APIs, claves, variables de entorno y configuracion

**Objetivo**

Aprender a integrar servicios externos con practicas basicas de seguridad y configuracion.

**Contenidos**

- Que es una API.
- API key versus token de texto.
- Request y response.
- Rate limits y costo.
- Variables de entorno.
- Separacion entre codigo y configuracion.
- Desarrollo, staging y produccion.
- Manejo basico de secretos.

**Ejercicio practico**

- Hacer una llamada simple a una API.
- Configurar claves con variables de entorno.
- Detectar errores comunes de seguridad y configuracion.

**Resultado del modulo**

Los participantes pueden conectar servicios sin hardcodear credenciales ni romper el entorno al mover la app entre maquinas o deploys.

### Modulo 6. Workflows, agentes, MCP y guardrails

**Objetivo**

Entender que no todo debe resolverse con un agente autonomo y aprender a diferenciar workflows simples de sistemas mas complejos.

**Contenidos**

- Workflow versus agente.
- Prompt chaining, routing y evaluacion iterativa a nivel conceptual.
- Que es un agente.
- Herramientas, memoria, estado y criterio de parada.
- MCP como protocolo estandar para integraciones.
- Permisos, aprobaciones humanas y guardrails.
- Riesgos: costo, latencia, errores compuestos y uso inseguro de herramientas.

**Ejercicio practico**

- Diseñar un workflow simple y compararlo con un agente para el mismo caso.
- Definir herramientas, permisos y limites para un agente pequeno.

**Resultado del modulo**

Los participantes desarrollan criterio para no sobreingenierizar y para usar agentes solo cuando agregan valor real.

### Modulo 7. Herramientas modernas de desarrollo con IA

**Objetivo**

Aprender el flujo real de trabajo con asistentes de desarrollo en 2026.

**Contenidos**

- VS Code como entorno central.
- GitHub Copilot.
- Cursor.
- Claude Code.
- Contexto del workspace.
- Diffs, checkpoints y revision de cambios.
- Custom instructions, agentes personalizados y herramientas.
- Logs y depuracion de interacciones con asistentes.

**Ejercicio practico**

- Resolver una tarea sencilla con dos herramientas distintas.
- Comparar autonomia, calidad, control, permisos y trazabilidad.

**Resultado del modulo**

Los participantes aprenden a trabajar con copilotos y agentes sin dejar de revisar, validar y dirigir el resultado.

### Modulo 8. Git, colaboracion y CI/CD basico

**Objetivo**

Construir una base minima para trabajo en equipo y automatizacion del flujo de entrega.

**Contenidos**

- Repositorio, commit, rama, merge.
- Clone, init, add, commit, push, pull.
- Conflictos simples.
- Gitignore.
- Pull requests y revision.
- Introduccion a CI/CD.
- GitHub Actions a nivel practico.
- Automatizar test, lint o build simple.

**Ejercicio practico**

- Crear un repo, trabajar en ramas y fusionar cambios.
- Configurar un workflow minimo para validar el proyecto en cada push.

**Resultado del modulo**

Los participantes entienden que entregar software no es solo escribir codigo: tambien es automatizar validaciones basicas.

### Modulo 9. Docker, observabilidad, seguridad y despliegue

**Objetivo**

Aprender a correr, inspeccionar y desplegar una app con una base minima de operaciones modernas.

**Contenidos**

- Que problema resuelve Docker.
- Imagen y contenedor.
- Dockerfile.
- Puertos y redes.
- Variables de entorno en despliegue.
- Logs basicos.
- Observabilidad inicial.
- Servidor, plataforma gestionada y VPS.
- Despliegue en Railway, Render o Vercel segun el caso.
- Seguridad basica: secretos, permisos, datos sensibles y prompt injection a nivel introductorio.

**Ejercicio practico**

- Dockerizar una app simple.
- Levantarla localmente con configuracion reproducible.
- Desplegar una primera version y revisar logs.

**Resultado del modulo**

Los participantes entienden el paso real entre prototipo local y sistema ejecutandose en produccion.

### Modulo 10. Proyecto final con evaluacion

**Objetivo**

Construir una aplicacion util con IA y validarla con criterios concretos.

**Opciones de proyecto**

- Asistente de planificacion personal o de equipo.
- Copiloto creativo para contenido o ideas.
- Mini app de chat con archivos y contexto.
- Workflow o agente simple con una o dos herramientas.

**Entregables**

- App funcional.
- Repositorio ordenado.
- Variables de entorno bien configuradas.
- Docker basico.
- Deploy funcional.
- Casos de prueba o evals sencillos.
- Demo final.

**Resultado del modulo**

Los participantes terminan con algo que existe, funciona y puede ser inspeccionado y mejorado con criterio.

## Capa nueva: evaluacion de apps con IA

Este programa alternativo incorpora una idea que hoy ya no es opcional para construir con IA: evaluar.

No basta con preguntar si una respuesta parece buena. Hay que enseñar a comprobar:

- Si el sistema responde consistentemente.
- Si se mantiene dentro del formato esperado.
- Si mejora o empeora al cambiar prompt o modelo.
- Si falla con casos borde.
- Si el costo y la latencia siguen siendo razonables.

En el proyecto final, conviene exigir una mini bateria de validacion, aunque sea sencilla.

## Proyecto final recomendado

La mejor opcion para este programa es un asistente de planificacion o un copiloto de trabajo con estas capas:

- Interfaz simple.
- Llamada a modelo.
- Contexto o archivo de apoyo.
- Salida estructurada.
- Variables de entorno.
- Git.
- Docker.
- Deploy.
- Casos de prueba o evals basicos.

Ese proyecto permite enseñar el flujo completo sin volverse demasiado ambicioso para principiantes.

## Metodologia sugerida

Cada sesion deberia combinar:

- Concepto.
- Demo.
- Practica.

La practica debe dominar. Si el curso se va demasiado a explicacion teorica o comparativas de herramientas, pierde valor.

## Criterios de evaluacion del curso

Conviene evaluar si cada proyecto:

- Resuelve un problema claro.
- Tiene un flujo entendible.
- Usa contexto de forma razonable.
- Produce salidas utiles y consistentes.
- Maneja bien credenciales y configuracion.
- Se puede levantar en otra maquina o entorno.
- Tiene una base minima de validacion.
- Puede desplegarse sin caos.

## Requisitos minimos recomendados

- Computador con acceso a internet.
- VS Code u otro editor equivalente.
- Git instalado.
- Docker instalado.
- Cuenta en al menos una plataforma con acceso a modelos o APIs.
- Disposicion para trabajar con herramientas modernas y revisar resultados de forma critica.

## Cierre

Este programa alternativo no busca impresionar con palabras de moda. Busca enseñar el oficio emergente de construir con IA. Eso incluye fundamentos, contexto, herramientas, integraciones, agentes cuando tienen sentido, y una disciplina minima de evaluacion, seguridad y despliegue. Ese es el tipo de formacion que mejor se alinea con el mercado actual y con el futuro cercano del desarrollo.