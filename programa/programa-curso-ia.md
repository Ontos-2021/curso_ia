# Programa del Curso: Construir Productos con IA

## Vision general

Este curso esta pensado para principiantes que quieren aprender a usar inteligencia artificial para construir cosas utiles con criterio tecnico. La idea no es solo aprender a "prompt-ear" o a sacar respuestas vistosas, sino entender como funciona un modelo, como se construye un producto encima de el y como llevar una aplicacion desde la idea hasta un prototipo desplegado.

El curso mezcla fundamentos de IA, prompting, asistentes, agentes, APIs, MCP y herramientas modernas de desarrollo con las bases minimas para entregar software: Git, variables de entorno, Docker y despliegue.

## Objetivo principal

Que cada participante pueda pasar de una idea a una aplicacion util con IA, entendiendo que esta haciendo, como integrarlo con herramientas reales y como dejarlo funcionando con una base robusta.

## Perfil de los participantes

- Principiantes totales o personas con muy poca experiencia tecnica.
- Personas curiosas por la IA que quieren construir herramientas utiles.
- Equipos o grupos de amigos que quieren aprender juntos a crear productos, automatizaciones o asistentes.

## Resultados esperados

Al terminar el curso, cada participante deberia poder:

- Explicar que es un LLM, que es un token y como funciona el contexto.
- Entender a nivel conceptual como se entrenan las redes neuronales modernas.
- Usar asistentes y prompting con criterio, no solo por intuicion.
- Distinguir entre modelo, chat, asistente, producto y agente.
- Consumir una API usando claves de forma segura.
- Entender que problema resuelve MCP y como pensar integraciones.
- Usar herramientas modernas como VS Code, GitHub Copilot, Cursor o Claude Code con mejor criterio.
- Trabajar con Git en un flujo basico de colaboracion.
- Configurar variables de entorno correctamente.
- Empaquetar una app simple con Docker.
- Desplegar una app o prototipo funcional.

## Formato recomendado

- Modalidad: curso modular.
- Duracion sugerida: 10 sesiones.
- Duracion por sesion: 90 a 120 minutos.
- Enfoque: 20 por ciento concepto, 30 por ciento demo, 50 por ciento practica.

Tambien se puede adaptar a una version intensiva de dos jornadas largas o compactarse a 8 sesiones, pero esta version modular de 10 sesiones da mas espacio para practicar y consolidar.

## Estructura del programa

### Modulo 1. Fundamentos de IA y LLMs

**Objetivo**

Que los participantes entiendan que es un modelo de lenguaje, que hace realmente y por que no es magia.

**Contenidos**

- Que es IA, machine learning, deep learning y LLM.
- Que es un token.
- Como predice texto un modelo.
- Que es el contexto y la ventana de contexto.
- Diferencia entre modelo, chat, asistente y producto.

**Ejercicio practico**

- Resolver una misma tarea con un prompt corto y con un prompt con contexto.
- Analizar que cambia cuando el contexto esta bien o mal definido.

**Resultado del modulo**

Los participantes dejan de ver la IA como una caja negra total y adquieren un mapa mental util para el resto del curso.

### Modulo 2. Redes neuronales, transformers y entrenamiento

**Objetivo**

Dar una base conceptual seria sobre como se construyen estos modelos, sin caer en matematica innecesaria para el nivel inicial.

**Contenidos**

- Que es una red neuronal.
- Embeddings.
- Atencion y transformers.
- Entrenamiento, loss y ajuste de pesos.
- Pretraining, fine-tuning y RLHF.
- Diferencia entre entrenamiento e inferencia.

**Ejercicio practico**

- Trazar el camino completo desde los datos hasta una respuesta del modelo.
- Discutir que cambia entre un modelo mas pequeno, mas barato o mas capaz.

**Resultado del modulo**

Los participantes entienden la base conceptual de un modelo moderno y pueden hablar con mas precision sobre sus capacidades y limites.

### Modulo 3. Prompting y chat con asistentes

**Objetivo**

Aprender a trabajar con asistentes de forma estructurada, evitando prompts vagos o improvisados.

**Contenidos**

- Como escribir instrucciones claras.
- Rol, objetivo, contexto, restricciones y formato de salida.
- Prompting iterativo.
- Zero-shot y few-shot.
- Como reducir alucinaciones.
- Como pedir salidas verificables y utiles.

**Ejercicio practico**

- Tomar prompts malos y reescribirlos hasta volverlos utiles.
- Diseñar un prompt para planificacion, uno para creatividad y uno para codigo.

**Resultado del modulo**

Los participantes aprenden a usar asistentes como herramientas de trabajo, no solo como buscadores conversacionales.

### Modulo 4. Productos construidos arriba de modelos

**Objetivo**

Entender que un producto con IA es mucho mas que una llamada a un modelo.

**Contenidos**

- Diferencia entre modelo y producto.
- Contexto persistente.
- Memoria.
- Archivos e instrucciones.
- Herramientas.
- Ejemplos tipo ChatGPT Projects.
- Que hace que una app sea robusta.

**Ejercicio practico**

- Disenar la arquitectura conceptual de un producto simple con IA.
- Separar que parte corresponde al modelo, cual al backend y cual a la interfaz.

**Resultado del modulo**

Los participantes empiezan a pensar en sistemas y productos, no solo en prompts sueltos.

### Modulo 5. APIs, claves, costos y variables de entorno

**Objetivo**

Aprender a integrar servicios externos con un minimo de higiene tecnica y control de costos.

**Contenidos**

- Que es una API.
- API key versus token de texto.
- Request y response.
- Rate limits y costo por uso.
- Variables de entorno.
- Por que no hardcodear claves.
- Diferencia entre desarrollo y produccion.

**Ejercicio practico**

- Hacer una llamada simple a una API.
- Configurar credenciales con variables de entorno.
- Detectar malas practicas de seguridad comunes.

**Resultado del modulo**

Los participantes pueden integrar modelos o servicios externos sin exponer secretos ni perder de vista el costo.

### Modulo 6. Agentes y MCP

**Objetivo**

Entender cuando tiene sentido usar un agente, que lo diferencia de un chat y que problema resuelve MCP.

**Contenidos**

- Que es un agente.
- Herramientas, estado, memoria y toma de decisiones.
- Cuando un agente tiene sentido y cuando es sobreingenieria.
- Que problema resuelve MCP.
- Integracion con archivos, servicios y herramientas.

**Ejercicio practico**

- Disenar un agente simple de research, planificacion o ejecucion.
- Definir sus herramientas, inputs, outputs, limites y criterio de parada.

**Resultado del modulo**

Los participantes entienden el concepto de agente con una base practica y sin caer en hype vacio.

### Modulo 7. Herramientas modernas para construir

**Objetivo**

Aprender a usar el ecosistema actual de herramientas para desarrollar mas rapido sin perder control.

**Contenidos**

- VS Code.
- GitHub Copilot.
- Cursor.
- Claude Code.
- Otras herramientas similares que encajen en el flujo del curso.
- Casos de uso: explorar codigo, escribir, refactorizar, depurar, documentar.
- Riesgos de delegar demasiado al asistente.

**Ejercicio practico**

- Resolver una mini tarea con distintas herramientas.
- Comparar velocidad, control, calidad y grado de supervision necesario.

**Resultado del modulo**

Los participantes desarrollan criterio para elegir herramientas segun la tarea, en vez de depender de una sola plataforma.

### Modulo 8. Git para trabajar en equipo

**Objetivo**

Aprender la base de control de versiones para colaborar sin caos.

**Contenidos**

- Que es control de versiones.
- Repositorio, commit, rama y merge.
- Comandos basicos: clone, init, add, commit, push, pull.
- Conflictos simples.
- Gitignore.
- Flujo minimo de trabajo en equipo.

**Ejercicio practico**

- Crear un repo, hacer commits con sentido, abrir una rama, fusionar cambios y resolver un conflicto simple.

**Resultado del modulo**

Los participantes adquieren una base real para trabajar juntos sobre el mismo proyecto.

### Modulo 9. Docker, despliegue y servidor

**Objetivo**

Entender como pasar de "funciona en mi maquina" a una aplicacion que puede correr de forma reproducible y desplegarse.

**Contenidos**

- Que problema resuelve Docker.
- Imagen y contenedor.
- Dockerfile.
- Puertos.
- Variables de entorno en despliegue.
- Logs basicos.
- Servidor, hosting y plataforma gestionada.
- Despliegue en opciones simples como Vercel, Railway o Render.
- Introduccion a un VPS con Docker como opcion mas manual.

**Ejercicio practico**

- Dockerizar una app simple.
- Levantarla localmente en un contenedor.
- Prepararla para un deploy inicial.

**Resultado del modulo**

Los participantes entienden el puente entre desarrollo local y produccion.

### Modulo 10. Proyecto final: una app util con IA

**Objetivo**

Cerrar el curso construyendo algo completo y funcional.

**Opciones de proyecto**

- Asistente de planificacion personal o de equipo.
- Copiloto creativo para ideas, contenido o guiones.
- Mini app de chat con archivos y contexto.
- Agente simple con una o dos herramientas.

**Entregables**

- App funcional.
- Repositorio ordenado.
- Variables de entorno bien configuradas.
- Docker basico.
- Despliegue funcionando.
- Demo final.

**Resultado del modulo**

Los participantes no terminan solo con teoria: terminan con un producto que existe, corre y puede mostrarse.

## Proyecto final recomendado

La opcion mas equilibrada para este curso es construir un asistente de planificacion o un copiloto de trabajo. Ese tipo de proyecto permite cubrir de forma natural casi todos los pilares del programa:

- Uso de LLMs y contexto.
- Prompting y estructura de instrucciones.
- Integracion con APIs.
- Manejo de variables de entorno.
- Trabajo con Git.
- Dockerizacion.
- Despliegue.
- Posible extension hacia agentes o MCP.

## Metodologia sugerida

Cada sesion deberia mezclar tres capas:

- Concepto: para entender el por que.
- Demo: para ver una implementacion concreta.
- Practica: para que el conocimiento quede fijado en un resultado.

La proporcion sugerida es:

- 20 por ciento concepto.
- 30 por ciento demo.
- 50 por ciento practica.

Si la parte practica queda corta, el curso se convierte en una charla interesante pero no en una formacion util.

## Criterios de evaluacion

No conviene evaluar solo si una app responde algo en pantalla. Conviene evaluar si:

- El problema esta bien definido.
- La salida del sistema es util y consistente.
- El contexto y las instrucciones estan bien pensados.
- La app es reproducible.
- El repositorio esta ordenado.
- Las claves y variables de entorno estan bien manejadas.
- El proyecto puede levantarse y desplegarse sin caos.

## Requisitos minimos recomendados

- Computador con acceso a internet.
- Editor de codigo, idealmente VS Code.
- Cuenta en alguna plataforma de IA con acceso a modelos o APIs.
- Git instalado.
- Docker instalado para la parte de contenedores.

## Cierre

Este curso no esta pensado como una introduccion superficial a herramientas de moda. Esta pensado como una formacion base para personas que quieren usar IA para construir productos utiles, entender lo que estan haciendo y desarrollar una forma de trabajo que combine creatividad, criterio tecnico y capacidad real de entrega.